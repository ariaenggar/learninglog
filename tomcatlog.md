# Tomcat Log

### Session Timeout

#### 13 Sep 2018

Unlike Jetty and Undertow, Tomcat only supports minute precision for session timeout. Any value that is greater than zero is converted to minutes with a minimum of 1 minute
(https://github.com/spring-projects/spring-boot/issues/7383#issuecomment-260383745)

### Unable to Login to manager, tomcat 8.5 and 9

#### 08 Nov 2018

Besides set tomcat-users.xml, comment the <Valve/> element in webapps/manager/META-INF/context.xml to enable tomcat manager accessed from remote IP
