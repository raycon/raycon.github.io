---
layout: post
date: 2018-06-07 13:55:03 +0900
categories: til
tags: ["language"]
---

# Lombok

gtter/setter, equals, hashCode, toString과 같은 메소드나 log 같은 필드를 주입해주는 라이브러리.

> Never write another getter or equals method again

## Install

### Gradle

#### 플러그인 사용

```gradle
plugins {
    id 'io.franzbecker.gradle-lombok' version '2.1'
}
```

`gradle-lombok` 플러그인을 지정하면 바로 사용 가능하다.

#### 플러그인 미사용

```gradle
configurations {
    compileOnly {
        extendsFrom annotationProcessor
    }
}

dependencies {
    compileOnly 'org.projectlombok:lombok'
    annotationProcessor 'org.projectlombok:lombok'
}
```

### Eclipse

lombok을 설정한 gradle 프로젝트에서 아래 task 를 실행한다.

    gradlew installLombok

다이얼로그가 뜨면 다음과 같이 설정한다.

- `Specify location...`을 선택
- 설치된 `eclipse.exe`를 지정
- `Install / Update`

eclipse가 설치된 경로에 `lombok.jar`가 복사되고, `eclipse.ini`에 다음 내용이 추가된다.

    -javaagent:[ECLIPSE_HOME]\lombok.jar

<https://projectlombok.org/download> 에서 `lombok.jar` 다운로드해서 설치할 수도 있다.

### Intellij IDEA

- `File > Settings > Plugins`
- `Browse repositories...`
- Lombok Plugin 검색
- Install & Restart

프로젝트 설정에서 다음 설정을 해야 에러가 발생하지 않는다.

- `File > Settings > Build, Execution, Deployment > Compiler > Annotation Processors`
- `Enable annotation processing` 체크

## Usage

- <http://www.coolio.so/lombok-%EC%82%AC%EC%9A%A9%EB%B2%95/>
- <https://projectlombok.org/features/all>

`@Slf4j` 상용시 `org.slf4j.LoggerFactory cannot be resolved to a type` 에러가 발생할 경우 `build.gradle`에 다음 내용을 추가한다.

    compile 'ch.qos.logback:logback-classic:1.2.3'
