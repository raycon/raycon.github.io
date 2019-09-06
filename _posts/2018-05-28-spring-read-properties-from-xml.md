---
layout: post
date: 2018-05-28 15:21:27 +0900
categories: til
tags: ["framework"]
---

# src/main/resources 폴더의 xml 파일 읽는법

```java
Resource resource = appContext.getResource("classpath:data.xml");
Properties properties = new Properties();

try (InputStream is = resource.getInputStream()) {
    properties.loadFromXML(is);
} catch (IOException e) {
    e.printStackTrace();
}
```
