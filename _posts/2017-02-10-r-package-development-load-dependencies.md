---
layout: post
title: '[R] Package development -  load dependencies'
date: 2017-02-10 11:59
comments: true
tags: [R, package-dev]
category: R
description: 在開發 R 套件的時候，如果想要在開發環境裡載入 package dependencies，原本需要手工的方式一個個加進去。後來發現 roxygen2 裡面有一個 function `load_pkg_dependencies()` 原本是用來測試套件的載入，這邊可作為我們一個簡單設置環境的工具
---

在開發 R 套件的時候，如果想要在開發環境裡載入 package dependencies，原本需要手工的方式一個個加進去。
後來發現 roxygen2 裡面有一個 function `load_pkg_dependencies()` 原本是用來測試套件的載入，這邊可作為我們一個簡單設置環境的工具：

```r
roxygen2:::load_pkg_dependencies()
```

看源碼可知道他是利用 `read_pkg_description()` 讀取套件路徑裡的 `DESCRIPTION` 檔案，載入 _Depends_, _Imports_。

```r
function (path)
{
    desc <- read_pkg_description(path)
    pkgs <- paste(c(desc$Depends, desc$Imports), collapse = ", ")
    if (pkgs == "")
        return()
    pkgs <- str_replace_all(pkgs, "\\(.*?\\)", "")
    pkgs <- str_split(pkgs, ",")[[1]]
    pkgs <- str_trim(pkgs)
    lapply(pkgs[pkgs != "R"], require, character.only = TRUE)
}
<environment: namespace:roxygen2>
```

所以執行了 `load_pkg_dependencies()` 後，我們就可以在其他套件載入的 ENV 中進行開發了。
