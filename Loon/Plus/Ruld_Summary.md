# 什么是规则

规则，决定了当一个请求进来时，如何通过匹配类型进行匹配，以及如何选用对应的策略

## 规则组成

![#f03c15](https://placehold.it/15/f03c15/000000?text=+) 规则分为三个部分

![#f03c15](https://placehold.it/15/f03c15/000000?text=+) 匹配类型 ，匹配关键字，策略名称

![#f03c15](https://placehold.it/15/f03c15/000000?text=+) 如： `DOMAIN-SUFFIX,twimg.com,PROXY`

## 匹配类型

匹配名称|匹配类型|说明
-|-|-
基于域名后缀|DOMAIN-SUFFIX|无
基于域名完整匹配|DOMAIN|无
基于域名关键字|DOMAIN-KEYWORD|无
基于用户代理串|USER-AGENT|根据 Http 的 user-agent 值来进行匹配，支持带有 \* , ? 的通配符匹配
基于URL正则|URL-REGEX|
基于请求IP范围|IP-CIDR|通常用作局域网匹配
基于IP定为国家编码|GEOIP|CN中国
兜底匹配|FINAL|如果没有匹配的规则，默认使用的匹配

## 实例示范理解规则的作用

![#f03c15](https://placehold.it/15/f03c15/000000?text=+) 如下图中的用户发起对 www.google.com 的一个访问请求中

![image](https://raw.githubusercontent.com/chiupam/tutorial-image/master/Loon/Plus/Ruld_Example.jpg)

![#f03c15](https://placehold.it/15/f03c15/000000?text=+) `策略` 栏中， `Proxy` 代表策略， `[隧道]香港01#GZCM` 代表代理节点

![#f03c15](https://placehold.it/15/f03c15/000000?text=+) `规则` 栏中，`DOMAIN-KEYWORD` 代表匹配类型， `google` 代表匹配关键字， `Proxy` 代表策略

即代表，用户发起对 `www.google.com` 的一个访问请求，被匹配类型为 `DOMAIN-KEYWORD` 域名关键字匹配，匹配关键字为 `google` ，使用 `Proxy` 策略，策略下代理节点是 `[隧道]香港01#GZCM`

# 参考

- [Loon 不完全教程 —— 规则导入](https://www.notion.so/2-967c1a07462c43ab88906162bec475a4)