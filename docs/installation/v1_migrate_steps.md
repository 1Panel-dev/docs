
!!! warning "注意"

    由于 V2 版本较 V1 版本有比较大的架构变动，目前不支持从 V1 版本直接在线升级至 V2 版本。

    为确保迁移顺利、安全，请务必在执行前仔细阅读本文档的[升级说明](v1_migrate.md)。

## 1. 安装 1panel-migrator

### 1.1 安装包获取

请访问 Gitee 发布页，手动下载适用于您服务器架构的安装包，并将其放置到 `/tmp` 目录：

> 🔗 https://gitee.com/fit2cloud-feizhiyun/1panel-migrator/releases/

每个版本会提供以下架构的安装包（文件名示例）：

- `1panel-migrator-linux-amd64`
- `1panel-migrator-linux-arm64`
- `1panel-migrator-linux-arm`
- `1panel-migrator-linux-ppc64le`
- `1panel-migrator-linux-s390x`

### 1.2 安装步骤（以 amd64 架构为例）

```bash
# 1. 进入临时目录
cd /tmp

# 2. 添加执行权限
chmod +x 1panel-migrator-linux-amd64

# 3. 移动至系统 PATH 中并重命名
mv 1panel-migrator-linux-amd64 /usr/local/bin/1panel-migrator
```

## 2. 升级说明

升级过程分为两步：**升级服务** 和 **升级网站**。

> 请务必先完成服务升级，再进行网站升级。

服务升级分为两种角色：

- **主节点**：包含 `1panel-core` 和 `1panel-agent` 两个服务，开放对外端口，支持通过浏览器访问；
- **从节点**：仅包含 `1panel-agent` 服务，不开放对外端口，需要通过主节点的 ``节点管理`` 页面添加并管理。

### 2.1 升级为主节点

#### 2.1.1 升级服务

```bash
1panel-migrator upgrade core
```

#### 2.1.2 升级网站

> 注意：请确保 V2 服务启动成功后再执行该命令。

```bash
1panel-migrator upgrade website
```

### 2.2 升级为从节点

#### 2.2.1 升级服务

```bash
1panel-migrator upgrade agent
```

#### 2.2.2 在主节点添加从节点

前往主节点 **节点管理** 页面，添加该从节点。系统会自动识别并处理 V1 的历史数据。

#### 2.2.3 升级网站

> 注意：添加完成后，请在从节点服务器上执行网站升级命令。

```bash
1panel-migrator upgrade website
```

## 3. 回滚说明

!!! note ""

    当升级过程出现问题时，可以使用回滚操作恢复到之前的 1Panel V1 版本。

回滚过程也分为两步：**回滚 1Panel 服务** 和 **回滚网站**。

!!! warning "注意"

    请务必先完成服务的回滚，再进行网站回滚。

### 3.1 服务回滚

不区分主从节点，直接在目标服务器执行以下命令：

```bash
1panel-migrator rollback service
```

### 3.2 网站回滚

同样在目标服务器执行以下命令：

> 注意：请确保 V1 服务启动成功后再执行该命令。

```bash
1panel-migrator rollback website
```