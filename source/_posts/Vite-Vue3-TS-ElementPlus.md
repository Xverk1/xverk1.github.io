---
title: Vite+Vue3+TS+ElementPlus
date: 2025-01-23 21:14:56
tags:
description: 描述喵~
---

# Vite + Vue3 + TypeScript + ElementPlus 创建后台管理项目

## 创建并启动项目

```bash
# 创建一个vite项目, 创建之后选择vue, 和typescript
npm create vite@latest
```

```bash
# 创建完成进入到项目文件夹
cd [project-folder]

# 安装依赖
npm i

# 启动项目
npm run dev
```

> 也可参阅 package.json 中的其他调试脚本

```json
// package.json

"scripts": {
  "dev": "vite",
  "build": "vue-tsc -b && vite build",
  "preview": "vite preview"
},
```
