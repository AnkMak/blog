---
layout: post
title: "首次用Github Pages創建Blog--使用Jekyll"
description: "使用Jekyll"
category: jekyll
tags: [blog]
keywords: github,blog,jekyll,markdown,教學
date: 2015-12-28 06:25:35
---

####開場廢話
> 首先，必須說明一下使用Jekyll真的不是一件簡單的事情，我花了好幾天的時間也才只有雛型而已(人笨也有關係)  不過Jekyll能讓我照自已喜好去修改Blog的**所有細節**，充分展現hacker精神  我的首個部落格就此誕生，當然這篇是我的第一篇文章哈哈。

####我的願景
> 我盡可能把我所會的和折騰過的東西，以最簡單易懂的方式去寫**教學文章**，希望有人能從這裡得到一些幫忙，省去一些我所走過的冤枉路 。如有錯誤之處，歡迎來信指點。

******

##我理想的Blog應該具備什麼?
* markdown語法
* 程式碼顯示美觀
* 簡潔(無廣告)
* 離線撰寫
* 可用編譯器(如:vim)寫文章
* 可修改所有細節
* 可靠的備份與長久保存
* 高移植性

如果你有跟我一樣的想法，那就不要嫌麻煩，跟著我做就對了！  
順便一提，你目前所看到的這個部落格就是使用**GitHub+Jekyll**所搭建的


##為何選擇GitHub?
![github]({{ site.url }}{{ site.baseurl }}/image/2015-12-28-my-first-blog/github.png)

如果沒有用過GitHub的朋友可以到[官網](https://github.com)了解一下~它是一個可以方便管理和備份程式碼(or其他文件)的好地方~！尤其對於進行程式開發的人來說十分建議學習Git和GitHub的使用方法。

GitHub提供了一個[github pages](https://pages.github.com/)的功能，能讓使用者以Websites的方式去呈現自己的東西，而不是冷冰冰的程式碼。

使用GitHub有一個好處就是不太需要擔心倒站或是資料掉失，GitHub是全球性的服務商，而且它本來就是以管理資料起家的:D
  

##為何選擇Jekyll?
![jeykll]({{ site.url }}{{ site.baseurl }}/image/2015-12-28-my-first-blog/jekyll-logo-light-solid.png)

Jekyll的官網：[英文](https://jekyllrb.com/)和[簡中](http://jekyllcn.com/)

它是一個靜態網頁的生成工具，是GitHub Pages所推薦使用的，它與GitHub搭配後，能擁有我上述所列舉的所有優點，而且它還有一項很吸引我的說法，就是**像駭客一樣寫Blog**，使用vim寫文章更乎合我的簡潔主義。

Q.如果不喜歡Jekyll怎麼辦？  
A.你可以試試其他的如：Octopress、ghost、Hexo。或者是自己撰寫網站=）


##使用後的一些成果
其實主要是使用它的markdown語法，因為能讓我更專心在寫作上，不需要考慮到html的語法。  
尤其是我未來會想把一些技術文章寫下來的時候，必定會大量寫下程式碼。  
所以希望可以用這種簡單的方法寫下，然後由Jekyll自動配色  
如輸入這種格式後：

```
	```c
	#include<stdio.h>  
	int main(){  
		int i;  
		printf("hello world\n");  
		return 0;  
	}
	```
```
會自動配色成:

```c
	#include<stdio.h>  
	int main(){  
		int i;  
		printf("hello world\n");  
		return 0;  
	}
```
******
以下測試程式碼

`cpp`

```cpp
#include <iostream>

int main(int argc, char *argv[]) {

	/* An annoying "Hello World" example */
	for (auto i = 0; i < 0xFFFF; i++)
		cout << "Hello, World!" << endl;

	char c = '\n';
	unordered_map <string, vector<string> > m;
	m["key"] = "\\\\"; // this is an error

	return -2e3 + 12l;
}
```

`java`

```java
/**
 * @author John Smith <john.smith@example.com>
 */
package l2f.gameserver.model;

public abstract class L2Char extends L2Object {
	public static final Short ERROR = 0x0001;

	public void moveTo(int x, int y, int z) {
		_ai = null;
		log("Should not be called");
		if (1 > 5) { // wtf!?
			return;
		}
	}
}
```

`bash`

```bash
#!/bin/bash

###### CONFIG
ACCEPTED_HOSTS="/root/.hag_accepted.conf"
BE_VERBOSE=false

if [ "$UID" -ne 0 ]
then
echo "Superuser rights required"
exit 2
fi

genApacheConf(){
	echo -e "# Host ${HOME_DIR}$1/$2 :"
}
```

`python`

```python
@requires_authorization
def somefunc(param1='', param2=0):
	r'''A docstring'''
	if param1 > param2: # interesting
		print 'Gre\'ater'
	return (param2 - param1 + 1) or None

class SomeClass:
	pass

>>> message = '''interpreter
... prompt'''
```

> 如果你對markdown語法有興趣，可以點[這裡](https://gist.githubusercontent.com/AnkMak/0a3b82c54df5781bc1b7/raw/262e3796bc68d6e10a2bb2718109b0ed4bc446c7/2015-12-28-my-first-blog.md)觀看本篇的markdown

這一篇主要是想要引起大家想用github+jekyll來打造Blog的動力，在下一篇我會詳細說明如何使用Jekyll。
