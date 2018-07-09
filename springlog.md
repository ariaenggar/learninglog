# Spring Log

Used for spring family tools, spring boot, spring cloud, etc..


### Spring Centralized Configuration
(https://spring.io/guides/gs/centralized-configuration/)

#### 5 Jul 2018 15:49

Trying spring.cloud.config.server.git.uri=${HOME} not working, using complete full url with "file://" prefix. spring.cloud.config.server.git.uri=spring.cloud.config.server.git.uri=file://C:/Users/LEGION/Desktop/config
(check: https://github.com/spring-guides/gs-centralized-configuration/issues/3, dsyer said it works.)

Firewall turned off with BlockInbound,AllowOutbound policy. Will try AllowInbound at home. Got to go now (15:49)

#### 5 Jul 2018 21:59

All firewall turned off, the client still can't read config using ${HOME}. Will try again later. Using file:// prefix for now.


### Spring Hot Swap with spring-boot-devtools on IntelliJ

#### 9 Jul 2018 14:59

1. add "runtime('org.springframework.boot:spring-boot-devtools')" to dependencies
2. File -> Settings -> Build, Execution, Deployment -> Compiler -> (at right panel) set "Build automatically" to checked -> OK
3. Ctrl + Shift + A -> type "registry" -> select "Regsitry..." (make sure it's with the ellipsis/three dots)
4. Find "compiler.automake.allow.when.app.running" key, set value to true (checked) -> Close
5. Restart IntelliJ


### Spring Boot to DB, HikariCP

#### 9 Jul 2018 15:43

It is said that: 'If you use the spring-boot-starter-jdbc or spring-boot-starter-data-jpa “starters”, you automatically get a dependency to HikariCP.'
https://docs.spring.io/spring-boot/docs/current/reference/html/boot-features-sql.html#boot-features-connect-to-production-database
