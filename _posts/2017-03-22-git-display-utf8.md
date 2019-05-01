---
layout: post
title: '[Git] 修正中文顯示亂碼'
date: 2017-03-22 15:41
comments: true
excerpt_separator: <!--more-->
tags: git
category: Git
---

在 Mac 使用 `git status` 或 `git ls-files` 時，若 Git 在顯示中文檔名出現類似下面的亂碼：

`"\321\203\321\201\321\202\320\260\320\275\320\276\320\262"`

這是因為 Git 預設只會印出 non-ASCII 字串，對於 utf8 的檔名或訊息，會用 _quoted octal notation_ 印出。

<!--more-->

> Git has always used octal utf8 display, and one way to show the actual name is by using printf in a bash shell.
>
> Since Git 1.7.10 introduced the support of unicode, this [wiki page](https://github.com/msysgit/msysgit/wiki/Git-for-Windows-Unicode-Support) mentions:
>
> By default, git will print non-ASCII file names in quoted octal notation, i.e. "\nnn\nnn...".

This can be disabled with:

```bash
git config [--global] core.quotepath off
```

## Reference

<http://stackoverflow.com/a/22828826/3744499>
