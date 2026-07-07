# gitt

## 项目简介

本项目是基于 **Qt 6.x（前端） + C++17（后端）** 技术栈开发的在线教育平台。

## 功能特性

- **用户管理**：学生/教师/管理员三种角色，支持注册、登录、权限管理
- **课程管理**：教师创建/编辑/发布课程，支持视频上传和自动转码
- **视频播放**：支持 HLS 流媒体播放、断点续播、倍速播放（0.5x~2x）
- **在线考试**：章节测验 + 期末考试，客观题自动评分，主观题教师批改
- **学习进度**：实时跟踪学习进度，生成学习报告
- **论坛互动**：课程专属讨论区，支持发帖、回帖、点赞
- **个性化推荐**：基于协同过滤 + 内容推荐的课程推荐（可选功能）

## 技术架构

| 层次 | 技术 |
|------|------|
| 前端 | Qt 6.x (Widgets + QML) |
| 后端 | C++17 + Drogon HTTP 框架 |
| 数据库 | MySQL 8.0 + Redis 7.x |
| 存储 | MinIO（视频/文档） |
| 消息队列 | RabbitMQ |
| 构建 | CMake 3.20+ |

## 开发环境要求

- **编译器**：GCC 11+ / Clang 14+ / MSVC 2022+
- **Qt**：6.x（Qt Multimedia 模块用于视频播放）
- **CMake**：3.20+
- **数据库**：MySQL 8.0+, Redis 7.x
- **FFmpeg**：用于视频转码

## 项目结构

```
gitt/
├── frontend/          # Qt 前端代码
├── backend/           # C++ 后端代码
├── docs/              # 文档（需求规格说明书等）
├── scripts/           # 构建和部署脚本
├── CMakeLists.txt     # 顶层 CMake 构建文件
└── README.md
```

## 快速开始

```bash
# 克隆仓库
git clone <仓库地址>

# 构建后端
cd backend
mkdir build && cd build
cmake .. -DCMAKE_BUILD_TYPE=Release
make -j$(nproc)

# 构建前端（Qt）
cd ../../frontend
mkdir build && cd build
cmake .. -DCMAKE_PREFIX_PATH=/path/to/Qt/6.x
make -j$(nproc)
```

## 许可证

MIT License