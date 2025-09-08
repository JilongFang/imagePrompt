# ImagePrompt 项目说明

## 项目概述
这是一个基于 Saasfly 的 Next.js SaaS 项目，专门用于图像提示生成和处理。项目采用 Monorepo 架构，包含前后端一体化的完整解决方案。

## 项目架构
- **框架**: Next.js (App Directory)
- **认证**: Clerk
- **数据库**: PostgreSQL + Prisma + Kysely
- **API**: tRPC
- **UI**: Tailwind CSS + Shadcn/ui + Framer Motion
- **状态管理**: Zustand + TanStack Query
- **邮件**: React Email + Resend
- **支付**: Stripe
- **部署**: Vercel

## 项目结构
```
├── apps/
│   └── nextjs/          # 主要 Next.js 应用
├── packages/
│   ├── ui/              # 共享 UI 组件
│   ├── db/              # 数据库模式和工具
│   ├── auth/            # 认证工具
│   └── email/           # 邮件模板和工具
├── tooling/             # 开发工具配置
└── turbo/               # Turbo 生成器配置
```

## 开发环境配置
- **包管理器**: Bun (推荐) / npm
- **开发端口**: 3000 (前端), 3001 (服务端)
- **Node.js**: >= 18

## 常用命令
```bash
# 安装依赖
bun install

# 开发环境启动
bun run dev:web

# 数据库推送
bun run db:push

# 构建
bun run build

# 代码检查
bun run lint
bun run typecheck

# 格式化
bun run format:fix
```

## 开发规范
1. 这是一个前后端一体的项目，所有调用第三方接口的代码都要写在 server 端，不能写在 client 端
2. 服务端口号是3001

## Coding Rules
1. 不要自作聪明瞎写代码，写代码前要先确认方案再执行
2. 不要添加冗余代码，比如各种无关的校验，只做必要的校验
3. 精简代码，如果之前已经有的功能、组件或者函数，可以考虑重构和抽象
4. 不要瞎改之前的代码，要先确认改完不会影响其他功能，比如之前的代码有问题，但是现在没有问题，不要瞎改，如果有不确定的可以跟我确认
5. 不要重复造轮子，比如之前已经有了一个类似的功能，不要重复造轮子
6. 有参考文档，比如接口文档或者官方示例文档，严格按照示例文档写代码，不要自由发挥
7. 打印调试日志要清晰，每一个步骤都要打印正确的上下文信息
8. 不要使用任何mock模拟数据

## 技术栈特性
### 核心功能
- 国际化支持 (i18n)
- SEO 优化
- Monorepo 架构
- 环境变量管理 (T3 Env)
- 端到端类型安全 (tRPC)

### UI/UX
- 响应式设计
- 动画效果 (Framer Motion)
- 图标库 (Lucide)
- 字体优化

### 代码质量
- TypeScript 类型检查
- ESLint + Prettier 代码规范
- Husky Git 钩子
- 性能监控 (Vercel Analytics)