## 1 安装驱动

!!! note ""
    针对 NVIDIA 显卡，用户可以在 https://www.nvidia.com/en-us/drivers/ 网站查找对应显卡型号支持的驱动版本，并进行下载安装。

    例如下载到的文件为 `NVIDIA-Linux-x86_64-570.86.15.run`，将文件上传到 1Panel 服务器后，可以在命令行执行以下命令进行安装：

    ```bash
    chmod +x NVIDIA-Linux-x86_64-570.86.15.run
    ./NVIDIA-Linux-x86_64-570.86.15.run
    ```

    > 执行命令后根据弹出的提示框信息进行安装即可。
    `nvidia-smi` 命令会随 NVIDIA 驱动一同安装，1Panel 将使用 `nvidia-smi` 命令获取显卡相关信息。

## 2 查看显卡信息

!!! note ""
    在 GPU 监控页面，可以查看到驱动版本，显卡型号以及显卡的使用率、温度、功耗等基础指标，还可以查看到目前正在使用显卡的进程信息。

![img.png](../../img/ai/gpu_monitor.png)

## 3 配置应用商店应用（容器）使用 GPU

!!! note ""
    显卡驱动安装完成后，还需要根据 [NVIDIA 官网指引](https://docs.nvidia.com/datacenter/cloud-native/container-toolkit/latest/install-guide.html)安装容器支持工具，才可以在应用商店应用或其他容器中使用 GPU 能力。

> 在应用商店安装应用时，勾选高级设置中的 `GPU 加速` 即可让该应用获得 GPU 支持。

![img.png](../../img/ai/gpu_acceleration.png)
