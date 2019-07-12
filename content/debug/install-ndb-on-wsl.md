---
title: "在wsl中安装使用ndb(未完成)"
date: 2018-03-02T12:15:19+08:00
draft: false
tags: ["wsl", "nodejs", "debug"]
categories: ["nodejs"]
subtitle: ""
descriptions: ""
bigimg:
---


在wsl中安装使用ndb(未完成)


## env

- wsl: ubuntu16.04
- node: 11.14.0

## 安装

## step

### currency-api

通过 [awesome-nodejs](https://github.com/sindresorhus/awesome-nodejs) 找到 [ndb](https://github.com/GoogleChromeLabs/ndb)

看了一下，是google开发维护的，决定尝试

从 https://geshan.com.np/blog/2019/01/getting-started-with-debugging-nodejs-applications-with-ndb/ 

到

https://github.com/geshan/currency-api

这是一个很好的测试nodejs工程。

### ndb index.js 

```
ndb index.js 
```

正常情况下，应该出来ndb的窗口。但是，我这里，无任何反应 Nothing but a flashing cursor when I get ndb installed 。

https://github.com/GoogleChromeLabs/ndb/issues/154

到

https://github.com/GoogleChromeLabs/ndb/issues/33

到

https://github.com/GoogleChrome/puppeteer/issues/1837#issuecomment-508761569

```
sudo apt install chromium-browser
npm i puppeteer-core
```

找到

```
DESKTOP-APB1HCJ% which chromium-browser
/usr/bin/chromium-browser
```

但是，有一句话，是：

`Once I had that, I added the path to it in the puppeteer.launch function as the executablePath argument. So my code now looks like this:`

这里提到的 `puppeteer.launch function` 在哪里呀？

## 思考

https://github.com/GoogleChrome/puppeteer/issues/1837


## wsl 升级到 wsl2

看来只能 wsl 升级到 wsl2 


这是一个大的步子，所以，这个先放一边吧。


