---
title: 1Panel 上传 SSL 证书
description: 介绍将已有 PEM 格式 SSL 证书和私钥上传到 1Panel，并用于网站 HTTPS 配置的方法。
keywords: 1Panel 上传证书,SSL 证书,PEM 证书,HTTPS 配置,SSL 私钥
schema_type: TechArticle
---

# 上传证书

!!! note ""

    点击证书列表上方的【上传证书】按钮，用户可以将已有的 SSL 证书上传至 1Panel 中，用于网站的 HTTPS 访问。

![img.png](../../img/websites/certificate_upload.png)
{: .browser-mockup}

!!! note ""

    上传证书时，用户需要提供 PEM 格式的证书和私钥，两者必须互相匹配。上传后应检查证书域名、签发机构和有效期，再用于网站 HTTPS 配置。

!!! warning "私钥安全"
    私钥属于敏感凭证，应仅通过安全渠道保存和传输。
