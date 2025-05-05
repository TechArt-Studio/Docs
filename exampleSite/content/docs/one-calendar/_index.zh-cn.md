---
linkTitle: "One Calendar"
title: One Calendar
next: /docs/one-calendar/url-to-add
sidebar:
open: true
---

<div align="center">
<img src="https://calendar.xyehr.cn/icon.svg" width="72">

# One Calendar

<p>

<a href="https://vercel.com/tech-art/one-calendar" target="_blank"><img src="https://vercelbadge.vercel.app/api/EvanTechDev/One-Calendar?style=flat-square" alt="Vercel 项目状态"></a>
<a href="https://github.com/EvanTechDev/One-Calendar/blob/master/LICENSE" target="blank"><img src="https://img.shields.io/github/license/EvanTechDev/One-Calendar?style=flat-square" alt="license"></a>
<a href="https://github.com/EvanTechDev/One-Calendar/fork" target="blank"><img src="https://img.shields.io/github/forks/EvanTechDev/One-Calendar?style=flat-square" alt="forks"></a>
<a href="https://github.com/EvanTechDev/One-Calendar/stargazers" target="blank"><img src="https://img.shields.io/github/stars/EvanTechDev/One-Calendar?style=flat-square" alt="stars"></a>
<a href="https://github.com/EvanTechDev/One-Calendar/issues" target="blank"><img src="https://img.shields.io/github/issues/EvanTechDev/One-Calendar?style=flat-square" alt="issues"></a>
<a href="https://github.com/EvanTechDev/One-Calendar/pulls" target="blank"><img src="https://img.shields.io/github/issues-pr/EvanTechDev/One-Calendar?style=flat-square" alt="pull-requests"></a>

</p>

一款精美简约的开源日历应用，助您规划一周日程和生活。

<a href="https://vercel.com/new/clone?repository-url=https://github.com/EvanTechDev/One-Calendar&env=NEXT_PUBLIC_BASE_URL,NEXT_PUBLIC_CLERK_PUBLISHABLE_KEY,CLERK_SECRET_KEY,OPENWEATHER_API_KEY,BLOB_READ_WRITE_TOKEN&project-name=one-calendar&repo-name=one-calendar" style="display: inline-block;"><img src="https://vercel.com/button" alt="使用 Vercel 部署" style="height: 32px;"></a>
<a href="https://app.netlify.com/start/deploy?repository=https://github.com/EvanTechDev/One-Calendar" style="display: inline-block;"><img src="https://www.netlify.com/img/deploy/button.svg" alt="部署到 Netlify" style="height: 32px;"></a>

</div>

## 什么是 One Calendar？

**One Calendar** 是一款注重隐私、专注于每周日程安排的开源日历应用，旨在帮助个人和团队规划、集中精力并保持同步。

> 如果没有 *One Calendar*，您的日程安排就会变得杂乱无章。有了它，您的一周就会感觉井井有条。

## 为什么选择 One Calendar？

大多数日历工具都杂乱无章、设计过度或需要付费使用。One Calendar 的目标是：

- 🧠 **AI 驱动** – AI 优先的应用，可简化您的日程安排。
- 🕹 **交互流畅** – 轻松拖放、右键单击和编辑。
- 🔐 **私密与本地** – 您的数据由您掌控。导出、备份和控制。
- ☁️ **云同步** – 可选通过 Vercel Blob 同步。
- 🌐 **Clerk-Account** – 轻松使用第三方账户登录。
- 🌍 **国际化** – 自动适应您的语言（英语/中文）。
- 🧱 **可定制** – 定制主题、默认视图和集成。

## 技术栈

- **前端**：Next.js 14、Tailwind CSS、shadcn/ui、TypeScript
- **授权**：Clerk
- **存储**：LocalStorage、Vercel Blob、Misskey Drive
- **天气**：OpenWeather API
- **人工智能**：Groq API

![TechStack](https://skills-icons.vercel.app/api/icons?i=nextjs,ts,tailwindcss,shadcnui,clerk,groq,vercel,openweather,bun)

## 预览

![Home](https://calendar.xyehr.cn/Home.jpg)
![App](https://calendar.xyehr.cn/Banner.jpg)

## 入门

### 先决条件

所需版本：

- [NodeJS](https://nodejs.org)（v18 或更高版本）
- [Bun](https://bun.sh) (v1.2 或更高版本)

### 快速入门

```bash
# 克隆代码库
git clone https://github.com/EvanTechDev/One-Calendar.git
cd One-Calendar

# 安装依赖项
bun install

# 启动应用
bun run dev
```

然后访问 `http://localhost:3000`

### 环境变量

将 `.env.example` 复制到 `.env` 并填写以下内容：

```env
NEXT_PUBLIC_BASE_URL=你的 URL

# Clerk API 密钥（必需）
NEXT_PUBLIC_CLERK_PUBLISHABLE_KEY=你的 Clerk 发布密钥
CLERK_SECRET_KEY=你的 Clerk 密钥

#可选
GROQ_API_KEY=你的 groq-api
OPENWEATHER_API_KEY=你的 open-weather-api-key

# 可选，在 Misskey 和 Vercel blob 之间选择
MISSKEY_URL=https://misskey.io
MISSKEY_TOKEN=你的 Misskey 令牌
BLOB_READ_WRITE_TOKEN=你的 Vercel blob 令牌
```

### 环境设置

1.Misskey Drive

前往使用 Misskey 构建的社交媒体

前往“设置”<“API”

![API](https://github.com/user-attachments/assets/db9cead7-96a2-4fd7-8c0b-55429198aa91)

点击“生成访问权限” Token

![Generate_Token](https://github.com/user-attachments/assets/db068882-060d-4752-ac5e-7809dfb6a9b8)

点击“Enable All”，然后确认

![Enable_All](https://github.com/user-attachments/assets/58d445da-4133-4519-9e7e-8f4d62dd9116)

填写环境变量：

```env
MISSKEY_URL=https://misskey.io（或您的 URL）
MISSKEY_TOKEN=您的 misskey 令牌
```

2. Groq

前往 [Groq 控制台](https://console.groq.com) 并登录

点击“Create API”密钥

![Screenshot_20250502_150743](https://github.com/user-attachments/assets/1e8faf08-7afe-405e-83a7-01039de35338)

复制您的 API 密钥

![Screenshot_20250502_150857](https://github.com/user-attachments/assets/55374169-7f2b-480d-924f-80a46b014551)

填写环境变量：

```env
GROQ_API_KEY=你的 API 密钥
```

## 路线图

您可以在我们的反馈网站上报告错误或请求新功能。

[路线图和反馈](https://feedback.xyehr.cn)

## 星级历史

[![星级历史图表](https://api.star-history.com/svg?repos=EvanTechDev/One-Calendar&type=Date)](https://www.star-history.com/#EvanTechDev/One-Calendar&Date)

## 团队

由一支热爱简洁工具和开源的小型创客团队为您带来。

查看我们的[贡献者](https://github.com/EvanTechDev/One-Calendar/graphs/contributors) ❤️

## 赞助商

BTC：`bc1qdhn6c7tlcaflzu3u5fva825l20k9eqnqag5xzj`

MOB： `6tKKBDHJFcRhCvTx9wJeNH8gUUfXvPUBHnegCV8M3Qniy4UBDyRzQrHQnxGcGEebibG3Q62RxgKABe75kArpLkd8igwWw6BviTAcyp7DGgZ2LqMBWjSPEgypMSGpDjwqfD6L9PECUm4HZzRGCvMT3jL8rjev4thCqH16jrrVBnUt7VDrqZsoSDVViEAGitG9axZtekUQNK2vzgdYxPEQtnZ4ouYyPLaxPYmKHDW2XrQuA5`

## 致谢

如果没有这些优秀的服务，这个项目就不可能实现：

<div style="display: flex; justify-content: center;">
<a href="https://vercel.com" style="text-decoration: none;"><img src="https://github.com/user-attachments/assets/5107d47f-7ce9-425a-8e24-77c322205bd4" alt="Vercel" width="96"/></a>
<a href="https://clerk.com" style="text-decoration: none;"><img src="https://github.com/user-attachments/assets/6f9fa5d7-e0c2-4c14-aef9-e39bd0465e23" alt="Clerk" width="96"/></a>
<a href="https://groq.com" style="text-decoraion: none;"><img src="https://github.com/user-attachments/assets/650dc220-c0a7-4761-a7ce-2c24a7d75133" alt="Groq" width="96"></a>
<a href="https://openweathermap.org" style="text-decoration: none;"><img src="https://github.com/user-attachments/assets/d07ed7a1-c374-45f5-90fd-17c3de2a9098" alt="OpenWeather API" width="96"/></a>
</div>

## 许可证

本项目采用 GNU 通用公共许可证 v3.0 (GPL-3.0) 授权。
详情请参阅 [LICENSE](./LICENSE) 文件。

> [!NOTE]\
> 部分组件根据 MIT 许可证改编自外部来源，包括 [Zero Email](https://github.com/Mail-0/Zero) 项目的部分内容。
> 这些组件保留其原始许可条款。请参阅相关文件了解版权信息。
