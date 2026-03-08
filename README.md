# 新能源AI助手 - 智能选车平台

[![Next.js](https://img.shields.io/badge/Next.js-15.5.7-black?style=flat-square&logo=next.js)](https://nextjs.org/)
[![React](https://img.shields.io/badge/React-19-61DAFB?style=flat-square&logo=react)](https://react.dev/)
[![TypeScript](https://img.shields.io/badge/TypeScript-5.0-3178C6?style=flat-square&logo=typescript)](https://www.typescriptlang.org/)
[![Tailwind CSS](https://img.shields.io/badge/Tailwind-3.4-06B6D4?style=flat-square&logo=tailwindcss)](https://tailwindcss.com/)
[![Dify](https://img.shields.io/badge/Dify-AI%20Chatbot-1E90FF?style=flat-square)](https://dify.ai/)
[![Vercel](https://img.shields.io/badge/Vercel-Deployed-000000?style=flat-square&logo=vercel)](https://findbestev.vercel.app/)

🚀 **在线预览**: [https://findbestev.vercel.app/](https://findbestev.vercel.app/)

## 项目简介

新能源AI助手是一个基于 **Next.js + Dify** 构建的智能选车平台。通过集成 Dify AI 聊天机器人，为用户提供个性化的新能源汽车推荐服务。

### 核心功能

- **AI 智能对话**：集成 Dify Chatbot，7x24 小时在线解答选车问题
- **个性化推荐**：根据用户需求（续航、预算、充电条件等）智能匹配车型
- **专业分析**：续航分析、充电便利性评估、性价比优化、安全评级
- **响应式设计**：完美适配桌面端和移动端

## 技术栈

| 类别 | 技术 |
|------|------|
| 框架 | Next.js 15 (App Router) |
| 前端 | React 19 + TypeScript 5 |
| 样式 | Tailwind CSS 3.4 + shadcn/ui |
| 字体 | Geist Sans / Mono |
| 动画 | @paper-design/shaders-react |
| AI 服务 | Dify Chatbot (iframe 嵌入) |
| 包管理 | pnpm |

## 项目结构

```
dify-findbest-ev-main/
├── app/                      # Next.js App Router
│   ├── globals.css          # 全局样式
│   ├── layout.tsx           # 根布局
│   └── page.tsx             # 首页
├── components/              # React 组件
│   ├── ui/                  # shadcn/ui 组件
│   │   ├── button.tsx
│   │   └── card.tsx
│   ├── about-section.tsx    # 关于我们区块
│   ├── chatbot-modal.tsx    # AI 聊天弹窗
│   ├── features-section.tsx # 功能特性区块
│   ├── footer.tsx           # 页脚
│   ├── pulsing-border-shader.tsx  # 动态背景效果
│   ├── testimonial-section.tsx    # 用户评价区块
│   └── theme-provider.tsx   # 主题提供者
├── lib/
│   └── utils.ts             # 工具函数
├── public/                  # 静态资源
│   └── *.png / *.svg        # 图片资源
├── hero-section.tsx         # Hero 主视觉区
├── next.config.mjs          # Next.js 配置
├── tailwind.config.ts       # Tailwind 配置
└── package.json             # 依赖管理
```

## 页面结构

```
首页 (page.tsx)
├── HeroSection (hero-section.tsx)
│   ├── 主标题 + 副标题
│   ├── CTA 按钮（打开 AI 助手）
│   └── 动态 Shader 背景动画
├── FeaturesSection (components/features-section.tsx)
│   └── 6 大核心功能卡片
├── AboutSection (components/about-section.tsx)
│   ├── 平台介绍
│   └── 数据统计展示
├── TestimonialSection (components/testimonial-section.tsx)
│   └── 用户评价卡片
└── Footer (components/footer.tsx)
    ├── 品牌信息
    ├── 服务链接
    └── 联系方式
```

## AI 助手集成

项目通过 iframe 嵌入 Dify Chatbot：

```typescript
// components/chatbot-modal.tsx
<iframe
  src="https://udify.app/chatbot/No3kd75DgSqYcg7u"
  style={{ width: '100%', height: '100%' }}
  allow="microphone"
/>
```

## 快速开始

### 环境要求

- Node.js 18+
- pnpm

### 安装依赖

```bash
pnpm install
```

### 开发模式

```bash
pnpm dev
```

访问 http://localhost:3000

### 构建生产版本

```bash
pnpm build
```

## 配置说明

### next.config.mjs

```javascript
const nextConfig = {
  eslint: { ignoreDuringBuilds: true },
  typescript: { ignoreBuildErrors: true },
  images: { unoptimized: true },
}
```

### Dify Chatbot 配置

如需更换 Dify Chatbot，修改 `components/chatbot-modal.tsx` 中的 iframe src：

```typescript
<iframe src="https://udify.app/chatbot/YOUR_CHATBOT_ID" />
```

## 自定义主题

项目使用 Tailwind CSS + CSS 变量实现主题：

- 主色调：绿色 (`green-400` ~ `green-600`)
- 辅助色：蓝色 (`blue-400` ~ `blue-600`)
- 背景色：深灰/黑色系

修改 `tailwind.config.ts` 和 `app/globals.css` 可自定义主题。

## 部署

项目可部署到 Vercel、Netlify 或任何支持 Node.js 的平台：

```bash
# Vercel
vercel --prod

# 或静态导出
next build
# 输出到 dist/ 目录
```

## 许可证

MIT License

---

*Built with v0.app & Dify.ai*
