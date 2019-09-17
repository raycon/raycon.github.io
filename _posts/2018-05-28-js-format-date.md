---
layout: post
date: 2018-05-28 15:21:27 +0900
categories: til
tags: ["language"]
---

# 오늘 날짜 시간 포맷하는 방법

<http://stackoverflow.com/questions/10645994/node-js-how-to-format-a-date-string-in-utc>

```javascript
new Date().toISOString()
// > '2012-11-04T14:51:06.157Z'

new Date().toISOString().
  replace(/T/, ' ').      // replace T with a space
  replace(/\..+/, '')     // delete the dot and everything after
// > '2012-11-04 14:55:45'

// in one line
new Date().toISOString().replace(/T/, ' ').replace(/\..+/, '')
```
