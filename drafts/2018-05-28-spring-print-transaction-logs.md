---
layout: post
date: 2018-05-28 15:21:27 +0900
categories: til
tags: ["framework"]
---

# Print transaction logs

`logback-spring.xml` 에 아래 내용을 추가한다.

    <logger name="org.hibernate.transaction.JDBCTransaction" level="DEBUG"/>
    <logger name="org.hibernate.jdbc.ConnectionManager" level="DEBUG"/>
    <logger name="org.springframework.orm.jpa.JpaTransactionManager" level="DEBUG"/>
