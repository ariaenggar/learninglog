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
