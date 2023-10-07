---
title: "部屬至GitHub Pages"
date: 2023-09-25T20:58:58+08:00
draft: false #草稿

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

## GitHub Page

GHitHub在特定限制下有提供:

* 免費的靜態網站服務
* `gh-pages`分支的檔案自動部屬至GitHub Page的靜態網站
* 免費SSH憑證(https)
* 預設網址: `https://<帳戶名稱>.github.io/<專案名稱>`(也可以改用自行購買的網址)

{{< admonition type=tip title="預設網址補充" open=false >}}
如果專案名稱與`<帳戶名稱>.github.io`相同
該專案的網址就會是`https://<帳戶名稱>.github.io`，後面不需要帶專案名稱`/<專案名稱>`
所以自己最主要的網站可以這樣設定專案名稱
{{< /admonition >}}

免費的[限制](https://docs.github.com/zh/pages/getting-started-with-github-pages/about-github-pages#github-pages-%E4%BD%BF%E7%94%A8%E9%99%90%E5%88%B6):

* 類型: 只能部屬靜態的專案(EX:HTML、React、Angular、Vue.js...等)，並沒有後端
* 空間: 每個儲存庫、站台最大1GB
* 流量: 每個月100GB
* 部屬次數: 每小時10次
* 部屬時間: 單次最久10分鐘

## 為何需要GitHub Action

這些是我們將專案發佈到`GitHub Page`的步驟

1. 發佈HUGO成靜態檔案
2. 靜態檔案上傳到`gh-pages`分支(開發過程中檔案誤上傳)

這些步驟其實也可以手動來，只是會很麻煩
因為光兩個分支內，一個要是開發的HUGO專案，一個是發佈出來的靜態檔案
內容完全不一樣，要注意上傳項目就會變得很麻煩
另外也有可能本機開發環境有異動導致發佈異常

所以因為以上種種，這時候我們就需要 **自動化!!!**
讓他每次執行都有一致性的信心

## 自動部屬運作流程

好來~ 那我們先用[時序圖]^(Sequence Diagram)把部屬流程畫出來就一目了然了!

{{< mermaid >}}sequenceDiagram
actor User
participant GitHub
participant GitHub Action
participant GitHub Pages

User->>User:編寫HUGO程式碼
User->>GitHub: Push程式碼到GitHub

GitHub->>GitHub Action: 觸發GitHub Actions工作流程
activate GitHub Action
GitHub Action->>GitHub:取得最新版程式碼
GitHub Action->>GitHub Action:虛擬機安裝HUGO程式
GitHub Action->>GitHub Action:發佈Hugo靜態檔案
GitHub Action->>GitHub:靜態檔案Push到gh-pages分支
deactivate GitHub Action

GitHub Pages-->>GitHub:偵測gh-pages分支內容

note over User,GitHub Pages:網站部屬完成
{{< /mermaid >}}

## 撰寫自動部屬YML腳本

再來~  我們把上方時序圖的動作寫成腳本試試看
建立`/.github/workflows/gh-pages.yml`腳本檔案

```yml
name: GitHub Pages

# 觸發執行腳本條件
on:
  push:
    branches: # 異動的分支
      - master
  workflow_dispatch: # 手動觸發

jobs:
  deploy:
    runs-on: ubuntu-22.04 #虛擬機的作業系統與版本
    steps:
      # 取得專案程式碼
      - name: checkout
        uses: actions/checkout@v3
        with:
          submodules: true # Fetch Hugo themes (true OR recursive)
          fetch-depth: 0 # Fetch all history for .GitInfo and .Lastmod

      # 建立HUGO環境
      - name: Setup Hugo
        uses: peaceiris/actions-hugo@v2
        with:
          hugo-version: "latest"
          extended: true # 擴展版

      # 發佈靜態檔案
      - name: Build
        run: hugo --gc --minify --cleanDestinationDir --enableGitInfo --forceSyncStatic

      # 部屬到gh-pages分支
      - name: Deploy
        uses: peaceiris/actions-gh-pages@v3
        with:
          github_token: ${{ secrets.GITHUB_TOKEN }}
          user_name: "github-actions[bot]" # 上傳人員
          user_email: "github-actions[bot]@users.noreply.github.com" # 上傳EMail
          full_commit_message: ${{ github.event.head_commit.message }} # 上傳訊息
          allow_empty_commit: true # 允許空上傳
```

### 觸發執行腳本條件

上列範例的寫法
在指定分支有異動或是手動觸發腳本時
就會執行`jobs:`內動作

### 建立虛擬機

可以設定為最新版本，或是指定版本
```yml
runs-on: ubuntu-latest # 最新版
runs-on: ubuntu-22.04
```

### 取得專案程式碼

由HitHub Action官方提供的[腳本](https://github.com/actions/checkout)
可以將最新版專案程式碼簽出至虛擬機上

### 建立HUGO環境

開源的[腳本](https://github.com/peaceiris/actions-hugo)
方便我們建立相關的HUGO作業環境

### 發佈靜態檔案

* `--gc` 建置後刪除快取檔案
* `--minify` 最小化檔案，壓縮HTML、CSS、JavaScrip...等文件
* `--cleanDestinationDir` 發佈前先清除目錄內檔案
* `--enableGitInfo` 將 Git 修訂版、日期、作者和代碼所有者資訊新增至頁面
* `--forceSyncStatic` 強制複製已存在的靜態文件，避免遺漏異動

### 部屬到gh-pages分支

將靜態檔案上傳到`gh-pages`分支後，便會被GitHub Page自動偵測內容發佈為網站
