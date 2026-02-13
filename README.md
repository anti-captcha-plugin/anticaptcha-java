You need Java installed.
This is an IntelliJ IDEA project and it should be compatible with Eclipse (but not tested).

Dependencies are located in libs/*.jar

### Examples:
- [Get Balance](https://github.com/anti-captcha/anticaptcha-java/blob/master/src/com/anti_captcha/Main.java#L481)
- [Image to text](https://github.com/anti-captcha/anticaptcha-java/blob/master/src/com/anti_captcha/Main.java#L210)
- [Recapcha V2](https://github.com/anti-captcha/anticaptcha-java/blob/master/src/com/anti_captcha/Main.java#L236)
- [Recaptcha V3](https://github.com/anti-captcha/anticaptcha-java/blob/master/src/com/anti_captcha/Main.java#L307)
- [Recaptcha V2 Enterprise](https://github.com/anti-captcha/anticaptcha-java/blob/master/src/com/anti_captcha/Main.java#L417)
- [HCaptcha](https://github.com/anti-captcha/anticaptcha-java/blob/master/src/com/anti_captcha/Main.java#L263)
- [Funcaptcha](https://github.com/anti-captcha/anticaptcha-java/blob/master/src/com/anti_captcha/Main.java#L496)
- [GeeTest V3](https://github.com/anti-captcha/anticaptcha-java/blob/master/src/com/anti_captcha/Main.java#L77)
- [GeeTest V4](https://github.com/anti-captcha/anticaptcha-java/blob/master/src/com/anti_captcha/Main.java#L113)
- [AntiGate Templates](https://github.com/anti-captcha/anticaptcha-java/blob/master/src/com/anti_captcha/Main.java#L566)



### Compile:
```bash
javac -cp "libs/*" \
 src/com/anti_captcha/*.java \
 src/com/anti_captcha/Api/*.java  \
 src/com/anti_captcha/ApiResponse/*.java \
 src/com/anti_captcha/Helper/*.java \
 src/com/anti_captcha/Http/HttpRequest.java \
 src/com/anti_captcha/Http/HttpResponse.java
```

### Run:
```bash
$ java -cp "src:libs/*" com.anti_captcha.Main
```

### Proxy for API requests
Set JVM system properties in the host application (library usage works the same as console apps).

Programmatic (inside your app, before using the library):
```java
System.setProperty("http.proxyHost", "proxy.example.com");
System.setProperty("http.proxyPort", "8080");
System.setProperty("https.proxyHost", "proxy.example.com");
System.setProperty("https.proxyPort", "8080");
// Or SOCKS5:
// System.setProperty("socksProxyHost", "proxy.example.com");
// System.setProperty("socksProxyPort", "1080");
```

HTTP/HTTPS proxy (JVM args):
```bash
java -Dhttp.proxyHost=proxy.example.com -Dhttp.proxyPort=8080 -Dhttps.proxyHost=proxy.example.com -Dhttps.proxyPort=8080 -cp "src:libs/*" com.anti_captcha.Main
```

SOCKS5 proxy (JVM args):
```bash
java -DsocksProxyHost=proxy.example.com -DsocksProxyPort=1080 -cp "src:libs/*" com.anti_captcha.Main
```

Non-proxy hosts (optional):
```bash
java -Dhttp.nonProxyHosts="localhost|127.0.0.1" -cp "src:libs/*" com.anti_captcha.Main
```
