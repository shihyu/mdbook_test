## mdBook的安裝與初次執行

### 下載 
將此執行檔複製到**PATH**指到的路徑內即可。

```
https://github.com/rust-lang/mdBook/releases
```

### 初次執行

在要存放書本的資料夾內執行指令`mdbook init`並回應內容：

### 啟始環境

```
mdbook init

Do you want a .gitignore to be created? (y/n)
y
What title would you like to give the book?
我的第一本網頁書
2020-04-23 18:04:31 [INFO] (mdbook::book::init): Creating a new book with stub content

All done, no errors...
```



要產生樣式檔則使用`mdbook init --theme`，/src會多出theme子目錄

mdBook自動產生書本的原始架構與相關檔案。目錄結構如下：

```sh
存放書本的資料夾/
├── book
└── src
    ├── chapter_1.md
    └── SUMMARY.md
```

### 組建書本

子目錄與檔案都產生後以下列指令執行第一次組建：

```
mdbook build
```

一切正常的話表示 book 資料夾內已有需要的網頁檔案了，再來啟動測試用的網頁伺服器：

```
mdbook serve
```

最後用瀏覽器瀏覽 `http://localhost:3000`，一切無誤的話會看到預設的網頁內容。



### 書本設定

開始說明mdBook電子書的組織方法。

電子書的基本設定資料是存放在根目錄的book.toml檔案。

▼ 範例：

```sh
[book]
authors = ["jdev.tw]
language = "zh"
multilingual = false
src = "src"
title = "用Markdown寫電子書：使用mdBook超簡單"
```

### 控制主文件：SUMMARY.md

SUMMARY.md是整本書的主要控制文件，左側的章節超連結即由SUMMARY.md組成。它由三大部份組成，每個部份可有多個項目：

```sh
* [第一章](第一章.md)
    * [第一節](第一章第一節.md)
    * [第二節](第一章第二節.md)
    * ...
* [第二章](第二章.md)
    * [第一節](第二章第一節.md)
    * [第二節](第二章第二節.md)    
    * ...
* ...
```

```sh
# 用Markdown寫書：使用mdBook超簡單

[修改歷程](./README.md)

----

- [mdBook是什麼？](./chapter_1.md)
- [mdBook的安裝與初次執行](./chapter_2.md)
    - [下載](./chapter_2.1.md)
    - [初次執行](./chapter_2.2.md)
- [書本設定：book.toml](./chapter_3.md)
- [控制主文件：SUMMARY.md](./chapter_4.md)
- [打包與部署](./chapter_5.md)

----

[宣告事項](./footer.md)
```



