---
title: 1Panel WAF 黑白名单管理
description: 介绍在 1Panel WAF 中配置 IP、URL、User-Agent 黑白名单和可复用 IP 组的方法。
keywords: 1Panel WAF,WAF 黑白名单,IP 黑名单,URL 白名单,User-Agent,IP 组
schema_type: TechArticle
---

# WAF 黑白名单

!!! info "版本与权限"
    黑白名单支持社区版、专业版和企业版。企业版普通用户需要 WAF 查看权限；创建、编辑、删除、导入和应用规则需要 WAF 管理权限。

!!! note ""
    进入 **WAF -> 黑白名单**，可以配置全局 IP、URL、User-Agent 黑白名单，并维护可复用的 IP 组。规则作用于已启用 WAF 的网站。

## 1 IP

IP 规则支持黑名单和白名单，可以填写 IPv4、IPv6、IP 段或已创建的 IP 组。黑名单用于拒绝匹配的来源，白名单允许匹配的来源跳过后续 WAF 规则。

## 2 URL

URL 黑名单用于阻止匹配的请求路径，URL 白名单用于让匹配路径跳过后续 WAF 规则。规则采用页面提示的匹配方式，添加前应确认是否需要包含路径前缀或完整路径。

## 3 User-Agent

User-Agent 黑名单和白名单根据请求头中的 User-Agent 内容进行匹配，可用于限制已知扫描器或放行可信客户端。User-Agent 可以被客户端伪造，不能单独作为身份认证依据。

## 4 IP 组

IP 组用于集中维护一组 IPv4、IPv6 或 CIDR 地址，并在 IP 黑白名单中重复引用。页面支持创建、编辑、删除、导入和导出 IP 组；每行填写一个 IP 或 IP 段。

!!! warning "规则范围"
    过宽的黑名单可能阻断正常业务，过宽的白名单会降低防护范围。修改后应验证登录、上传、API 和回调等关键路径；专业版和企业版还可以结合拦截记录确认规则效果。
