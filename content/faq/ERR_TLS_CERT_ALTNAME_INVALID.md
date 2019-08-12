---
date: 2019-01-08T21:07:13+01:00
title: "ERR_TLS_CERT_ALTNAME_INVALID"
weight: 10
keywords:
- faq
- nodejs
description : "nodejs安装包时出现ERR_TLS_CERT_ALTNAME_INVALID"
---


如果出现了`ERR_TLS_CERT_ALTNAME_INVALID`错误，具体如下：


```
ubuntu@utuntu:~/chat/chat-admin-server$ cnpm init egg --type=simple
npm ERR! code ERR_TLS_CERT_ALTNAME_INVALID
npm ERR! errno ERR_TLS_CERT_ALTNAME_INVALID
npm ERR! request to https://registry.npmjs.org/create-egg failed, reason: Hostname/IP does not match certificate's altnames: Host: registry.npmjs.org. is not in the cert's altnames: DNS:a.sni.fastly.net, DNS:a.sni.global-ssl.fastly.net

npm ERR! A complete log of this run can be found in:
npm ERR!     /home/ubuntu/.npm/_logs/2019-08-12T06_32_33_746Z-debug.log
Install for create-egg@latest failed with code 1
ubuntu@utuntu:~/chat/chat-admin-server$ 
```

解决方式：

1. `npm config set strict-ssl false`。参考[这里](https://blog.csdn.net/Lianxingjie_1024/article/details/80275618)
2. 设置registry. 运行`npm config set registry "http://registry.npmjs.org"`。参考[这里](https://stackoverflow.com/questions/52129097/npm-err-code-err-tls-cert-altname-invalid)
3. 修改 `/etc/hosts` 中的 `registry.npmjs.org` 的配置。比如，我是注释掉 `#151.101.16.162 registry.npmjs.org`。

