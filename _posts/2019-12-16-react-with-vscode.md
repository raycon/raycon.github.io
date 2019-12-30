---
layout: post
date: 2019-12-16 00:00:00 +0900
categories: til
tags: ["vscode", "react"]
---

# React with VSCode

VSCode에서 리액트를 개발하기 위한 설정

## create-react-app

Node.js 를 설치한다. (5.2 이상 버전)

`create-react-app` 모듈을 설치한다.

    npx create-react-app my-app
    cd my-app
    npm start

다음과 같은 구조로 파일이 생성된다.

    my-app
    ├── README.md
    ├── node_modules
    ├── package.json
    ├── .gitignore
    ├── public
    │   ├── favicon.ico
    │   ├── index.html
    │   └── manifest.json
    └── src
        ├── App.css
        ├── App.js
        ├── App.test.js
        ├── index.css
        ├── index.js
        ├── logo.svg
        └── serviceWorker.js

<http://localhost:3000> 에 접속해서 로고가 뱅글뱅글 도는 것을 확인한다.

## VSCode

[ES7 React/Redux/GraphQL/React-Native snippets](https://marketplace.visualstudio.com/items?itemName=dsznajder.es7-react-js-snippets) 확장을 설치한다.

사용할 수 있는 스니펫 목록은 `F1 > ES7 snippet search` 명령으로 확인할 수 있다.
