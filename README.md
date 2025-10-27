# VabHub-Resources

VabHub 资源文件仓库，包含配置文件、数据模板和平台相关的二进制资源。

## 🚀 快速开始

### 安装资源文件
```bash
# 复制资源文件到 VabHub-Core
cp -r ./* ../VabHub-Core/app/helper/

# 或使用安装脚本
./scripts/install_resources.sh
```

### 更新资源文件
```bash
# 从 GitHub 更新资源文件
git pull origin main

# 重新安装资源
./scripts/install_resources.sh
```

## 📁 项目结构

```
VabHub-Resources/
├── config/                 # 配置文件模板
│   ├── config.example.yaml
│   ├── categories.yaml
│   ├── classifiers.yaml
│   └── services.json
├── data/                  # 数据模板
│   ├── media_database.json
│   ├── user_profiles.json
│   └── plugin_templates/
├── docs/                  # 文档资源
│   ├── api/
│   ├── tutorials/
│   └── examples/
├── binaries/              # 平台二进制文件
│   ├── linux/
│   ├── windows/
│   ├── macos/
│   └── docker/
├── scripts/               # 工具脚本
│   ├── install_resources.sh
│   ├── update_resources.sh
│   └── validate_resources.sh
└── README.md
```

## 🔧 资源类型

### 配置文件模板
- **config.example.yaml** - 主配置文件模板
- **categories.yaml** - 媒体分类配置
- **classifiers.yaml** - 智能分类器配置
- **services.json** - 服务配置

### 数据模板
- **media_database.json** - 媒体数据库模板
- **user_profiles.json** - 用户配置模板
- **plugin_templates/** - 插件开发模板

### 平台二进制文件
- **Linux** - Linux 平台专用二进制文件
- **Windows** - Windows 平台专用二进制文件  
- **macOS** - macOS 平台专用二进制文件
- **Docker** - Docker 容器内使用的二进制文件

### 文档资源
- **API 文档** - OpenAPI 规范文件
- **教程文档** - 使用教程和示例
- **开发文档** - 开发指南和最佳实践

## 📊 配置文件说明

### 主配置文件模板
```yaml
# config.example.yaml
server:
  host: "0.0.0.0"
  port: 8090
  workers: 4

database:
  type: "postgresql"
  host: "localhost"
  port: 5432
  name: "vabhub"
  username: "vabhub"
  password: "${DB_PASSWORD}"

media:
  library_path: "/media"
  supported_formats:
    - "mp4"
    - "mkv"
    - "avi"
    - "mov"
  
plugins:
  enabled: true
  auto_update: true
  install_path: "./plugins"
```

### 分类配置
```yaml
# categories.yaml
categories:
  movie:
    name: "电影"
    patterns:
      - "*电影*"
      - "*Movie*"
    
  tv_show:
    name: "电视剧"
    patterns:
      - "*剧集*"
      - "*TV*"
      - "*Season*"
```

## 🚀 部署和使用

### 开发环境
```bash
# 1. 克隆资源仓库
git clone https://github.com/vabhub/vabhub-resources.git

# 2. 安装资源文件
cd vabhub-resources
./scripts/install_resources.sh

# 3. 启动开发服务
cd ../VabHub-Core
python start.py
```

### 生产环境
```bash
# 使用 Docker 部署时，资源文件会自动复制
cd VabHub-Deploy
docker-compose up -d
```

### 资源验证
```bash
# 验证资源文件完整性
./scripts/validate_resources.sh

# 检查资源版本
./scripts/check_version.sh
```

## 🔌 平台适配

### Linux 平台
```bash
# Linux 专用二进制文件
binaries/linux/ffmpeg
binaries/linux/ffprobe
binaries/linux/mediainfo
```

### Windows 平台
```cmd
# Windows 专用二进制文件
binaries\windows\ffmpeg.exe
binaries\windows\ffprobe.exe
binaries\windows\mediainfo.exe
```

### macOS 平台
```bash
# macOS 专用二进制文件
binaries/macos/ffmpeg
binaries/macos/ffprobe
binaries/macos/mediainfo
```

## 📋 资源管理

### 版本控制
- 使用语义化版本控制 (SemVer)
- 每个资源文件包含版本信息
- 支持资源文件的增量更新

### 依赖管理
```json
{
  "name": "vabhub-resources",
  "version": "1.0.0",
  "dependencies": {
    "vabhub-core": ">=1.0.0",
    "vabhub-plugins": ">=1.0.0"
  },
  "platforms": ["linux", "windows", "macos"]
}
```

### 更新策略
- 定期从上游源更新二进制文件
- 配置文件变更时提供迁移脚本
- 保持向后兼容性

## 🔗 相关仓库

- [VabHub-Core](https://github.com/vabhub/vabhub-core) - 后端核心服务
- [VabHub-Frontend](https://github.com/vabhub/vabhub-frontend) - 前端界面
- [VabHub-Plugins](https://github.com/vabhub/vabhub-plugins) - 插件系统
- [VabHub-Deploy](https://github.com/vabhub/vabhub-deploy) - 部署配置

## 🤝 贡献指南

欢迎提交资源文件和改进！

### 资源提交规范
- 配置文件使用 YAML 格式
- 二进制文件按平台分类
- 提供完整的文档说明
- 包含版本信息

### 开发流程
```bash
# 1. Fork 仓库
# 2. 克隆到本地
git clone https://github.com/your-username/vabhub-resources.git

# 3. 创建开发分支
git checkout -b feature/your-resource

# 4. 添加资源文件
# 按照平台和类型分类存放

# 5. 更新安装脚本
# 修改 scripts/install_resources.sh

# 6. 提交更改
git commit -m "feat: add your resource"

# 7. 推送到远程
git push origin feature/your-resource

# 8. 创建 Pull Request
```

### 测试要求
- 验证配置文件语法正确性
- 测试二进制文件兼容性
- 确保跨平台一致性
- 提供测试用例

## 📄 许可证

本项目采用 MIT 许可证 - 详见 [LICENSE](LICENSE) 文件。

## 📞 支持

- 文档: [VabHub Wiki](https://github.com/vabhub/vabhub-wiki)
- 问题: [GitHub Issues](https://github.com/vabhub/vabhub-resources/issues)
- 讨论: [GitHub Discussions](https://github.com/vabhub/vabhub-resources/discussions)