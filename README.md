# ZZF Questions Front - 前端展示系统

基于Vue 3 + Element Plus开发的题目管理系统前端界面。

## 功能特性

### 🎯 后台管理界面 (`/admin`)
- ✅ 题目创建：支持单选题、多选题创建
- ✅ 题目编辑：完整的CRUD操作
- ✅ 题目列表：分页展示，支持筛选搜索
- ✅ 题目删除：单个删除功能
- ✅ 状态管理：启用/禁用题目状态

### 📚 前台展示界面 (`/frontend`)
- ✅ 题目浏览：逐题查看，支持上下翻页
- ✅ 答题功能：支持选择答案
- ✅ 答案查看：显示/隐藏正确答案和解析
- ✅ 随机题目：随机获取题目功能
- ✅ 筛选功能：按类型、难度、分类筛选
- ✅ 统计信息：题目统计数据展示

## 技术栈

- **Vue 3** - 前端框架
- **Vue Router 4** - 路由管理
- **Element Plus** - UI组件库
- **Axios** - HTTP客户端
- **Vue CLI** - 项目构建工具

## 快速开始

### 环境要求
- Node.js 16+
- npm 8+

### 启动步骤
```bash
# 克隆项目
git clone https://github.com/zzfer/zzf-questions-front.git
cd zzf-questions-front

# 安装依赖
npm install

# 启动开发服务器
npm run serve
```

应用将启动在: http://localhost:8083

### 配置说明
- 后端API地址: `src/api/index.js` 中配置为 `http://localhost:8082`
- 开发服务器端口: `vue.config.js` 中配置为 `8083`

## 项目结构

```
src/
├── api/                 # API接口封装
│   ├── index.js        # Axios配置
│   └── questions.js    # 题目相关API
├── router/             # 路由配置
│   └── index.js
├── views/              # 页面组件
│   ├── AdminPanel.vue  # 后台管理页面
│   └── FrontendDisplay.vue # 前台展示页面
├── App.vue            # 根组件
└── main.js           # 入口文件
```

## API集成

### 后台管理API
```javascript
import { adminApi } from '@/api/questions'

// 创建题目
await adminApi.createQuestion(questionData)

// 获取题目列表
await adminApi.getQuestions(params)

// 更新题目
await adminApi.updateQuestion(id, questionData)

// 删除题目  
await adminApi.deleteQuestion(id)
```

### 前台展示API
```javascript
import { publicApi } from '@/api/questions'

// 获取激活题目
await publicApi.getActiveQuestions(params)

// 随机获取题目
await publicApi.getRandomQuestions({ count: 5 })

// 获取题目答案
await publicApi.getQuestionAnswer(id)
```

## 页面说明

### 后台管理页面 (/admin)
- **左侧**: 题目创建/编辑表单
- **右侧**: 题目列表和管理操作
- **功能**: 支持题目的完整生命周期管理

### 前台展示页面 (/frontend) 
- **左侧**: 当前题目展示和答题区域
- **右侧**: 题目筛选、列表导航和统计信息
- **功能**: 提供良好的题目浏览和答题体验

## 构建和部署

### 开发环境
```bash
npm run serve
```

### 生产构建
```bash
npm run build
```

生成的文件在 `dist/` 目录下，可以部署到任何静态文件服务器。

### 环境变量
- `VUE_APP_API_BASE_URL`: 后端API基础地址
- `NODE_ENV`: 运行环境 (development/production)

## 贡献
欢迎提交Issue和Pull Request来帮助改进项目。

## 许可证
MIT License