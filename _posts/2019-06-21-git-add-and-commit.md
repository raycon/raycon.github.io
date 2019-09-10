---
layout: post
date: 2019-06-21 09:20:22 +0900
categories: til
tags: ["tool"]
image: https://images.unsplash.com/photo-1556075798-4825dfaaf498?ixlib=rb-1.2.1&ixid=eyJhcHBfaWQiOjEyMDd9&auto=format&fit=crop&w=1055&q=80
---

# Git add and commit in one command

일반적인 파일 추가 후 커밋 하는 방법

    git add .
    git commit -m "message"

은 귀찮다

alias 를 지정해서 사용하면 편하다

    git config --global alias.ac '!git add -A && git commit -m'
