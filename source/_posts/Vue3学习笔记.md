---
title: Vue3学习笔记
date: 2025-01-01 22:07:31
tags:
description: Vue3的学习记录, 欸嘿嘿
categories:
  - 开发
  - 前端
---

# Vue3 简介

> 以后再写

# 创建 Vue3 工程

## 准备阶段

### 安装 Nodejs

需要下载并安装`Nodejs`环境, 我现在用的版本是`v22.12.0`, 若遇到网络问题可自行使用国外旅游软件

下载地址: https://nodejs.org/zh-cn

下载完毕后按照步骤安装即可
安装完毕后使用一下命令看是否出现版本号

```bash
node -v
npm -v
```

输出结果应该为(根据安装版本不同版本号会有差异)

```bash
v22.12.0
10.9.0
```

### 修改 npm 镜像源(可选)

因为众所周知的原因, 在境内访问境外服务器总是出现网络问题, `nodejs`的包管理器`npm`是重灾区, 为避免使用`npm`时出现网络问题, 可将`npm`的仓库换成境内镜像源

```bash
npm config set registry https://registry.npmmirror.com
```

还有一种方式是下载`cnpm`替代`npm`, 我不想用, 就不写了

## 步骤

有两种方法

- 基于`vue-cli` (目前`vue-cli`已处于维护模式，官方推荐基于`Vite`创建项目。)
- 基于`Vite`

由于 vue-cli 已停止维护, 所以这里使用官方更推荐的`Vite`创建项目

### 使用 Vite 创建项目

在项目文件夹中

```bash
npm create vue@latest
```

输出结果为

```bash
> npx
> create-vue


Vue.js - The Progressive JavaScript Framework

? 请输入项目名称： » vue-project
```

根据提示输入项目名称, 以 learn-vue3 为例

刚开始学习建议仅启用`TypeScript`, 其他可以先选择否, 学习到后面再引入

```bash
√ 请输入项目名称： ... learn-vue3
√ 是否使用 TypeScript 语法？ ... 否 / 是
√ 是否启用 JSX 支持？ ... 否 / 是
√ 是否引入 Vue Router 进行单页面应用开发？ ... 否 / 是
√ 是否引入 Pinia 用于状态管理？ ... 否 / 是
√ 是否引入 Vitest 用于单元测试？ ... 否 / 是
√ 是否要引入一款端到端（End to End）测试工具？ » 不需要
√ 是否引入 ESLint 用于代码质量检测？ » 否

正在初始化项目 C:\Users\Xverk\Workspace\learn-vue3...(这里是你的项目文件夹)
```

执行完毕后, 会输出以下结果

```bash
项目初始化完成，可执行以下命令：

  cd learn-vue3
  npm install
  npm run dev
```

#### 安装依赖并启动项目

根据提示, 可以依次执行上述代码

- `cd learn-vue3`: 移动到项目文件夹
- `npm install`: 使用`npm`安装依赖

输出结果(依赖安装完毕)

```bash
added 175 packages in 8s

45 packages are looking for funding
  run `npm fund` for details
```

- `npm run dev`: 运行`dev`开发脚本

输出结果(项目成功启动)

```bash
VITE v6.0.7  ready in 683 ms

  ➜  Local:   http://localhost:5173/
  ➜  Network: use --host to expose
  ➜  Vue DevTools: Open http://localhost:5173/__devtools__/ as a separate window
  ➜  Vue DevTools: Press Alt(⌥)+Shift(⇧)+D in App to toggle the Vue DevTools
  ➜  press h + enter to show help
```

至此, 使用 Vite 创建的 Vue3 项目已经创建完毕, 可以打开提示中的`http://localhost:5173/`进入项目页面, 成功进入页面并且元素正常显示说明创建成功

### 使用 vue-cli 创建项目

> 由于`vue-cli`已经停止维护, 这里暂时先不写创建方法, 以后随缘...

# Vue3 核心语法

## 认识 Vue3 项目结构

![test.png](./Vue3项目结构.png)
