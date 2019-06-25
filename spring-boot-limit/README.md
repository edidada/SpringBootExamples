# README

lua调试
对lua调试最开始花掉了我不少时间，主要对于redis-cli命令不太熟悉。大家有一样问题的可以参见这篇文章。大致来说就是将写好的脚本放到redis所在文件夹下（我是windows环境），然后在cmd下执行 redis-cli.exe --eval rate_limit.lua test2(key，可重复) , (逗号分隔) init 10101 100 100 10 test2 (后跟参数，空格隔开)。

作者：ro9er
链接：https://www.jianshu.com/p/c8cee1507ccc
来源：简书
简书著作权归作者所有，任何形式的转载都请联系作者获得授权并注明出处。

运行，浏览器访问
[限流测试 test](http://127.0.0.1:8080/test)

[参考文档](https://segmentfault.com/a/1190000016042927)

```

2019-06-25 15:39:21.128  INFO 18412 --- [           main] c.s.example.SpringBootLimitApplication   : Starting SpringBootLimitApplication on ChengWu-Win10 with PID 18412 (D:\github\SpringBootExamples\spring-boot-limit\target\classes started by edidada in D:\github\SpringBootExamples\spring-boot-limit)
2019-06-25 15:39:21.138  INFO 18412 --- [           main] c.s.example.SpringBootLimitApplication   : No active profile set, falling back to default profiles: default
2019-06-25 15:39:21.255  INFO 18412 --- [           main] ConfigServletWebServerApplicationContext : Refreshing org.springframework.boot.web.servlet.context.AnnotationConfigServletWebServerApplicationContext@60d8c9b7: startup date [Tue Jun 25 15:39:21 CST 2019]; root of context hierarchy
2019-06-25 15:39:22.863  INFO 18412 --- [           main] .s.d.r.c.RepositoryConfigurationDelegate : Multiple Spring Data modules found, entering strict repository configuration mode!
2019-06-25 15:39:23.868  INFO 18412 --- [           main] o.s.b.w.embedded.tomcat.TomcatWebServer  : Tomcat initialized with port(s): 8080 (http)
2019-06-25 15:39:23.899  INFO 18412 --- [           main] o.apache.catalina.core.StandardService   : Starting service [Tomcat]
2019-06-25 15:39:23.899  INFO 18412 --- [           main] org.apache.catalina.core.StandardEngine  : Starting Servlet Engine: Apache Tomcat/8.5.34
2019-06-25 15:39:23.899  INFO 18412 --- [ost-startStop-1] o.a.catalina.core.AprLifecycleListener   : The APR based Apache Tomcat Native library which allows optimal performance in production environments was not found on the java.library.path: [D:\Program Files\Java\jdk1.8.0_161\bin;C:\WINDOWS\Sun\Java\bin;C:\WINDOWS\system32;C:\WINDOWS;C:\Users\edidada\.cargo\bin;E:\etcd-v3.3.12-windows-amd64;D:\Program Files\Java\jdk1.8.0_161\bin;G:\apache-jmeter-4.0\bin;C:\Program Files (x86)\Common Files\Oracle\Java\javapath;D:\kubernetes;C:\Program Files\Docker Toolbox\netcat-1.11;C:\Program Files\Docker Toolbox;D:\zookeeper-3.4.10\bin;G:\cmake-3.12.0-win64-x64\bin;E:\gradle-3.5.1\bin;C:\Program Files\qemu;E:\apache-maven-3.6.1\bin;C:\Program Files (x86)\Microsoft Visual Studio 14.0\VC\bin;C:\ProgramData\Chocolatey\lib\chocolatey;D:\android-ndk-r10b;C:\WINDOWS\system32;C:\WINDOWS;C:\WINDOWS\System32\Wbem;C:\WINDOWS\System32\WindowsPowerShell\v1.0\;D:\android-sdk-windows\platform-tools;D:\android-sdk-windows\tools;D:\MinGW\bin;D:\Program Files\ffmpeg-win64-static\bin;C:\Program Files\PuTTY\;D:\mysql-5.7.17-winx64\bin;D:\opencv\build\x64\vc14\bin;C:\Program Files (x86)\WinSCP\;C:\Program Files\Microsoft SQL Server\130\Tools\Binn\;C:\Program Files (x86)\Windows Kits\10\Windows Performance Toolkit\;D:\springbotcli\spring-1.3.0.RELEASE\bin;C:\Program Files\Git\cmd;D:\apktool;C:\WINDOWS\System32\OpenSSH\;G:\node-v8.11.3-win-x64;C:\Program Files\erl9.0\bi;E:\apache-ant-1.10.5\bin;E:\tiancheng\20190311\jna\test\com\sun\jna\win32-x86-64;D:\Program Files\Java\jdk1.8.0_161\jre\bin;C:\WINDOWS\system32;C:\WINDOWS;C:\WINDOWS\System32\Wbem;C:\WINDOWS\System32\WindowsPowerShell\v1.0\;C:\WINDOWS\System32\OpenSSH\;C:\Go\bin;D:\antlr;C:\Program Files\Sublime Text 3;D:\vert.x-3.7.1-full\vertx\bin;C:\Users\edidada\.cargo\bin;d:\Ruby24-x64\bin;C:\Users\edidada\AppData\Local\Microsoft\WindowsApps;;C:\Users\edidada\AppData\Local\Microsoft\WindowsApps;C:\Program Files\JetBrains\CLion 2019.1.2\bin;;C:\Users\edidada\go\bin;C:\Program Files\JetBrains\GoLand 2019.1.1\bin;;C:\Program Files\JetBrains\DataGrip 2019.1.2\bin;;.]
2019-06-25 15:39:24.024  INFO 18412 --- [ost-startStop-1] o.a.c.c.C.[Tomcat].[localhost].[/]       : Initializing Spring embedded WebApplicationContext
2019-06-25 15:39:24.024  INFO 18412 --- [ost-startStop-1] o.s.web.context.ContextLoader            : Root WebApplicationContext: initialization completed in 2774 ms
2019-06-25 15:39:24.200  INFO 18412 --- [ost-startStop-1] o.s.b.w.servlet.ServletRegistrationBean  : Servlet dispatcherServlet mapped to [/]
2019-06-25 15:39:24.207  INFO 18412 --- [ost-startStop-1] o.s.b.w.servlet.FilterRegistrationBean   : Mapping filter: 'characterEncodingFilter' to: [/*]
2019-06-25 15:39:24.208  INFO 18412 --- [ost-startStop-1] o.s.b.w.servlet.FilterRegistrationBean   : Mapping filter: 'hiddenHttpMethodFilter' to: [/*]
2019-06-25 15:39:24.208  INFO 18412 --- [ost-startStop-1] o.s.b.w.servlet.FilterRegistrationBean   : Mapping filter: 'httpPutFormContentFilter' to: [/*]
2019-06-25 15:39:24.208  INFO 18412 --- [ost-startStop-1] o.s.b.w.servlet.FilterRegistrationBean   : Mapping filter: 'requestContextFilter' to: [/*]
2019-06-25 15:39:24.743  INFO 18412 --- [           main] o.s.w.s.handler.SimpleUrlHandlerMapping  : Mapped URL path [/**/favicon.ico] onto handler of type [class org.springframework.web.servlet.resource.ResourceHttpRequestHandler]
2019-06-25 15:39:25.158  INFO 18412 --- [           main] s.w.s.m.m.a.RequestMappingHandlerAdapter : Looking for @ControllerAdvice: org.springframework.boot.web.servlet.context.AnnotationConfigServletWebServerApplicationContext@60d8c9b7: startup date [Tue Jun 25 15:39:21 CST 2019]; root of context hierarchy
2019-06-25 15:39:25.205  INFO 18412 --- [           main] s.w.s.m.m.a.RequestMappingHandlerMapping : Mapped "{[/test],methods=[GET]}" onto public java.lang.String com.souyunku.example.controller.LimiterController.luaLimiter()
2019-06-25 15:39:25.221  INFO 18412 --- [           main] s.w.s.m.m.a.RequestMappingHandlerMapping : Mapped "{[/error]}" onto public org.springframework.http.ResponseEntity<java.util.Map<java.lang.String, java.lang.Object>> org.springframework.boot.autoconfigure.web.servlet.error.BasicErrorController.error(javax.servlet.http.HttpServletRequest)
2019-06-25 15:39:25.221  INFO 18412 --- [           main] s.w.s.m.m.a.RequestMappingHandlerMapping : Mapped "{[/error],produces=[text/html]}" onto public org.springframework.web.servlet.ModelAndView org.springframework.boot.autoconfigure.web.servlet.error.BasicErrorController.errorHtml(javax.servlet.http.HttpServletRequest,javax.servlet.http.HttpServletResponse)
2019-06-25 15:39:25.252  INFO 18412 --- [           main] o.s.w.s.handler.SimpleUrlHandlerMapping  : Mapped URL path [/webjars/**] onto handler of type [class org.springframework.web.servlet.resource.ResourceHttpRequestHandler]
2019-06-25 15:39:25.252  INFO 18412 --- [           main] o.s.w.s.handler.SimpleUrlHandlerMapping  : Mapped URL path [/**] onto handler of type [class org.springframework.web.servlet.resource.ResourceHttpRequestHandler]
2019-06-25 15:39:25.549  INFO 18412 --- [           main] o.s.j.e.a.AnnotationMBeanExporter        : Registering beans for JMX exposure on startup
2019-06-25 15:39:25.630  INFO 18412 --- [           main] o.s.b.w.embedded.tomcat.TomcatWebServer  : Tomcat started on port(s): 8080 (http) with context path ''
2019-06-25 15:39:25.630  INFO 18412 --- [           main] c.s.example.SpringBootLimitApplication   : Started SpringBootLimitApplication in 5.514 seconds (JVM running for 7.853)
2019-06-25 15:39:27.665  INFO 18412 --- [nio-8080-exec-2] o.a.c.c.C.[Tomcat].[localhost].[/]       : Initializing Spring FrameworkServlet 'dispatcherServlet'
2019-06-25 15:39:27.665  INFO 18412 --- [nio-8080-exec-2] o.s.web.servlet.DispatcherServlet        : FrameworkServlet 'dispatcherServlet': initialization started
2019-06-25 15:39:27.700  INFO 18412 --- [nio-8080-exec-2] o.s.web.servlet.DispatcherServlet        : FrameworkServlet 'dispatcherServlet': initialization completed in 35 ms
2019-06-25 15:39:27.836  INFO 18412 --- [nio-8080-exec-2] io.lettuce.core.EpollProvider            : Starting without optional epoll library
2019-06-25 15:39:27.837  INFO 18412 --- [nio-8080-exec-2] io.lettuce.core.KqueueProvider           : Starting without optional kqueue library
2019-06-25 15:39:29.987  INFO 18412 --- [nio-8080-exec-2] com.souyunku.example.config.LimitAspect  : 限流时间段内访问第：1 次
2019-06-25 15:39:31.960  INFO 18412 --- [xecutorLoop-1-2] i.l.core.protocol.ConnectionWatchdog     : Reconnecting, last destination was /60.205.225.118:6379
2019-06-25 15:39:32.007  INFO 18412 --- [ioEventLoop-4-2] i.l.core.protocol.ReconnectionHandler    : Reconnected to 60.205.225.118:6379
2019-06-25 15:39:33.901  INFO 18412 --- [ioEventLoop-4-3] i.l.core.protocol.ReconnectionHandler    : Reconnected to 60.205.225.118:6379
2019-06-25 15:39:36.007  INFO 18412 --- [ioEventLoop-4-4] i.l.core.protocol.ReconnectionHandler    : Reconnected to 60.205.225.118:6379
2019-06-25 15:39:37.965  INFO 18412 --- [xecutorLoop-1-1] i.l.core.protocol.ConnectionWatchdog     : Reconnecting, last destination was /60.205.225.118:6379
2019-06-25 15:39:37.999  INFO 18412 --- [ioEventLoop-4-1] i.l.core.protocol.ReconnectionHandler    : Reconnected to 60.205.225.118:6379
2019-06-25 15:39:40.009  INFO 18412 --- [ioEventLoop-4-2] i.l.core.protocol.ReconnectionHandler    : Reconnected to 60.205.225.118:6379
2019-06-25 15:39:40.683  INFO 18412 --- [nio-8080-exec-4] com.souyunku.example.config.LimitAspect  : 限流时间段内访问第：1 次
2019-06-25 15:39:42.002  INFO 18412 --- [ioEventLoop-4-3] i.l.core.protocol.ReconnectionHandler    : Reconnected to 60.205.225.118:6379
2019-06-25 15:39:43.964  INFO 18412 --- [xecutorLoop-1-4] i.l.core.protocol.ConnectionWatchdog     : Reconnecting, last destination was /60.205.225.118:6379
2019-06-25 15:39:43.999  INFO 18412 --- [ioEventLoop-4-4] i.l.core.protocol.ReconnectionHandler    : Reconnected to 60.205.225.118:6379
2019-06-25 15:39:44.454  INFO 18412 --- [nio-8080-exec-5] com.souyunku.example.config.LimitAspect  : 限流时间段内访问第：1 次
2019-06-25 15:39:44.708  INFO 18412 --- [nio-8080-exec-7] com.souyunku.example.config.LimitAspect  : 限流时间段内访问第：2 次
2019-06-25 15:39:44.854  INFO 18412 --- [nio-8080-exec-8] com.souyunku.example.config.LimitAspect  : 限流时间段内访问第：3 次
2019-06-25 15:39:45.044  INFO 18412 --- [nio-8080-exec-9] com.souyunku.example.config.LimitAspect  : 限流时间段内访问第：4 次
2019-06-25 15:39:45.221  INFO 18412 --- [io-8080-exec-10] com.souyunku.example.config.LimitAspect  : 限流时间段内访问第：5 次
2019-06-25 15:39:45.376  INFO 18412 --- [nio-8080-exec-2] com.souyunku.example.config.LimitAspect  : 限流时间段内访问第：6 次
2019-06-25 15:39:45.576  INFO 18412 --- [nio-8080-exec-1] com.souyunku.example.config.LimitAspect  : 限流时间段内访问第：7 次
2019-06-25 15:39:46.488  INFO 18412 --- [nio-8080-exec-4] com.souyunku.example.config.LimitAspect  : 限流时间段内访问第：8 次
2019-06-25 15:39:47.596  INFO 18412 --- [nio-8080-exec-5] com.souyunku.example.config.LimitAspect  : 限流时间段内访问第：9 次
2019-06-25 15:39:48.423  INFO 18412 --- [nio-8080-exec-8] com.souyunku.example.config.LimitAspect  : 限流时间段内访问第：10 次
2019-06-25 15:39:49.448 ERROR 18412 --- [io-8080-exec-10] o.a.c.c.C.[.[.[/].[dispatcherServlet]    : Servlet.service() for servlet [dispatcherServlet] in context with path [] threw exception [Request processing failed; nested exception is java.lang.RuntimeException: 已经到设置限流次数] with root cause

java.lang.RuntimeException: 已经到设置限流次数
	at com.souyunku.example.config.LimitAspect.interceptor(LimitAspect.java:73) ~[classes/:na]
	at sun.reflect.NativeMethodAccessorImpl.invoke0(Native Method) ~[na:1.8.0_161]
	at sun.reflect.NativeMethodAccessorImpl.invoke(NativeMethodAccessorImpl.java:62) ~[na:1.8.0_161]
	at sun.reflect.DelegatingMethodAccessorImpl.invoke(DelegatingMethodAccessorImpl.java:43) ~[na:1.8.0_161]
	at java.lang.reflect.Method.invoke(Method.java:498) ~[na:1.8.0_161]
	at org.springframework.aop.aspectj.AbstractAspectJAdvice.invokeAdviceMethodWithGivenArgs(AbstractAspectJAdvice.java:644) ~[spring-aop-5.0.10.RELEASE.jar:5.0.10.RELEASE]
	at org.springframework.aop.aspectj.AbstractAspectJAdvice.invokeAdviceMethod(AbstractAspectJAdvice.java:633) ~[spring-aop-5.0.10.RELEASE.jar:5.0.10.RELEASE]
	at org.springframework.aop.aspectj.AspectJAroundAdvice.invoke(AspectJAroundAdvice.java:70) ~[spring-aop-5.0.10.RELEASE.jar:5.0.10.RELEASE]
	at org.springframework.aop.framework.ReflectiveMethodInvocation.proceed(ReflectiveMethodInvocation.java:185) ~[spring-aop-5.0.10.RELEASE.jar:5.0.10.RELEASE]
	at org.springframework.aop.interceptor.ExposeInvocationInterceptor.invoke(ExposeInvocationInterceptor.java:92) ~[spring-aop-5.0.10.RELEASE.jar:5.0.10.RELEASE]
	at org.springframework.aop.framework.ReflectiveMethodInvocation.proceed(ReflectiveMethodInvocation.java:185) ~[spring-aop-5.0.10.RELEASE.jar:5.0.10.RELEASE]
	at org.springframework.aop.framework.CglibAopProxy$DynamicAdvisedInterceptor.intercept(CglibAopProxy.java:688) ~[spring-aop-5.0.10.RELEASE.jar:5.0.10.RELEASE]
	at com.souyunku.example.controller.LimiterController$$EnhancerBySpringCGLIB$$379ed738.luaLimiter(<generated>) ~[classes/:na]
	at sun.reflect.NativeMethodAccessorImpl.invoke0(Native Method) ~[na:1.8.0_161]
	at sun.reflect.NativeMethodAccessorImpl.invoke(NativeMethodAccessorImpl.java:62) ~[na:1.8.0_161]
	at sun.reflect.DelegatingMethodAccessorImpl.invoke(DelegatingMethodAccessorImpl.java:43) ~[na:1.8.0_161]
	at java.lang.reflect.Method.invoke(Method.java:498) ~[na:1.8.0_161]
	at org.springframework.web.method.support.InvocableHandlerMethod.doInvoke(InvocableHandlerMethod.java:209) ~[spring-web-5.0.10.RELEASE.jar:5.0.10.RELEASE]
	at org.springframework.web.method.support.InvocableHandlerMethod.invokeForRequest(InvocableHandlerMethod.java:136) ~[spring-web-5.0.10.RELEASE.jar:5.0.10.RELEASE]
	at org.springframework.web.servlet.mvc.method.annotation.ServletInvocableHandlerMethod.invokeAndHandle(ServletInvocableHandlerMethod.java:102) ~[spring-webmvc-5.0.10.RELEASE.jar:5.0.10.RELEASE]
	at org.springframework.web.servlet.mvc.method.annotation.RequestMappingHandlerAdapter.invokeHandlerMethod(RequestMappingHandlerAdapter.java:891) ~[spring-webmvc-5.0.10.RELEASE.jar:5.0.10.RELEASE]
	at org.springframework.web.servlet.mvc.method.annotation.RequestMappingHandlerAdapter.handleInternal(RequestMappingHandlerAdapter.java:797) ~[spring-webmvc-5.0.10.RELEASE.jar:5.0.10.RELEASE]
	at org.springframework.web.servlet.mvc.method.AbstractHandlerMethodAdapter.handle(AbstractHandlerMethodAdapter.java:87) ~[spring-webmvc-5.0.10.RELEASE.jar:5.0.10.RELEASE]
	at org.springframework.web.servlet.DispatcherServlet.doDispatch(DispatcherServlet.java:991) ~[spring-webmvc-5.0.10.RELEASE.jar:5.0.10.RELEASE]
	at org.springframework.web.servlet.DispatcherServlet.doService(DispatcherServlet.java:925) ~[spring-webmvc-5.0.10.RELEASE.jar:5.0.10.RELEASE]
	at org.springframework.web.servlet.FrameworkServlet.processRequest(FrameworkServlet.java:974) ~[spring-webmvc-5.0.10.RELEASE.jar:5.0.10.RELEASE]
	at org.springframework.web.servlet.FrameworkServlet.doGet(FrameworkServlet.java:866) ~[spring-webmvc-5.0.10.RELEASE.jar:5.0.10.RELEASE]
	at javax.servlet.http.HttpServlet.service(HttpServlet.java:635) ~[tomcat-embed-core-8.5.34.jar:8.5.34]
	at org.springframework.web.servlet.FrameworkServlet.service(FrameworkServlet.java:851) ~[spring-webmvc-5.0.10.RELEASE.jar:5.0.10.RELEASE]
	at javax.servlet.http.HttpServlet.service(HttpServlet.java:742) ~[tomcat-embed-core-8.5.34.jar:8.5.34]
	at org.apache.catalina.core.ApplicationFilterChain.internalDoFilter(ApplicationFilterChain.java:231) ~[tomcat-embed-core-8.5.34.jar:8.5.34]
	at org.apache.catalina.core.ApplicationFilterChain.doFilter(ApplicationFilterChain.java:166) ~[tomcat-embed-core-8.5.34.jar:8.5.34]
	at org.apache.tomcat.websocket.server.WsFilter.doFilter(WsFilter.java:52) ~[tomcat-embed-websocket-8.5.34.jar:8.5.34]
	at org.apache.catalina.core.ApplicationFilterChain.internalDoFilter(ApplicationFilterChain.java:193) ~[tomcat-embed-core-8.5.34.jar:8.5.34]
	at org.apache.catalina.core.ApplicationFilterChain.doFilter(ApplicationFilterChain.java:166) ~[tomcat-embed-core-8.5.34.jar:8.5.34]
	at org.springframework.web.filter.RequestContextFilter.doFilterInternal(RequestContextFilter.java:99) ~[spring-web-5.0.10.RELEASE.jar:5.0.10.RELEASE]
	at org.springframework.web.filter.OncePerRequestFilter.doFilter(OncePerRequestFilter.java:107) ~[spring-web-5.0.10.RELEASE.jar:5.0.10.RELEASE]
	at org.apache.catalina.core.ApplicationFilterChain.internalDoFilter(ApplicationFilterChain.java:193) ~[tomcat-embed-core-8.5.34.jar:8.5.34]
	at org.apache.catalina.core.ApplicationFilterChain.doFilter(ApplicationFilterChain.java:166) ~[tomcat-embed-core-8.5.34.jar:8.5.34]
	at org.springframework.web.filter.HttpPutFormContentFilter.doFilterInternal(HttpPutFormContentFilter.java:109) ~[spring-web-5.0.10.RELEASE.jar:5.0.10.RELEASE]
	at org.springframework.web.filter.OncePerRequestFilter.doFilter(OncePerRequestFilter.java:107) ~[spring-web-5.0.10.RELEASE.jar:5.0.10.RELEASE]
	at org.apache.catalina.core.ApplicationFilterChain.internalDoFilter(ApplicationFilterChain.java:193) ~[tomcat-embed-core-8.5.34.jar:8.5.34]
	at org.apache.catalina.core.ApplicationFilterChain.doFilter(ApplicationFilterChain.java:166) ~[tomcat-embed-core-8.5.34.jar:8.5.34]
	at org.springframework.web.filter.HiddenHttpMethodFilter.doFilterInternal(HiddenHttpMethodFilter.java:93) ~[spring-web-5.0.10.RELEASE.jar:5.0.10.RELEASE]
	at org.springframework.web.filter.OncePerRequestFilter.doFilter(OncePerRequestFilter.java:107) ~[spring-web-5.0.10.RELEASE.jar:5.0.10.RELEASE]
	at org.apache.catalina.core.ApplicationFilterChain.internalDoFilter(ApplicationFilterChain.java:193) ~[tomcat-embed-core-8.5.34.jar:8.5.34]
	at org.apache.catalina.core.ApplicationFilterChain.doFilter(ApplicationFilterChain.java:166) ~[tomcat-embed-core-8.5.34.jar:8.5.34]
	at org.springframework.web.filter.CharacterEncodingFilter.doFilterInternal(CharacterEncodingFilter.java:200) ~[spring-web-5.0.10.RELEASE.jar:5.0.10.RELEASE]
	at org.springframework.web.filter.OncePerRequestFilter.doFilter(OncePerRequestFilter.java:107) ~[spring-web-5.0.10.RELEASE.jar:5.0.10.RELEASE]
	at org.apache.catalina.core.ApplicationFilterChain.internalDoFilter(ApplicationFilterChain.java:193) ~[tomcat-embed-core-8.5.34.jar:8.5.34]
	at org.apache.catalina.core.ApplicationFilterChain.doFilter(ApplicationFilterChain.java:166) ~[tomcat-embed-core-8.5.34.jar:8.5.34]
	at org.apache.catalina.core.StandardWrapperValve.invoke(StandardWrapperValve.java:198) ~[tomcat-embed-core-8.5.34.jar:8.5.34]
	at org.apache.catalina.core.StandardContextValve.invoke(StandardContextValve.java:96) [tomcat-embed-core-8.5.34.jar:8.5.34]
	at org.apache.catalina.authenticator.AuthenticatorBase.invoke(AuthenticatorBase.java:493) [tomcat-embed-core-8.5.34.jar:8.5.34]
	at org.apache.catalina.core.StandardHostValve.invoke(StandardHostValve.java:140) [tomcat-embed-core-8.5.34.jar:8.5.34]
	at org.apache.catalina.valves.ErrorReportValve.invoke(ErrorReportValve.java:81) [tomcat-embed-core-8.5.34.jar:8.5.34]
	at org.apache.catalina.core.StandardEngineValve.invoke(StandardEngineValve.java:87) [tomcat-embed-core-8.5.34.jar:8.5.34]
	at org.apache.catalina.connector.CoyoteAdapter.service(CoyoteAdapter.java:342) [tomcat-embed-core-8.5.34.jar:8.5.34]
	at org.apache.coyote.http11.Http11Processor.service(Http11Processor.java:800) [tomcat-embed-core-8.5.34.jar:8.5.34]
	at org.apache.coyote.AbstractProcessorLight.process(AbstractProcessorLight.java:66) [tomcat-embed-core-8.5.34.jar:8.5.34]
	at org.apache.coyote.AbstractProtocol$ConnectionHandler.process(AbstractProtocol.java:806) [tomcat-embed-core-8.5.34.jar:8.5.34]
	at org.apache.tomcat.util.net.NioEndpoint$SocketProcessor.doRun(NioEndpoint.java:1498) [tomcat-embed-core-8.5.34.jar:8.5.34]
	at org.apache.tomcat.util.net.SocketProcessorBase.run(SocketProcessorBase.java:49) [tomcat-embed-core-8.5.34.jar:8.5.34]
	at java.util.concurrent.ThreadPoolExecutor.runWorker(ThreadPoolExecutor.java:1149) [na:1.8.0_161]
	at java.util.concurrent.ThreadPoolExecutor$Worker.run(ThreadPoolExecutor.java:624) [na:1.8.0_161]
	at org.apache.tomcat.util.threads.TaskThread$WrappingRunnable.run(TaskThread.java:61) [tomcat-embed-core-8.5.34.jar:8.5.34]
	at java.lang.Thread.run(Thread.java:748) [na:1.8.0_161]

2019-06-25 15:39:50.963  INFO 18412 --- [xecutorLoop-1-1] i.l.core.protocol.ConnectionWatchdog     : Reconnecting, last destination was /60.205.225.118:6379
2019-06-25 15:39:51.010  INFO 18412 --- [ioEventLoop-4-1] i.l.core.protocol.ReconnectionHandler    : Reconnected to 60.205.225.118:6379
2019-06-25 15:39:53.006  INFO 18412 --- [ioEventLoop-4-2] i.l.core.protocol.ReconnectionHandler    : Reconnected to 60.205.225.118:6379
2019-06-25 15:39:55.010  INFO 18412 --- [ioEventLoop-4-3] i.l.core.protocol.ReconnectionHandler    : Reconnected to 60.205.225.118:6379
2019-06-25 15:39:56.864  INFO 18412 --- [xecutorLoop-1-4] i.l.core.protocol.ConnectionWatchdog     : Reconnecting, last destination was /60.205.225.118:6379
2019-06-25 15:39:56.902  INFO 18412 --- [ioEventLoop-4-4] i.l.core.protocol.ReconnectionHandler    : Reconnected to 60.205.225.118:6379
2019-06-25 15:39:58.918  INFO 18412 --- [ioEventLoop-4-1] i.l.core.protocol.ReconnectionHandler    : Reconnected to 60.205.225.118:6379
2019-06-25 15:40:00.918  INFO 18412 --- [ioEventLoop-4-2] i.l.core.protocol.ReconnectionHandler    : Reconnected to 60.205.225.118:6379
2019-06-25 15:40:02.868  INFO 18412 --- [xecutorLoop-1-3] i.l.core.protocol.ConnectionWatchdog     : Reconnecting, last destination was /60.205.225.118:6379
2019-06-25 15:40:02.914  INFO 18412 --- [ioEventLoop-4-3] i.l.core.protocol.ReconnectionHandler    : Reconnected to 60.205.225.118:6379
2019-06-25 15:40:04.914  INFO 18412 --- [ioEventLoop-4-4] i.l.core.protocol.ReconnectionHandler    : Reconnected to 60.205.225.118:6379
2019-06-25 15:40:07.001  INFO 18412 --- [ioEventLoop-4-1] i.l.core.protocol.ReconnectionHandler    : Reconnected to 60.205.225.118:6379
2019-06-25 15:40:08.963  INFO 18412 --- [xecutorLoop-1-2] i.l.core.protocol.ConnectionWatchdog     : Reconnecting, last destination was /60.205.225.118:6379
2019-06-25 15:40:09.010  INFO 18412 --- [ioEventLoop-4-2] i.l.core.protocol.ReconnectionHandler    : Reconnected to 60.205.225.118:6379
2019-06-25 15:40:11.011  INFO 18412 --- [ioEventLoop-4-3] i.l.core.protocol.ReconnectionHandler    : Reconnected to 60.205.225.118:6379
2019-06-25 15:40:13.014  INFO 18412 --- [ioEventLoop-4-4] i.l.core.protocol.ReconnectionHandler    : Reconnected to 60.205.225.118:6379
2019-06-25 15:40:14.967  INFO 18412 --- [xecutorLoop-1-1] i.l.core.protocol.ConnectionWatchdog     : Reconnecting, last destination was /60.205.225.118:6379
2019-06-25 15:40:15.004  INFO 18412 --- [ioEventLoop-4-1] i.l.core.protocol.ReconnectionHandler    : Reconnected to 60.205.225.118:6379
2019-06-25 15:40:17.041  INFO 18412 --- [ioEventLoop-4-2] i.l.core.protocol.ReconnectionHandler    : Reconnected to 60.205.225.118:6379
2019-06-25 15:40:18.926  INFO 18412 --- [ioEventLoop-4-3] i.l.core.protocol.ReconnectionHandler    : Reconnected to 60.205.225.118:6379
2019-06-25 15:40:20.874  INFO 18412 --- [xecutorLoop-1-4] i.l.core.protocol.ConnectionWatchdog     : Reconnecting, last destination was /60.205.225.118:6379
2019-06-25 15:40:20.905  INFO 18412 --- [ioEventLoop-4-4] i.l.core.protocol.ReconnectionHandler    : Reconnected to 60.205.225.118:6379
2019-06-25 15:40:22.905  INFO 18412 --- [ioEventLoop-4-1] i.l.core.protocol.ReconnectionHandler    : Reconnected to 60.205.225.118:6379
2019-06-25 15:40:24.920  INFO 18412 --- [ioEventLoop-4-2] i.l.core.protocol.ReconnectionHandler    : Reconnected to 60.205.225.118:6379
2019-06-25 15:40:26.873  INFO 18412 --- [xecutorLoop-1-3] i.l.core.protocol.ConnectionWatchdog     : Reconnecting, last destination was /60.205.225.118:6379
2019-06-25 15:40:26.920  INFO 18412 --- [ioEventLoop-4-3] i.l.core.protocol.ReconnectionHandler    : Reconnected to 60.205.225.118:6379
2019-06-25 15:40:29.014  INFO 18412 --- [ioEventLoop-4-4] i.l.core.protocol.ReconnectionHandler    : Reconnected to 60.205.225.118:6379
2019-06-25 15:40:31.014  INFO 18412 --- [ioEventLoop-4-1] i.l.core.protocol.ReconnectionHandler    : Reconnected to 60.205.225.118:6379
2019-06-25 15:40:32.967  INFO 18412 --- [xecutorLoop-1-2] i.l.core.protocol.ConnectionWatchdog     : Reconnecting, last destination was /60.205.225.118:6379
2019-06-25 15:40:33.014  INFO 18412 --- [ioEventLoop-4-2] i.l.core.protocol.ReconnectionHandler    : Reconnected to 60.205.225.118:6379
2019-06-25 15:40:34.998  INFO 18412 --- [ioEventLoop-4-3] i.l.core.protocol.ReconnectionHandler    : Reconnected to 60.205.225.118:6379

```
