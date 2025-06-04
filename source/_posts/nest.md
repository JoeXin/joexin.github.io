
---
title: Nest使用
date: 2025-06-04
tags: [后台]
---

#### 安装 Node.js 和 npm
首先，确保你的系统上安装了 Node.js 和 npm。你可以通过在终端或命令提示符中运行以下命令来检查它们是否已安装：

`
node -v
npm -v
`

如果未安装，请从 Node.js 官网 下载并安装。

#### 安装 Nest CLI
Nest CLI 是一个命令行工具，用于快速创建和管理 NestJS 项目。安装完成后，你可以使用它来生成项目、服务和控制器等。

`
npm i -g @nestjs/cli
`

创建一个新的 Nest 项目
使用 Nest CLI 创建一个新的项目：

`
nest new project-name
`

将 project-name 替换为你的项目名称。这将创建一个新的目录，并在其中生成一个基本的 NestJS 项目结构。

启动开发服务器
进入项目目录并启动开发服务器：


`
cd project-name
npm run start
`

现在，你可以在浏览器中访问 http://localhost:3000，你应该会看到一个欢迎页面。