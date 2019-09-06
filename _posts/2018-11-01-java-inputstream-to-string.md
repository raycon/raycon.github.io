---
layout: post
date: 2018-11-01 16:44:21 +0900
categories: til
tags: ["language"]
---

# InputStream to String

```java
BufferedReader br = new BufferedReader(new InputStreamReader(is));

String line;
while ((line = br.readLine()) != null) {
  System.out.println(line);
}

br.close();
```

Commons IO:

```gradle
// build.gradle
compile 'commons-io:commons-io:2.6'
```

```java
String message = org.apache.commons.io.IOUtils.toString(rd);
```

Java 8:

```java
rd.lines().collect(Collectors.joining());
```
