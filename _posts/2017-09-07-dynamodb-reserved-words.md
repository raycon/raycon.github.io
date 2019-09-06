---
layout: post
date: 2017-09-07 16:28:44 +0900
categories: til
tags: ["aws"]
---

# Reserved Words in DynamoDB

DynamoDB 에는 예약어가 있는데, 이 단어들은 attribute name 으로 쓸 수 없다.
<http://docs.aws.amazon.com/amazondynamodb/latest/developerguide/ReservedWords.html>

이를 해결하기 위해서는 ExpressionAttributeName 을 사용하면 된다.
<http://docs.aws.amazon.com/amazondynamodb/latest/developerguide/ExpressionPlaceholders.html#ExpressionAttributeNames>

[링크]({% post_url 2018-05-28-atom-perforce-package %})