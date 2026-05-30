[README_EN.md](https://github.com/user-attachments/files/28418900/README_EN.md)
# msc-manager-modelscope-desk-
 ModelScope SDK本地桌面门户 🏔️魔搭方寸间# 🏔️ 魔搭方寸间

> **第三方声明**：本项目是 ModelScope SDK 的第三方桌面封装工具，**非阿里达摩院/魔搭官方项目**。
> 仅对原生 SDK 做调用封装与流程简化，依赖官方 `modelscope` 包，不修改 SDK 源码。
> 使用请遵守 [ModelScope Apache 2.0 协议](https://github.com/modelscope/modelscope)。

ModelScope SDK 本地桌面门户。搜尽天下模型，方寸之间。

## 功能

| 功能 | 说明 | 状态 |
|------|------|------|
| **主页 Dashboard** | SDK 全能力图谱 · 15 个功能模块一览 | ✅ |
| **模型发现** | 搜索直跳官网，不截流 | ✅ 官网跳转 |
| **我的模型** | 本地已下载模型管理 | ✅ 本地 |
| **下载管理** | 实时进度 + 排队 + 完成列表 | ✅ 本地 |
| **设置** | 环境检测 + 配置编辑（路径、端口） | ✅ 本地 |
| **数据集/创空间/推理等** | 一键跳转官网对应页面 | ✅ 官网跳转 |

## 使用

### Mac

```bash
# 方式 1：双击启动（推荐）
解压 → 双击「启动魔搭方寸间.command」

# 方式 2：终端启动
cd msc_manager && bash start.sh
```

### Windows

```bash
解压 → 双击 start.bat
```

首次运行自动检测 Python → 创建虚拟环境 → 安装依赖 → 启动。

**依赖**：Python 3.10+ · macOS 或 Windows

## 架构

```
msc_manager/
├── server.py              # WebSocket(14027) + HTTP(14028) 双端口服务
├── platform_adapters.py   # 三平台适配（路径、命令、环境）
├── config.json            # 用户可改配置（下载路径、端口）
├── requirements.txt       # 依赖：websockets + pywebview + modelscope
├── start.sh               # Mac 启动脚本
├── start.bat              # Windows 启动脚本
└── web/
    ├── index.html         # Dashboard 主页 + 子面板
    ├── style.css          # 武侠风主题（暖墨 + 朱砂 + 竹青）
    └── app.js             # WebSocket 通信 + UI 逻辑
```

## 设计思路

**壳就是壳。** 本地能做的，在壳内完成，需要官网深度的（推理、训练、创空间）一键跳转官网。

- **通信**：WebSocket + JSON-RPC，前端直接调用 SDK 方法
- **窗口**：pywebview 原生桌面窗口
- **下载**：SDK 原生 `snapshot_download` + 实时进度推送
- **风格**：少林/武侠风 · 暖墨色系 · 黄金分割圆角 · 竖排古书排版

## 许可证

本项目基于 [Apache 2.0](LICENSE) 协议开源。

ModelScope SDK 同样采用 Apache 2.0 协议。详见 [modelscope/LICENSE](https://github.com/modelscope/modelscope)。

## 免责声明

魔搭方寸间是一个第三方桌面工具，与阿里云/魔搭官方无直接关联。

[README.md](https://github.com/user-attachments/files/28418903/README.md)
