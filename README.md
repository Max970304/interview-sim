# Interview Simulator (模拟面试平台)

## 项目简介
本项目旨在实现一个**模拟面试平台**，帮助用户进行多场景下的面试练习，包括但不限于：
- 各种类型的面试官角色选择（男/女、年轻/年长、不同风格等）
- 可选的面试种类和岗位（如升学、选调生、产品经理、算法工程师面试等）
- 设备检测（摄像头、麦克风、网络连接）
- 逐题展示面试题并播放对应音频
- 面试者通过摄像头实时录制回答视频
- 面试结束后，录制的视频上传至数据库，并显示完成提示

## 技术栈
- **前端**：
  - React 18 + TypeScript
  - TailwindCSS + shadcn/ui 组件库
  - React Router v7 路由管理
  - React Context 状态管理
- **后端**：
  - Supabase（Backend as a Service）
  - PostgreSQL 数据库
  - Supabase Auth 身份验证
  - Supabase Storage 对象存储
- **语音生成**：
  - fish-audio API

## 当前开发进度
### 项目初始化
- [x] 项目初始化与环境配置
  - [x] React + TypeScript 项目搭建
  - [x] TailwindCSS 配置
  - [x] shadcn/ui 组件库集成
  - [x] Supabase 集成
- [x] 语音服务配置
  - [x] fish-audio API 集成
  - [x] 音频服务器搭建
  - [x] 临时文件管理

### 数据存储
- [x] 用户数据存储（由supabase auth自动管理）
- [x] 面试官数据存储
- [x] 面试类型数据存储
- [x] 题库数据存储
- [x] 面试记录数据存储
- [x] 音频文件存储
  - [x] 参考音频存储
  - [x] 欢迎语音存储
  - [x] 题目音频存储

### 用户端
- [x] 用户认证系统
  - [x] 注册页面
    - [x] 表单验证
    - [x] 邮箱验证流程
    - [x] 错误处理
  - [x] 登录页面
    - [x] 表单验证
    - [x] "记住我"功能
    - [x] 错误处理
  - [x] 路由保护
    - [x] 未登录用户重定向
    - [x] 已登录用户访问限制
- [x] 面试场景配置
  - [x] 面试官选择
    - [x] 面试官数据展示
    - [x] 选择状态管理
    - [x] 页面间数据传递
  - [x] 面试类型选择
    - [x] 类型数据展示
    - [x] 已选面试官展示
    - [x] 选择状态管理
  - [x] 设备检测
    - [x] 摄像头检测与预览
    - [x] 麦克风检测与音量显示
    - [x] 网络连接测试
    - [x] 设备选择功能
    - [x] 测试失败重试机制
- [x] 面试流程
  - [x] 问题展示
    - [x] 音频播放控制
    - [x] 文字同步显示
  - [x] 视频录制
    - [x] 摄像头实时预览
    - [x] 音量实时显示
    - [x] 准备时间倒计时
    - [x] 回答时间倒计时
    - [x] 录制状态管理
  - [x] 面试完成页面
    - [x] 面试总结展示
    - [x] 查看录像入口
- [x] 个人中心
  - [x] 面试记录列表展示
  - [x] 录像回放功能
  - [x] 视频下载功能
  - [x] 记录删除功能
  - [x] 用户数据安全隔离
  - [x] 其他页面的个人中心组件

### 管理员端
- [x] 管理员登录与鉴权
- [x] 管理员控制台
  - [x] 统计数据展示
  - [x] 面试会话类型分布展示
  - [x] 快速导航到各管理功能
- [x] 面试官管理
  - [x] 添加/编辑/删除面试官
  - [x] 设置面试官头像、性别、年龄组和描述
  - [x] 上传参考音频
  - [x] 生成欢迎语音
- [x] 面试类型管理
  - [x] 添加/编辑/删除面试类型
  - [x] 查看每种类型的题目数量
- [x] 面试题目管理
  - [x] 按类型筛选题目
  - [x] 添加/编辑/删除题目
  - [x] 设置思考时间和回答时间
- [x] 面试记录管理
  - [x] 按用户筛选
  - [x] 按面试官筛选
  - [x] 按面试类型筛选
  - [x] 视频回放功能

## 最近更新
1. **响应式设计优化**
   - 优化所有页面在移动设备上的显示效果
   - 调整布局、字体大小和交互元素，确保在各种屏幕大小上的良好体验
   - 特别优化了面试记录管理页面和个人中心页面的小屏幕显示

2. **管理员界面改进**
   - 重新设计管理员控制台，提供更直观的数据统计展示
   - 加入面试类型分布图表，方便管理员了解系统使用情况
   - 所有管理页面统一添加退出登录按钮，提高用户体验
   - 管理功能直接导航优化，减少点击层级

3. **安全性增强**
   - 用户数据安全隔离，确保用户只能查看和操作自己的面试记录
   - 强化删除操作的权限验证，防止越权访问
   - 管理员权限控制优化

## 本地开发
1. **Supabase本地化实现**
- 安装Homebrew（用于下载本地版supabase）
```bash
/bin/bash -c "$(curl -fsSL https://gitee.com/ineo6/homebrew-install/raw/master/install.sh)"  # 执行安装Homebrew的脚本
wget https://gitee.com/cunkai/HomebrewCN/raw/master/Homebrew.sh ; bash Homebrew.sh  # Homebrew更换国内源
```
- 安装docker（本地版supabase内部依赖docker进行安装）
```bash
sudo apt update                    # 更新软件包列表
sudo apt upgrade -y               # 升级所有已安装的软件包
sudo apt install -y apt-transport-https ca-certificates curl software-properties-common    # 安装Docker的依赖包
curl -fsSL https://mirrors.aliyun.com/docker-ce/linux/ubuntu/gpg | sudo gpg --dearmor -o /usr/share/keyrings/docker-archive-keyring.gpg    # 下载并安装Docker的GPG密钥
echo "deb [arch=$(dpkg --print-architecture) signed-by=/usr/share/keyrings/docker-archive-keyring.gpg] https://download.docker.com/linux/ubuntu $(lsb_release -cs) stable" | sudo tee /etc/apt/sources.list.d/docker.list > /dev/null    # 添加Docker的软件源
sudo apt update                   # 再次更新软件包列表以包含Docker源
sudo apt install -y docker-ce docker-ce-cli containerd.io    # 安装Docker引擎和相关组件
sudo systemctl start docker      # 启动Docker服务
sudo systemctl enable docker     # 设置Docker开机自启动
sudo usermod -aG docker $USER    # 将当前用户添加到docker用户组
docker --version                 # 检查Docker版本
docker compose version           # 检查Docker Compose版本
```
- 安装supabase CLI
```bash
brew install supabase/tap/supabase  # 安装 Supabase CLI
echo 'export PATH=$PATH:/home/linuxbrew/.linuxbrew/bin' >> ~/.bashrc  # 将 Homebrew 的路径添加到环境变量中
source ~/.bashrc                      # 重新加载 .bashrc 文件以应用更改
which supabase                        # 显示 supabase 命令的安装路径
supabase --version                    # 显示已安装的 supabase 版本
```
- 启动supabase CLI
```bash
supabase init # 初始化supabase
supabase login # 登录supabase
supabase link --project-ref wzqpvtajwpkcvzgnbirh # 关联远程supabase项目
supabase start # 启动本地supabase项目
```
- 迁移远程supabase项目数据到本地supabase CLI
```bash
supabase db pull # 拉取远程supabase项目的表结构
supabase db pull --schema auth,storage # 拉取远程supabase项目的用户认证和存储结构
supabase db dump -f complete_dump.sql --schema public,auth,storage # 导出所有数据结构
sudo apt install postgresql-client-common postgresql-client # 安装PostgreSQL客户端工具
psql postgresql://postgres:postgres@127.0.0.1:54322/postgres -f complete_dump.sql # 连接到本地Supabase PostgreSQL数据库并导入数据结构
npm init -y
npm install @supabase/supabase-js
node download_storage.js # 从远程supabase项目下载存储文件（包括图像、音频、视频）迁移到本地
```

2. **克隆项目**
```bash
git clone [repository-url]
cd interview-sim
```

3. **安装依赖**
```bash
npm install
```

4. **环境变量配置**
创建 `.env.local` 文件并添加以下配置：
```
REACT_APP_SUPABASE_URL=your_supabase_url
REACT_APP_SUPABASE_ANON_KEY=your_supabase_anon_key
```

5. **配置 Python 环境**
```bash
conda create -n interview python=3.10
conda activate interview
pip install fish-audio-sdk aiofiles
```

6. **启动服务**
```bash
npm run dev
```

## 项目结构
```
interview-sim/
├── src/
│   ├── components/        # 可复用组件
│   │   ├── ProtectedRoute.tsx  # 普通用户路由保护
│   │   ├── AdminRoute.tsx      # 管理员路由保护
│   │   └── ui/           # UI 组件
│   │       ├── alert-dialog.tsx
│   │       ├── button.tsx
│   │       ├── card.tsx
│   │       ├── checkbox.tsx
│   │       ├── dialog.tsx
│   │       ├── input.tsx
│   │       ├── label.tsx
│   │       ├── progress.tsx
│   │       ├── select.tsx
│   │       ├── tabs.tsx
│   │       ├── textarea.tsx
│   │       ├── toast.tsx
│   │       └── toaster.tsx
│   │       └── use-toast.ts
│   ├── context/          # 全局状态管理
│   │   └── UserContext.tsx
│   ├── lib/             # 工具函数
│   │   └── utils.ts
│   ├── pages/            # 页面组件
│   │   ├── admin/           # 管理员页面
│   │   │   ├── Dashboard.tsx
│   │   │   ├── InterviewerManagement.tsx
│   │   │   ├── TypeManagement.tsx
│   │   │   ├── QuestionManagement.tsx
│   │   │   └── RecordManagement.tsx
│   │   ├── DeviceCheck.tsx
│   │   ├── Home.tsx
│   │   ├── Interview.tsx
│   │   ├── InterviewComplete.tsx
│   │   ├── InterviewerSelect.tsx
│   │   ├── InterviewerTest.tsx
│   │   ├── InterviewTypeSelect.tsx
│   │   ├── Login.tsx
│   │   ├── Profile.tsx
│   │   └── Register.tsx
│   ├── services/         # 服务层
│   │   ├── authService.ts
│   │   └── supabaseClient.ts
│   ├── server/          
│   │   └── audioServer.ts   # 音频服务器
│   ├── utils/           # 工具函数
│   │   ├── storageCleamup.ts
│   │   └── textToSpeech.ts  # 语音合成工具
│   └── App.tsx          # 路由配置
├── temp/               # 临时文件目录（自动清理）
├── public/             # 静态资源
├── .env.local          # 环境变量
├── tsconfig.json       # TypeScript配置
├── tsconfig.server.json # 服务器端TypeScript配置
└── package.json
```
## 功能测试
目前可以测试以下功能：
1. **管理员功能**：访问 `/admin`
  - 使用管理员账号登录
  - 查看系统统计数据
  - 管理面试官（添加、编辑、删除）
  - 管理面试类型（添加、编辑、删除）
  - 管理面试题目（按类型筛选、添加、编辑、删除）
  - 查看面试记录（按用户、面试官和类型筛选）

2. **用户注册**：访问 `/register`
  - 输入邮箱和密码
  - 提交后查看注册结果

3. **用户登录**：访问 `/login`
  - 使用已注册的邮箱和密码
  - 登录成功后进入面试官选择页面

4. **路由保护**：
  - 未登录时访问任何受保护页面会自动重定向到登录页
  - 登录后可正常访问面试流程页面
  - 管理员路由保护，普通用户无法访问管理页面

5. **面试官选择**：访问 `/interviewer-select`
  - 查看不同类型的面试官
  - 显示面试官性别、年龄组和描述信息
  - 选择合适的面试官进入下一步

6. **面试类型选择**：访问 `/interview-type`
  - 查看已选择的面试官信息
  - 选择面试类型（校园招聘、社会招聘等）
  - 确认选择后进入设备检测环节

7. **设备检测**：访问 `/device-check`
  - 选择并测试摄像头
    - 实时视频预览
    - 支持多摄像头切换
  - 选择并测试麦克风
    - 实时音量显示
    - 支持多麦克风切换
  - 网络连接测试
    - 测试与 Supabase 的连接状态
  - 支持测试失败后重试
  - 全部测试通过后可进入面试

8. **面试流程**：访问 `/interview`
  - 逐题展示面试题
    - 音频播放
    - 文字同步显示
  - 视频录制
    - 摄像头实时预览
    - 音量实时显示
    - 准备时间倒计时
    - 回答时间倒计时
    - 录制状态管理
  - 面试完成页面
    - 面试总结展示
    - 查看录像入口

9. **个人中心**：访问 `/profile`
  - 显示用户信息
  - 面试记录列表（仅展示当前用户记录）
  - 录像回放功能
  - 视频下载功能
  - 记录删除功能
  - 其他页面的个人中心组件

## 注意事项
- 确保 `.env.local` 中的 Supabase 配置正确
- 确保 Python 环境和依赖安装完整
- 临时文件会自动清理，无需手动管理
- 所有用户数据严格隔离，确保数据安全
- 响应式设计已优化，但仍建议在不同设备上测试以确保最佳体验
