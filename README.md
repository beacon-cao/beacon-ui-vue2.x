# Beacon-UI

<p align="center">
  <a href="https://github.com/vuejs/vue">
    <img src="https://img.shields.io/badge/vue-2.7.14-brightgreen.svg" alt="vue">
  </a>
  <a href="https://github.com/ElemeFE/element">
    <img src="https://img.shields.io/badge/element--ui-2.15.12-brightgreen.svg" alt="element-ui">
  </a>
  <a href="https://opensource.org/licenses/MIT">
    <img src="https://img.shields.io/badge/license-MIT-blue.svg" alt="license">
  </a>
</p>

## 简介

Beacon-UI 是一套基于 **Vue 2** 和 **Element UI** 的前端快速开发脚手架，适用于企业级后台管理系统。项目内置了完善的权限管理、动态路由、代码生成、系统监控等核心功能模块，开箱即用，帮助开发者快速搭建后台管理应用。

> 💡 需要配套后端服务：[open-beacon](https://github.com/Beacon/open-beacon)（基于 Spring Boot 的快速开发平台）

## 技术栈

| 技术 | 版本 | 说明 |
|------|------|------|
| Vue | 2.7.14 | 渐进式 JavaScript 框架 |
| Vue Router | 3.4.9 | 官方路由管理器 |
| Vuex | 3.6.2 | 状态管理模式 |
| Element UI | 2.15.12 | 桌面端组件库 |
| Axios | 0.27.2 | HTTP 客户端 |
| ECharts | 5.4.0 | 数据可视化图表 |
| Monaco Editor | - | 代码编辑器（VS Code 内核） |

| Quill | 1.3.7 | 富文本编辑器 |
| Tinymce | - | 富文本编辑器（可选） |
| SCSS | - | CSS 预处理器 |

## 功能模块

```
├── 系统管理
│   ├── 用户管理        — 系统用户 CRUD、分配角色
│   ├── 部门管理        — 组织架构树形管理
│   ├── 岗位管理        — 岗位信息维护
│   ├── 角色管理        — 角色 CRUD、菜单/数据权限分配
│   ├── 菜单管理        — 动态菜单 & 按钮权限配置
│   ├── 字典管理        — 数据字典类型 & 数据维护
│   ├── 通知公告        — 系统公告发布
│   └── 站内信          — 站内消息通知（模板 & 发送）
├── 系统监控
│   ├── 在线用户        — 当前在线会话管理
│   ├── 操作日志        — 用户操作行为记录
│   ├── 登录日志        — 登录/登出记录
│   ├── 定时任务        — 在线 Cron 任务调度 & 日志
│   ├── Redis 监控      — 缓存状态 & 键值管理
│   ├── 服务监控        — 服务器 CPU/内存/磁盘/网络
│   ├── 数据源监控      — Druid 连接池状态
│   └── API 日志        — API 访问/错误日志
├── 系统工具
│   ├── 代码生成        — 前后端代码一键生成
│   ├── 系统接口        — Swagger / Knife4j 接口文档
│   ├── 数据库文档      — 数据库表结构文档
│   ├── 表单构建        — 可视化表单拖拽设计
│   └── 文件管理        — 文件上传/下载/预览
├── 认证中心
│   ├── 账号登录        — 用户名/密码 + 验证码
│   ├── 社交登录        — 第三方 OAuth2.0 登录
│   ├── SSO 单点登录    — 统一身份认证
│   ├── OAuth2 客户端   — 客户端管理 & Token 管理
│   └── Token 刷新      — 无感刷新 Access Token

```

## 内置功能

- ✅ **RBAC 权限模型** — 用户 → 角色 → 菜单/按钮，支持数据权限
- ✅ **动态路由** — 菜单路由从后端加载，前端动态注册
- ✅ **多标签页** — 类似浏览器标签的页面缓存管理
- ✅ **主题切换** — 暗色/亮色侧边栏，多色主题
- ✅ **国际化** — 完善的 i18n 支持
- ✅ **验证码** — 滑块验证 / 点选验证 / 图片验证码
- ✅ **响应式布局** — 适配桌面端和移动端
- ✅ **错误处理** — 401/404 错误页面，全局异常拦截
- ✅ **Token 管理** — 登录过期自动刷新，请求队列重放
- ✅ **数据字典** — 启动时缓存字典，全局可访问
- ✅ **文件上传** — 支持本地/OSS 等多种存储方式
- ✅ **代码编辑器** — 集成 Monaco Editor（VS Code 内核）
- ✅ **图表可视化** — ECharts 仪表盘面板
- ✅ **Gzip 压缩** — 生产环境静态资源压缩
- ✅ **Baidu 统计** — 可选的页面访问分析

## 目录结构

```
beacon-ui-vue2.x/
├── public/                 # 静态资源（不经过 webpack）
│   ├── favicon.ico         # Favicon 图标
│   ├── index.html          # HTML 模板
│   ├── libs/               # 第三方库（Monaco Editor）
│   └── robots.txt
├── src/
│   ├── api/                # API 接口定义
│   │   ├── login.js        # 登录认证接口
│   │   ├── menu.js         # 菜单接口
│   │   ├── system/         # 系统管理接口
│   │   └── infra/          # 基础设施接口
│   ├── assets/             # 静态资源（经过 webpack）
│   │   ├── icons/          # SVG 图标
│   │   ├── images/         # 图片资源
│   │   ├── logo/           # Logo 资源
│   │   └── styles/         # 全局样式
│   ├── components/         # 公共组件
│   │   ├── Breadcrumb/     # 面包屑
│   │   ├── Crontab/        # Cron 表达式生成器
│   │   ├── DictTag/        # 字典标签
│   │   ├── Editor/         # 富文本编辑器
│   │   ├── FileUpload/     # 文件上传
│   │   ├── IconSelect/     # 图标选择器
│   │   ├── ImagePreview/   # 图片预览
│   │   ├── ImageUpload/    # 图片上传
│   │   ├── Pagination/     # 分页组件
│   │   ├── RightToolbar/   # 右侧工具栏
│   │   ├── SvgIcon/        # SVG 图标组件
│   │   ├── ThemePicker/    # 主题选择器
│   │   ├── TopNav/         # 顶部导航
│   │   ├── Verifition/     # 验证码组件
│   │   ├── generator/      # 表单代码生成器
│   │   ├── parser/         # 动态表单解析器
│   │   ├── render/         # 动态表单渲染器
│   │   └── tinymce/        # Tinymce 编辑器
│   ├── directive/          # 自定义指令
│   │   ├── dialog/         # 弹窗拖拽/拉伸
│   │   ├── module/         # 剪贴板复制
│   │   └── permission/     # 权限控制 (v-hasPermi / v-hasRole)
│   ├── layout/             # 页面布局
│   │   ├── index.vue       # 主布局
│   │   └── components/     # 布局组件（导航栏/侧边栏/标签页）
│   ├── plugins/            # 自定义插件
│   │   ├── auth.js         # 认证插件
│   │   ├── cache.js        # 缓存插件
│   │   ├── download.js     # 下载插件
│   │   ├── modal.js        # 弹窗插件
│   │   └── tab.js          # 标签页插件
│   ├── router/             # 路由配置
│   │   └── index.js        # 静态路由 + 动态路由注册
│   ├── store/              # Vuex 状态管理
│   │   └── modules/        # app / user / tagsView / permission / settings / dict
│   ├── utils/              # 工具函数
│   │   ├── request.js      # Axios 封装（拦截器/Token刷新）
│   │   ├── auth.js         # Token 存取工具
│   │   ├── permission.js   # 权限判断工具
│   │   ├── ruoyi.js        # 通用业务方法
│   │   └── validate.js     # 表单验证规则
│   ├── views/              # 页面视图
│   │   ├── login.vue       # 登录页
│   │   ├── index.vue       # 仪表盘首页
│   │   ├── system/         # 系统管理页面
│   │   ├── infra/          # 基础设施页面
│   │   ├── dashboard/      # 仪表盘图表
│   │   └── error/          # 错误页面 (401/404)
│   ├── App.vue             # 根组件
│   ├── main.js             # 入口文件
│   ├── permission.js       # 路由权限守卫
│   └── settings.js         # 全局配置
├── .env.dev                # 开发环境配置
├── .env.front              # 前端开发环境（远程 API）
├── .env.prod               # 生产环境配置
├── .env.stage              # 预发布环境配置
├── .env.static             # 静态部署配置
├── vue.config.js           # Vue CLI 构建配置
├── babel.config.js         # Babel 配置
├── .eslintrc.js            # ESLint 配置
├── Jenkinsfile             # Jenkins CI/CD
└── package.json
```

## 快速开始

### 环境要求

- **Node.js** >= 14.x
- **npm** >= 6.x（推荐使用 [cnpm](https://npmmirror.com/) 或 yarn）

### 安装依赖

```bash
# 克隆项目
git clone https://github.com/Beacon/beacon-ui.git

# 进入项目目录
cd beacon-ui-vue2.x

# 安装依赖（推荐使用 npmmirror 镜像）
npm install --registry=https://registry.npmmirror.com
```

### 本地开发

```bash
# 启动开发服务器（连接本地后端：localhost:7525）
npm run dev

# 或连接远程演示 API
npm run front
```

启动后浏览器自动打开 `http://localhost`，默认端口 80。

> ⚠️ 如需修改端口，编辑 `vue.config.js` 中 `devServer.port` 字段。

### 构建部署

```bash
# 生产环境构建
npm run build:prod

# 预发布环境构建
npm run build:stage

# 开发环境构建
npm run build:dev

# 静态资源部署构建
npm run build:static

# 预览生产构建结果
npm run preview
```

构建产物输出到 `dist/` 目录。

## 环境变量

| 变量名 | 说明 | 示例 |
|--------|------|------|
| `VUE_APP_TITLE` | 页面标题 | `Beacon快速开发脚手架` |
| `VUE_APP_BASE_API` | 后端 API 地址 | `http://localhost:7525` |
| `VUE_APP_APP_NAME` | 子路径部署名 | `/beacon-admin/` |
| `PUBLIC_PATH` | 静态资源 CDN 路径 | `/` |
| `VUE_APP_TENANT_ENABLE` | 多租户开关 | `true` / `false` |
| `VUE_APP_CAPTCHA_ENABLE` | 验证码开关 | `true` / `false` |
| `VUE_APP_DOC_ENABLE` | 内置文档开关 | `true` / `false` |

环境配置文件位于项目根目录：
- `.env.dev` — 本地开发
- `.env.front` — 远程演示 API 开发
- `.env.prod` — 生产环境
- `.env.stage` — 预发布环境
- `.env.static` — 静态部署

## 后端对接

本项目需要搭配后端服务使用，API 请求路径前缀为 `/admin-api/`。

开发环境下，前端通过 webpack devServer 将 `/proxy-api` 代理到 `http://localhost:7525`。生产环境下，`VUE_APP_BASE_API` 直接指向后端服务地址。

后端服务仓库：[open-beacon](https://github.com/Beacon/open-beacon)

## 浏览器兼容性

| Chrome | Firefox | Safari | Edge | IE |
|--------|---------|--------|------|-----|
| ✅ 最新版 | ✅ 最新版 | ✅ 最新版 | ✅ 最新版 | ⚠️ IE 11（需 polyfill） |

## License

[MIT](./LICENSE)

---

> 🏗️ **Beacon** — 让后台开发更简单高效
