---
title: 1Panel SSL 证书申请方法
description: 介绍使用 DNS 账户、手动 DNS 解析或 HTTP 验证方式在 1Panel 中申请 SSL 证书的方法。
keywords: 1Panel 申请证书,SSL 证书申请,ACME,DNS 验证,HTTP 验证,HTTPS
schema_type: TechArticle
---

## 1 前置条件

!!! note ""

    - 已经创建 ACME 账户
    - 如果是 DNS 验证模式，需要提前准备 DNS 账号

<div class="browser-mockup" markdown>

![img.png](../../img/websites/certificate_create.png)

</div>

## 2 DNS 账号模式申请证书

!!! note ""

    1. 选择 ACME 账号
    2. 选择 DNS 账号
    3. 选择是否自动续签
    4. 点击确认

## 3 手动解析模式申请证书

!!! note ""

    1. 选择 ACME 账号
    2. 点击确认
    3. 等待返回解析内容，然后在 DNS 供应商解析处添加解析内容
    4. 点击确认

## 4 HTTP 模式申请证书

!!! note ""

    1. 选择 ACME 账号
    2. 选择是否自动续签
    3. 点击确认
