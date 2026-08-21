---
title: 1Panel GPU 监控使用说明
description: 介绍在 1Panel 中查看 GPU 当前状态和历史记录，以及为容器配置 GPU 资源的方法。
keywords: 1Panel GPU 监控,GPU 状态,GPU 历史记录,Docker GPU,NVIDIA GPU
schema_type: TechArticle
---

# GPU 监控

!!! note "功能说明"
    GPU 监控用于查看当前节点的显卡信息、实时指标、占用进程和历史趋势。入口为左侧菜单 **AI -> GPU 监控**，页面包含 **当前状态** 和 **历史记录**。

    社区版、专业版和企业版均可使用。多节点环境中，页面展示的是当前所选节点的数据。

## 1 使用前提
!!! warning "注意"
    1Panel 通过主机上已安装的显卡管理工具读取数据。以 NVIDIA GPU 为例，需要先安装与显卡和操作系统匹配的驱动，并确保在服务器终端执行 `nvidia-smi` 能正常返回信息。

    需要在容器中使用 NVIDIA GPU 时，还应按照 [NVIDIA Container Toolkit 安装文档](https://docs.nvidia.com/datacenter/cloud-native/container-toolkit/latest/install-guide.html)完成容器运行时配置。

!!! warning "驱动安装"
    显卡驱动与内核、操作系统和硬件型号相关。升级内核或驱动可能影响现有 GPU 工作负载，生产环境应先确认兼容性并安排维护窗口。

## 2 当前状态

!!! note ""
    当前状态展示驱动版本、显卡型号、利用率、显存、温度、功耗等指标，并列出正在使用 GPU 的进程。实际可见字段取决于显卡类型、驱动和管理工具返回的数据。

![GPU 当前状态](../../img/ai/gpu_monitor.png)
{: .original}

如果页面无数据，请先在终端验证显卡管理命令，再检查驱动状态和 1Panel 服务日志。

## 3 历史记录

!!! note ""
    历史记录用于按时间范围查看 GPU 指标趋势。只有已被采集并保存的数据才能形成历史曲线；更换节点时，应重新确认当前节点和查询时间范围。

## 4 在容器中使用 GPU

驱动和容器工具配置完成后，可在支持 GPU 的应用或容器配置中启用 **GPU 加速**，并选择需要分配的设备。容器启动后，可通过容器日志、主机 GPU 进程和利用率确认设备是否生效。

![应用 GPU 加速](../../img/ai/gpu_acceleration.png)
{: .original}
