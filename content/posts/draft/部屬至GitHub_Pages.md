---
title: "部屬至GitHub_Pages"
date: 2023-09-25T20:58:58+08:00
draft: true #草稿

tags: [Blog, Hugo]
categories: [Blog]
series: [動手建部落格]
series_weight: 6

featuredImage: "/Logo/hugo-logo-1200x628.png"
featuredImagePreview: ""

# hiddenFromHomePage: true # 主頁隱藏該文章
# hiddenFromSearch: true # 搜尋隱藏該文章
---
<!--more-->

## 上傳GitHub

## 建立gh-page分支

## 發布部落格專案

## 撰寫自動部屬YML腳本

建立`.github/workflows/gh-pages.yml`腳本檔案
就可以將上述的麻煩動作自動化完成

```yml
name: GitHub Pages

on:
  push:
    branches: # 設定分支
      - master
  pull_request:

jobs:
  deploy:
    runs-on: ubuntu-22.04
    concurrency:
      group: ${{ github.workflow }}-${{ github.ref }}
    steps:
      - uses: actions/checkout@v3
        with:
          submodules: true # Fetch Hugo themes (true OR recursive)
          fetch-depth: 0 # Fetch all history for .GitInfo and .Lastmod

      - name: Setup Hugo
        uses: peaceiris/actions-hugo@v2
        with:
          hugo-version: "latest"
          extended: true

      - name: Build
        run: hugo --gc --minify --cleanDestinationDir

      - name: Deploy
        uses: peaceiris/actions-gh-pages@v3
        with:
          github_token: ${{ secrets.GITHUB_TOKEN }}
          user_name: "github-actions[bot]"
          user_email: "github-actions[bot]@users.noreply.github.com"
          full_commit_message: ${{ github.event.head_commit.message }}
          allow_empty_commit: true
```
