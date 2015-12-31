---
layout: post
title: "Jekyll+Github的一個簡單範例"
description: "Jekyll的基本範本"
category: jekyll
tags: github,blog
keywords: github,blog,jekyll,教學
date: 2015-12-29 01:08:20
---

> 所謂在GitHub上使用Jekyll，其實就是把適當的Jekyll的檔案架構和名稱放置到GitHub上而已，因為GitHub已經開啟了Jekyll的服務，所以只要架構與名稱合符了規定，就可以被靜態生成出blog文件，[點擊這裡](https://pages.github.com/versions/)可以知道Jekyll目前在GitHub上的版本是多少。

## 第零步、事前準備
* 到[Github](https://github.com)申請一組個人帳號

## 第一步、建立儲存庫
值得注意，命名儲存庫時有兩種方式:

1. 自訂專案名稱
2. 命名為`你的帳號.github.io`

這兩種結果分別會影響你專案網站的URL:

1.選擇**自訂專案名稱**，能夠讓你的專案完整放置在`你的帳號.github.io/你的專案名稱`下，但有一個規定是必須在`gh-pages`分支下才會生成網頁文件，當然一個GitHub帳號能擁有多個專案網站~

2.如果選擇***你的帳號.github.io***的方式的話，URL便是`你的帳號.github.io`，使用`master`分支便能夠正常建置。官網上快速建置的[教學](https://pages.github.com/)

在這一篇裡我會介紹**自訂專案名稱**的做法，為什麼呢？因為方法能套用在第2點上

###1.首先創建一個專案
按`new repository`
![new repository]({{ site.url }}{{ site.baseurl }}/image/2015-12-29-simple-jekyll/1.png)

###2.命名專案名稱
這裡填上`blog`
![repository name]({{ site.url }}{{ site.baseurl }}/image/2015-12-29-simple-jekyll/2.png)

然後會看到這個頁面
![repository name blog]({{ site.url }}{{ site.baseurl }}/image/2015-12-29-simple-jekyll/3.png)

##第二步、創建專案資料夾
1.在你的電腦上，創建一個目錄，名稱要與剛在github上創建的專案名稱相同  
2.進入目錄  
3.對目錄進行初始化  
4.切換成`gh-pages`分支，因為github規定只有在該分支下才會生成網頁文件  

```
$ mkdir ~/blog
$ cd ~/blog
$ git init
$ git checkout --orphan gh-pages
```
接下來的動作都需要在**gh-pages**分支下完成

##第三步、創建部落格結構
**請在`~/blog`的路經底下操作**

1.建立**_config.yml文件**`vim _config.yml`並加入以下內容

```
baseurl: /blog
```

目錄結構變成:  
![config]({{ site.url }}{{ site.baseurl }}/image/2015-12-29-simple-jekyll/4.png)

#　
2.建立**index.html文件** `vim index.html`並加入以下內容

<script src="https://gist.github.com/AnkMak/3ee1aa2ed86cb105a4ea.js?file=simple-jekyll-index.html"></script>

目錄結構變成:  
![index](http://ank.csie.io/blog/image/2015-12-29-simple-jekyll/5.png)

#　
3.建立**_layout資料夾**並在裡面建立**default.html文件**

```
$ mkdir _layout
$ touch _layout/default.html
```

編輯**default.html** `vim _layout/default.html`並加入以下內容
<script src="https://gist.github.com/AnkMak/3ee1aa2ed86cb105a4ea.js?file=simple-jekyll-default.html"></script>

目錄結構變成:  
![layout/default]({{ site.url }}{{ site.baseurl }}/image/2015-12-29-simple-jekyll/6.png)

#　
4.建立**_posts資料夾**並在裡面建立**2012-08-25-hello-world.html文件**

* 值得注意，文章一律放置於 **_posts** 資料夾底下，文章要按照 **年-月-日-名稱.副檔名** 來命名

```
$ mkdir _posts
$ touch _posts/2012-08-25-hello-world.html
```

編輯**2012-08-25-hello-world.html** `vim _posts/2012-08-25-hello-world.html`並加入以下內容

<script src="https://gist.github.com/AnkMak/3ee1aa2ed86cb105a4ea.js?file=2012-08-25-hello-world.html"></script>

目錄結構變成:  
![posts/html]({{ site.url }}{{ site.baseurl }}/image/2015-12-29-simple-jekyll/7.png)

基本上現在就有一個簡單的架構jekyll，只要上傳至github就大功告成。

##第六步、上傳發布

```
$ git remote add origin https://github.com/你的用戶名/blog.git
```

```
$ git add .
$ git commit -m "first post"
$ git push origin gh-pages
```
以後文章如果有新增或更改，只要執行上面的3行指令重新上傳發布即可

上傳成功後，再等個~~10~~幾分鐘，連上 http://**你的用戶名**.github.com/blog/ 就可以看到了，如沒有的話...再多按幾下重新整理

效果大概是這樣:

![main blog]({{ site.url }}{{ site.baseurl }}/image/2015-12-29-simple-jekyll/8.png)
#　
![first blog]({{ site.url }}{{ site.baseurl }}/image/2015-12-29-simple-jekyll/9.png)

嗯！沒錯！因為這是最陽春的架構所以介面非常的~~難看~~簡潔，不過如果你喜歡從無到有開始打造你的部落格，這種簡潔風格應該很適合你，不過由於太過~~醜陋~~簡潔，甚至連我都無法直視XDD，所以下一篇會教學如何從官方默認模版(Theme)開始，修改成自已理想的外觀

> 本文內容參考自[阮一峰-搭建一个免费的，无限流量的Blog----github Pages和Jekyll入门](http://www.ruanyifeng.com/blog/2012/08/blogging_with_jekyll.html)
