---
title: 1Panel Docker 编排模板管理
description: 介绍在 1Panel 中创建、使用、导入和导出 Docker Compose 编排模板的方法。
keywords: 1Panel Docker,Docker Compose,编排模板,Compose 模板,容器编排
schema_type: TechArticle
---

# 编排模板

!!! note ""
    编排模板用于保存可复用的 Docker Compose 内容，在创建编排时快速填充。入口为 **容器 -> 编排模板**，社区版、专业版和企业版均可使用，前提是当前节点已经安装并启动 Docker。

## 1 创建模板

!!! note ""
    点击 **创建**，填写模板名称、描述和 Compose 内容后保存。模板只保存配置文本，不会自动创建容器、网络或存储卷。

<div class="browser-mockup" markdown>

![创建编排模板](../../img/containers/compose_template_create.png)

</div>

!!! warning "模板中的敏感信息"
    不建议把数据库密码、访问令牌或私钥直接写入模板。优先使用环境变量文件、Docker Secret 或其他受控凭证方式，并确认导出文件不包含敏感数据。

## 2 使用和管理

- 在模板列表点击名称可查看内容，点击 **编辑** 可修改名称、描述和 Compose 配置。
- 创建编排时，可从已有模板载入内容，再根据目标节点修改目录、端口、网络和环境变量。
- 删除模板不会删除已由该模板创建的编排。

## 3 导入和导出

模板支持 JSON 导入和批量导出。导入外部模板后，应检查镜像来源、特权模式、主机目录挂载、端口和启动命令，再用于生产环境。模板中的主机路径和网络名称不一定在其他节点存在，跨节点使用时必须重新核对。
