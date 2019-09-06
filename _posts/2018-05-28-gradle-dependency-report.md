---
layout: post
date: 2018-05-28 15:21:27 +0900
categories: til
tags: ["tool"]
---

# Gradle 에서 dependency 확인하기

- `gradle dependencies` 명령을 실행하면 의존성 트리가 표시된다.
- `build.gradle`에 `apply plugin: 'project-report'`를 추가하고 `gradle htmlDependencyReport`를 실행하면 디펜던시 트리가 포함된 html 파일이 생성된다.
