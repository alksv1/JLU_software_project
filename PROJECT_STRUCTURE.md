# 项目结构说明

```
JLU_software_project/
├── README.md                    # 项目主要文档
├── QUICK_START.md              # 快速开始指南
├── PROJECT_STRUCTURE.md       # 项目结构说明 (本文件)
├── database_design.md         # 数据库设计文档
├── pyproject.toml             # Python项目配置和依赖管理
├── uv.lock                    # uv锁定文件
├── env.example               # 环境变量模板
├── .env                      # 环境变量文件 (git忽略)
├── .gitignore               # Git忽略文件配置
│
├── scripts/                 # 脚本目录
│   ├── init-dev.sh         # 开发环境初始化脚本
│   └── start-dev.sh        # 开发服务启动脚本
│
├── backend/                 # 后端代码目录
│   ├── run.py              # 后端启动脚本
│   └── app/                # FastAPI应用
│       ├── main.py         # 应用入口文件
│       ├── __init__.py
│       │
│       ├── core/           # 核心配置模块
│       │   ├── __init__.py
│       │   ├── config.py   # 应用配置
│       │   ├── security.py # 安全相关(JWT, 密码哈希等)
│       │   └── deps.py     # 依赖注入(认证, 权限等)
│       │
│       ├── db/             # 数据库相关
│       │   ├── __init__.py
│       │   └── database.py # 数据库连接配置
│       │
│       ├── models/         # 数据模型(SQLAlchemy ORM)
│       │   ├── __init__.py
│       │   ├── user.py     # 用户模型
│       │   ├── campus.py   # 校区模型
│       │   ├── coach.py    # 教练模型
│       │   ├── student.py  # 学员模型
│       │   ├── coach_student.py    # 教练学员关系
│       │   ├── course.py   # 课程模型
│       │   ├── booking.py  # 预约模型
│       │   ├── payment.py  # 支付模型
│       │   ├── evaluation.py      # 评价模型
│       │   ├── competition.py     # 比赛模型
│       │   ├── system_log.py      # 系统日志模型
│       │   └── license.py  # 许可证模型
│       │
│       ├── schemas/        # Pydantic数据传输对象
│       │   ├── __init__.py
│       │   ├── user.py     # 用户相关Schema
│       │   ├── campus.py   # 校区相关Schema
│       │   ├── coach.py    # 教练相关Schema
│       │   ├── student.py  # 学员相关Schema
│       │   ├── booking.py  # 预约相关Schema
│       │   ├── payment.py  # 支付相关Schema
│       │   ├── evaluation.py      # 评价相关Schema
│       │   ├── competition.py     # 比赛相关Schema
│       │   └── system_log.py      # 日志相关Schema
│       │
│       ├── services/       # 业务逻辑服务层
│       │   ├── __init__.py
│       │   ├── user_service.py     # 用户服务
│       │   ├── campus_service.py   # 校区服务
│       │   ├── coach_service.py    # 教练服务
│       │   ├── student_service.py  # 学员服务
│       │   ├── booking_service.py  # 预约服务
│       │   ├── payment_service.py  # 支付服务
│       │   ├── evaluation_service.py   # 评价服务
│       │   ├── competition_service.py  # 比赛服务
│       │   └── system_log_service.py   # 日志服务
│       │
│       ├── api/            # API路由层
│       │   ├── __init__.py
│       │   ├── auth/       # 认证相关API
│       │   │   └── __init__.py
│       │   └── v1/         # API版本1
│       │       ├── __init__.py
│       │       ├── auth.py      # 认证路由
│       │       ├── users.py     # 用户管理路由
│       │       ├── campus.py    # 校区管理路由
│       │       ├── coaches.py   # 教练管理路由
│       │       ├── students.py  # 学员管理路由
│       │       ├── bookings.py  # 预约管理路由
│       │       ├── payments.py  # 支付管理路由
│       │       ├── evaluations.py   # 评价管理路由
│       │       ├── competitions.py  # 比赛管理路由
│       │       └── system_logs.py   # 系统日志路由
│       │
│       └── utils/          # 工具函数
│           ├── __init__.py
│           ├── helpers.py  # 通用辅助函数
│           ├── validators.py    # 数据验证器
│           └── constants.py     # 常量定义
│
├── frontend/               # 前端代码目录
│   ├── package.json       # Node.js项目配置
│   ├── tsconfig.json      # TypeScript配置
│   ├── vite.config.ts     # Vite构建配置
│   ├── index.html         # HTML模板
│   │
│   ├── public/            # 静态资源
│   │   └── favicon.ico
│   │
│   └── src/               # 源代码目录
│       ├── main.ts        # 应用入口文件
│       ├── App.vue        # 根组件
│       │
│       ├── types/         # TypeScript类型定义
│       │   └── index.ts   # 全局类型定义
│       │
│       ├── api/           # API接口层
│       │   ├── request.ts # HTTP请求封装
│       │   ├── auth.ts    # 认证相关API
│       │   └── campus.ts  # 校区相关API
│       │
│       ├── store/         # Pinia状态管理
│       │   └── user.ts    # 用户状态管理
│       │
│       ├── router/        # Vue Router路由配置
│       │   └── index.ts   # 路由定义
│       │
│       ├── components/    # 可复用组件
│       │   ├── common/    # 通用组件
│       │   ├── user/      # 用户相关组件
│       │   ├── admin/     # 管理员组件
│       │   ├── coach/     # 教练组件
│       │   └── student/   # 学员组件
│       │
│       ├── views/         # 页面组件
│       │   ├── auth/      # 认证页面
│       │   │   ├── Login.vue    # 登录页
│       │   │   └── Register.vue # 注册页
│       │   ├── user/      # 用户页面
│       │   │   └── Profile.vue  # 个人信息页
│       │   ├── admin/     # 管理员页面
│       │   │   ├── Layout.vue          # 管理员布局
│       │   │   ├── CampusManagement.vue    # 校区管理
│       │   │   └── UserManagement.vue     # 用户管理
│       │   ├── student/   # 学员页面
│       │   │   ├── Layout.vue      # 学员布局
│       │   │   ├── CoachList.vue   # 教练列表
│       │   │   ├── Bookings.vue    # 我的预约
│       │   │   ├── Payments.vue    # 账户充值
│       │   │   └── Competitions.vue # 比赛报名
│       │   ├── coach/     # 教练页面
│       │   │   ├── Layout.vue      # 教练布局
│       │   │   ├── Students.vue    # 我的学员
│       │   │   ├── Bookings.vue    # 课程安排
│       │   │   └── Evaluations.vue # 课后评价
│       │   ├── error/     # 错误页面
│       │   │   └── NotFound.vue    # 404页面
│       │   └── Dashboard.vue       # 仪表板页面
│       │
│       └── utils/         # 工具函数
│           ├── helpers.ts # 通用辅助函数
│           ├── constants.ts    # 常量定义
│           └── validators.ts   # 表单验证器
│
├── tests/                 # 测试目录
│   ├── backend/          # 后端测试
│   │   ├── test_auth.py  # 认证测试
│   │   └── test_users.py # 用户测试
│   └── frontend/         # 前端测试
│       └── unit/         # 单元测试
│
├── alembic/              # 数据库迁移文件 (运行后生成)
│   ├── versions/         # 迁移版本文件
│   ├── env.py           # Alembic环境配置
│   └── alembic.ini      # Alembic配置文件
│
├── uploads/              # 文件上传目录 (运行后生成)
│   ├── avatars/         # 用户头像
│   └── documents/       # 文档文件
│
└── logs/                 # 日志文件目录 (运行后生成)
    ├── app.log          # 应用日志
    └── error.log        # 错误日志
```

## 🏗️ 架构说明

### 后端架构 (FastAPI)

采用分层架构设计：

1. **API层** (`api/`): 处理HTTP请求，参数验证，响应格式化
2. **服务层** (`services/`): 业务逻辑处理，事务管理
3. **模型层** (`models/`): 数据模型定义，数据库映射
4. **核心层** (`core/`): 配置管理，安全认证，依赖注入

### 前端架构 (Vue 3)

采用组件化架构：

1. **视图层** (`views/`): 页面级组件，路由对应
2. **组件层** (`components/`): 可复用UI组件
3. **状态层** (`store/`): 全局状态管理
4. **服务层** (`api/`): API接口封装

### 数据流

```
前端组件 → API调用 → 后端路由 → 服务层 → 数据模型 → 数据库
    ↑                                                      ↓
响应数据 ← JSON响应 ← 数据验证 ← 业务处理 ← 数据查询 ← SQL执行
```

## 📝 开发规范

### 命名规范

- **文件名**: 小写+下划线 (如: `user_service.py`)
- **类名**: 大驼峰 (如: `UserService`)
- **函数名**: 小写+下划线 (如: `get_user_by_id`)
- **变量名**: 小写+下划线 (如: `user_id`)
- **常量名**: 大写+下划线 (如: `MAX_FILE_SIZE`)

### 目录规范

- 每个目录都有 `__init__.py` 文件
- 相关功能模块放在同一目录下
- 测试文件与源文件目录结构保持一致

### 导入规范

```python
# 标准库导入
from typing import List, Optional

# 第三方库导入
from fastapi import APIRouter, Depends
from sqlalchemy.orm import Session

# 本地导入
from ..models.user import User
from ..services.user_service import UserService
```

## 🔧 扩展指南

### 添加新功能模块

1. 在 `models/` 中定义数据模型
2. 在 `schemas/` 中定义请求/响应模式
3. 在 `services/` 中实现业务逻辑
4. 在 `api/v1/` 中创建API路由
5. 在前端添加对应的页面和组件

### 添加新的用户角色

1. 修改 `models/user.py` 中的 `UserRole` 枚举
2. 更新 `core/deps.py` 中的权限检查函数
3. 在前端路由中添加角色权限配置
4. 创建对应的前端页面和菜单

---

这个项目结构遵循了现代Web开发的最佳实践，具有良好的可维护性和可扩展性。
