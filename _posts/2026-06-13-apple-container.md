---
layout: post
title: "Apple 开源 container：macOS 上运行 Linux 容器的终极方案"
date: 2026-06-13
categories: [开源项目, GitHub]
tags: [Apple, 容器, Linux, macOS, Swift, 虚拟化, 开源]
---

## 项目简介

2026 年 6 月，Apple 在 GitHub 上正式开源了 `container` 项目（[github.com/apple/container](https://github.com/apple/container)），这是一款专为 macOS 设计的 Linux 容器管理工具。该项目使用纯 Swift 编写，深度优化 Apple silicon 芯片，能够通过轻量级虚拟机（Lightweight VM）的方式在 Mac 上创建和运行 Linux 容器。

截至目前，该项目已获得超过 30,000 颗 Star，足见开发者社区对它的期待与认可。它的底层依赖 Apple 开源的 [`Containerization`](https://github.com/apple/containerization) Swift 包，提供了完整的容器运行时能力，并且完全兼容 OCI（Open Container Initiative）标准镜像格式。

## 核心功能特点

1. **原生 Apple silicon 优化**：专为 M 系列芯片设计，利用硬件虚拟化能力实现接近原生的容器性能，相比传统的 Docker for Mac 方案，资源占用更低、启动速度更快。

2. **轻量级虚拟机架构**：每个容器运行在独立的轻量级虚拟机中，提供了更好的安全隔离性，同时保持了容器的便捷性。

3. **OCI 兼容**：完全支持标准的 OCI 容器镜像，可以直接从 Docker Hub、GitHub Container Registry 等标准镜像仓库拉取和推送镜像。

4. **Swift 原生开发**：整个项目使用 Swift 编写，代码质量高、可读性强，对 Swift 开发者来说非常友好，便于贡献和二次开发。

5. **完善的命令行体验**：提供直观的 CLI 命令，支持容器的创建、启动、停止、管理等完整生命周期操作。

6. **Apache-2.0 开源许可**：宽松的开源协议，允许商业使用和二次开发。

## 安装和使用方法

### 系统要求

- **硬件**：必须是 Apple silicon Mac（M1/M2/M3/M4 系列）
- **操作系统**：仅支持 macOS 26（由于依赖新的虚拟化和网络特性）

### 安装步骤

**第一步**：从 [GitHub Releases 页面](https://github.com/apple/container/releases) 下载签名安装包。

**第二步**：双击安装包，按照提示完成安装（需要管理员密码，工具会安装到 `/usr/local` 目录）。

**第三步**：启动容器服务：

```bash
container system start
```

### 升级与卸载

升级到最新版本：

```bash
# 先停止服务
container system stop

# 升级到最新版
/usr/local/bin/update-container.sh

# 重新启动服务
container system start
```

降级到指定版本（例如 0.3.0）：

```bash
container system stop
/usr/local/bin/uninstall-container.sh -k  # 保留用户数据
/usr/local/bin/update-container.sh -v 0.3.0
container system start
```

完全卸载：

```bash
/usr/local/bin/uninstall-container.sh -d  # 删除工具和用户数据
```

### 基本使用

启动服务后，你可以像使用其他容器工具一样管理 Linux 容器。项目还提供了完整的[命令参考文档](https://github.com/apple/container/blob/main/docs)和 [API 文档](https://apple.github.io/container/documentation/)。

## 为什么值得关注

**对 macOS 开发者的意义**：长久以来，macOS 用户运行 Linux 容器主要依赖 Docker Desktop，但 Docker Desktop 存在资源占用高、需要付费（商业用途）等问题。Apple 官方推出的 `container` 工具提供了一个原生、免费且高性能的替代方案。

**Apple 正式拥抱开源容器生态**：这是 Apple 首次以官方身份深度参与 Linux 容器生态建设。从底层的 `Containerization` 框架到上层的 `container` CLI 工具，Apple 展示了对开发者工具链的重视。

**Swift 在系统工具领域的突破**：该项目证明了 Swift 不仅适用于 iOS/macOS 应用开发，在系统级工具和基础设施领域同样具有强大的竞争力。

**活跃的社区和持续迭代**：30K+ Star、800+ Fork，加上 Apple 官方团队的持续维护，项目发展势头强劲。最新 1.0.0 版本的发布标志着项目进入了稳定阶段。

## 总结

Apple `container` 项目的开源是 2026 年开发者工具领域最重要的事件之一。它为 macOS 用户提供了一个原生、高效、免费的 Linux 容器运行方案，打破了 Docker Desktop 长期以来的垄断地位。如果你是一名使用 Apple silicon Mac 的开发者，这款工具绝对值得你第一时间尝试。随着社区的不断壮大和功能的持续完善，`container` 有望成为 macOS 上运行 Linux 容器的新标准。
