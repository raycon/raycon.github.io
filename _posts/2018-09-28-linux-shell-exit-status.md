---
layout: post
date: 2018-09-28 10:37:44 +0900
categories: til
tags: ["os"]
---

# Exit Status

> Return status, Exit Code 로 불리기도 한다.

`exit` 명령어로 스크립트의 종료 상태를 쉘에 전달할 수 있다.

유닉스 관례에 따르면 `0`은 성공을 의미하고, `0`이 아닌 값은 특정한 에러 코드를 의미한다.

`exit` 명령어를 실행하지 않고 스크립트가 종료될 경우, 마지막에 실행된 명령어의 종료 상태가 스크립트의 종료 상태가 된다.

`$?` 명령어를 통해서 가장 최근 실행된 명령어의 종료 상태를 확인할 수 있다.

```bash
$ true
$ echo $?
0
$ ! true
$ echo $?
1
```

몇몇 종료 종료 상태는 [예약](http://tldp.org/LDP/abs/html/exitcodes.html)되어 있으므로 사용하면 안된다.
