# 启动-中文

## 注意
为什么必须使用Docker
Penpot的开发环境设计为容器化架构,原因包括:

多语言运行时依赖: 开发环境需要同时运行多个语言环境,包括OpenJDK 24、Node.js 22、Rust 1.85、Clojure等

外部服务依赖: 项目依赖PostgreSQL 16、Redis/Valkey、MinIO对象存储、MailCatcher等服务

统一开发环境: Docker确保所有开发者使用相同的工具链和配置

## 命令

```bash
# 拉取开发环境所需的Docker镜像
# 这个命令会下载Penpot开发环境的所有容器镜像,包括PostgreSQL、Redis、MinIO等服务
./manage.sh pull-devenv

# 启动开发环境的后台服务
# 启动PostgreSQL数据库、Redis缓存、MinIO对象存储、MailCatcher邮件服务等依赖服务
# 这些服务会在后台运行,为开发环境提供必要的基础设施
./manage.sh start-devenv

# 进入开发环境容器
# 启动一个交互式的开发容器,在容器内可以运行前端、后端等开发任务
# 容器内已配置好所有开发工具(JDK、Node.js、Rust、Clojure等)
./manage.sh run-devenv
```