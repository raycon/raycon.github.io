---
layout: post
date: 2018-05-28 15:21:27 +0900
categories: til
tags: ["language"]
---

# Read file from resource

`com.example.test` 패키지의 `ExampleTest.java` 테스트에서 파일을 읽는 방법.

`src/test/resource/com/example/test/abc.xml` 파일을 읽을 때 :

    File file = new File(this.getClass().getResource("abc.xml").getFile());

`src/test/resources/abc.xml` 파일을 읽을 때  :

    File file = new File(this.getClass().getResource("/abc.xml").getFile());
