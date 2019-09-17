---
layout: post
date: 2018-05-28 15:21:27 +0900
categories: til
tags: ["language"]
---

# 자바스크립트에서 문자열을 라인별로 나누는 방법

`\r\n`이나 `\n` 을 기준으로 자름 :

    lines = str.split(/\r?\n/);

`\r`, `\n`이 아닌(`^`) 연속된 문자를 기준 찾아서 저장함 :

    lines = str.match(/[^\r\n]+/g)

이 방법은 빈 라인이 생기지 않아서 좋다.
