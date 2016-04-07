plurk-makerserver: 透過IFTTT可以把Twitter 轉到 Plurk的伺服器 
==============

 [![GoDoc](https://godoc.org/github.com/kkdai/plurk-makerserver?status.svg)](https://godoc.org/github.com/kkdai/plurk-makerserver)  [![Build Status](https://travis-ci.org/kkdai/plurk-makerserver.svg?branch=master)](https://travis-ci.org/kkdai/plurk-makerserver)

![](http://ext.pimg.tw/derek2009/4a0e884470b0d.jpg)

"Plurk Maker Server" 一個 Web Service 可以幫助你使用 [IFTTT](https://ifttt.com) 來將你的 Twitter 轉發到 Plurk


如何讓你的 Twitter 轉發到 Plurk ?
=============

### 首先申請一個 Plurk APP

1. 先到這個地方，申請你的 [App](http://www.plurk.com/PlurkApp/)．
	- **類別**:  手機或應用程式
	- 其他相關資料填寫可以參考[這篇文章](http://zh.blog.plurk.com/archives/1121)
2. 點下測試工具
3. 取得以下四個數值
	- App key
	- App secret
	- Token
	- Token secret

在Plurk  App就算是完成，接下來要到 [IFTTT](https://ifttt.com)設定

### 再來架設你自己的Plurk Maker Server

按下下面的按鈕

[![Deploy](https://www.herokucdn.com/deploy/button.svg)](https://heroku.com/deploy)

記住你的 Server URL 等等要使用

#### 在 IFTTT Maker 上的設定

1. 接下來到 [IFTTT Maker](https://ifttt.com/maker) 申請一個帳號．

2. 建立一個 IFTTT Receipt ， 前端用 Twitter 接起來，後面接到剛剛建立的 Maker ．

3. Maker 設定頁面上，資料依照以下的格式來填:

- URL :  你剛剛的 Server URL
- Method: POST
- Content Type: application/json
- Body: 依照以以下的修改，貼上去

```
// 記得將以下資料換成剛剛在 Plurk 拿到的資料
// {{App key}}      -> App key
// {{App secret}}   -> App secret
// {{Token}}        -> Token
// {{Token secret}} -> Token secret

{"ConsumerToken":"{{App key}}", "ConsumerSecret":"{{App secret}}", "AccessToken": "{{Token}}","AccessSecret":"{{Token secret}}", "Msg": "{{Text}}"}
``` 

這樣就可以了....


Inspired By
=============

- [Github: Plurk on Go](https://github.com/clsung/plurgo)
- [簡單上手撰寫你的噗浪機器人](http://zh.blog.plurk.com/archives/1121)

Project52
---------------

It is one of my [project 52](https://github.com/kkdai/project52).


License
---------------

Licensed under the Apache License, Version 2.0 (the "License");
you may not use this file except in compliance with the License.
You may obtain a copy of the License at

http://www.apache.org/licenses/LICENSE-2.0

Unless required by applicable law or agreed to in writing, software
distributed under the License is distributed on an "AS IS" BASIS,
WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
See the License for the specific language governing permissions and
limitations under the License.

