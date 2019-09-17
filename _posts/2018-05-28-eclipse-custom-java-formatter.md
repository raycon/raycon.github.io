---
layout: post
date: 2018-05-28 15:21:27 +0900
categories: til
tags: ["editor"]
---

# Eclipse 포매터 설정

[Eclipse Java Google Style](https://github.com/google/styleguide/blob/gh-pages/eclipse-java-google-style.xml) 을 받아서 `Edit > Preferences > Java > Code Style > Formatter` 에서 `Import...` 한다. `Edit` 버튼을 누르고 `Indentation > General settings` 에서 다음 항목을 수정한다.

- Indentation size: 2 -> 4
- Tab size: 2 -> 4

## Line Wrapping

- `'enum' declation > Constants`: Wrap all elements, every element on a new line, Force split 체크
- `Annotations > Element-value paris`: Wrap all elements, except first element if not necessary 체크
- `Function Calls > Qualified invocations`: Wrap all elements, except first element if not necessary 체크
