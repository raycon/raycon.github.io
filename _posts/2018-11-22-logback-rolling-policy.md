---
layout: post
date: 2018-11-22 10:34:10 +0900
categories: til
tags: ["framework"]
thumbnail: rolling-wave.jpg
---

# Logback Rolling Policy

## 시간, 사이즈로 로그 파일 나누기

`1.1.7` 이전 버전:

예전에는 `TimeBasedRollingPolicy`에 `SizeAndTimeBasedFNATP`를 적용해서 `maxFileSize` 옵션을 적용했었다. 현재 이 방법은 공식 문서에서 삭제되었으나, 작동은 한다. `%d`와 `%i`는 필수로 지정해야 한다.

```xml
...
  <appender name="ROLLING" class="ch.qos.logback.core.rolling.RollingFileAppender">
    <file>mylog.txt</file>
    <rollingPolicy class="ch.qos.logback.core.rolling.TimeBasedRollingPolicy">
      <fileNamePattern>mylog-%d{yyyy-MM-dd}.%i.txt</fileNamePattern>
      <timeBasedFileNamingAndTriggeringPolicy class="ch.qos.logback.core.rolling.SizeAndTimeBasedFNATP">
        <maxFileSize>10MB</maxFileSize>
      </timeBasedFileNamingAndTriggeringPolicy>
    </rollingPolicy>
  </appender>
...
```

현재:

`SizeAndTimeBasedRollingPolicy`에 `maxFileSize` 옵션으로 각 파일당 사이즈를 지정하도록 수정되었다. [SizeAndtimeBasedRollingPolicy.java](https://github.com/qos-ch/logback/blob/master/logback-core/src/main/java/ch/qos/logback/core/rolling/SizeAndTimeBasedRollingPolicy.java)를 보면 `SizeAndTimeBasedFNATP`를 변수로 가지고 있다.

```xml
<configuration>
  <appender name="ROLLING" class="ch.qos.logback.core.rolling.RollingFileAppender">
    <file>mylog.txt</file>
    <rollingPolicy class="ch.qos.logback.core.rolling.SizeAndTimeBasedRollingPolicy">
      <!-- rollover daily -->
      <fileNamePattern>mylog-%d{yyyy-MM-dd}.%i.txt</fileNamePattern>
       <!-- each file should be at most 100MB, keep 60 days worth of history, but at most 20GB -->
       <maxFileSize>100MB</maxFileSize>
       <maxHistory>60</maxHistory>
       <totalSizeCap>20GB</totalSizeCap>
    </rollingPolicy>
    <encoder>
      <pattern>%msg%n</pattern>
    </encoder>
  </appender>


  <root level="DEBUG">
    <appender-ref ref="ROLLING" />
  </root>

</configuration>
```
