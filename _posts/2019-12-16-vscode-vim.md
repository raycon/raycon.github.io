---
layout: post
date: 2019-12-16 00:00:00 +0900
categories: til
tags: ["vscode", "vim"]
---

# VSCode VIM

VSCode 에서 VIM 확장을 사용한다.

## Extensions

[Vim](https://marketplace.visualstudio.com/items?itemName=vscodevim.vim) 확장을 설치한다.

## Configurations

`.vimrc_vscode` 파일을 만들어서 아래 내용을 입력한다.

    " j and k move around wrapped line

    " Windows navigation
    nmap <C-h> <C-w>h
    nmap <C-j> <C-w>j
    nmap <C-k> <C-w>k
    nmap <C-l> <C-w>l

    " Center search results
    nmap n nzz
    nmap N Nzz
    nmap * *zz
    nmap # #zz
    nmap g* g*zz
    nmap g# g#zz

2019년도 12월 기준으로 `vim` 플러그인은 키 매핑만 지원한다.

`settings.json` 에 아래 내용을 추가한다.

    // VIM
    "vim.easymotion": true,
    "vim.surround": true,
    "vim.wrapscan": true,
    "vim.incsearch": true,
    "vim.ignorecase": true,
    "vim.smartcase": true,
    "vim.hlsearch": true,
    "vim.leader": ",",
    "vim.normalModeKeyBindingsNonRecursive": [{
        "before": ["j"],
        "after": ["g", "j"]
      },
      {
        "before": ["k"],
        "after": ["g", "k"]
      },
      {
        "before": ["<C-h>"],
        "after": ["<C-w>", "h"]
      },
      {
        "before": ["<C-l>"],
        "after": ["<C-w>", "l"]
      }
    ]

