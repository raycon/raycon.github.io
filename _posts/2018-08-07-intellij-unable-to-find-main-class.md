---
layout: post
date: 2018-08-07 15:05:09 +0900
categories: til
tags: ["editor"]
---

# 오류: 기본 클래스 [Application]을(를) 찾거나 로드할 수 없습니다

Gradle 프로젝트를 import 한 뒤 Run 에서 어플리케이션을 실행하면 위 에러가 발생한다. 컴파일 된 파일이 없어서 발생하는 문제인데 `Ctrl + F9`를 눌러서 빌드를 하면 `out`폴더가 생성되고 이후 실행이 가능하다.
