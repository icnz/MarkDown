**1、druid 数据连接错误 discard long time none received connection**

```java
if (valid && isMySql) { // unexcepted branch
    long lastPacketReceivedTimeMs = MySqlUtils.getLastPacketReceivedTimeMs(conn);
    if (lastPacketReceivedTimeMs > 0) {
        long mysqlIdleMillis = currentTimeMillis - lastPacketReceivedTimeMs;
        if (lastPacketReceivedTimeMs > 0 //
                && mysqlIdleMillis >= timeBetweenEvictionRunsMillis) {
            discardConnection(holder);
            String errorMsg = "discard long time none received connection. "
                    + ", jdbcUrl : " + jdbcUrl
                    + ", version : " + VERSION.getVersionNumber()
                    + ", lastPacketReceivedIdleMillis : " + mysqlIdleMillis;
            LOG.warn(errorMsg);
            return false;
        }
    }
}
```

解决1：运行参数中增加：-Ddruid.mysql.usePingMethod=false

原理是让验证空闲连接使用 select 1，而不是使用MySQL的Ping，这样就刷新了上次使用时间，不会出现空闲 60秒以上的连接。

```java
public void configFromProperties(Properties properties) {
    String property = properties.getProperty("druid.mysql.usePingMethod");
    if ("true".equals(property)) {
        setUsePingMethod(true);
    } else if ("false".equals(property)) {
       setUsePingMethod(false);
    }
}
```

解决2：在配置中加timeBetweenEvictionRunsMillis:1800000（待验证）