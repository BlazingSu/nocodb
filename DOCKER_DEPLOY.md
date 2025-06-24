# 一键 Docker 部署指南

此仓库提供了 `deploy.sh` 脚本和 `docker-compose/simple-deploy.yml`，可以在不修改源码的情况下快速部署 NocoDB。

## 步骤

1. **安装 Docker 与 Docker Compose**
   - Ubuntu/Debian 示例：
     ```bash
     sudo apt update
     sudo apt install docker.io docker-compose -y
     ```
2. **拉取代码**
   ```bash
   git clone https://github.com/nocodb/nocodb.git
   cd nocodb
   ```
3. **执行部署脚本**
   ```bash
   ./deploy.sh
   ```
   该脚本会按 `docker-compose/simple-deploy.yml` 创建并启动容器。

## 默认配置

- 数据库密码：`123456`
- `NC_PUBLIC_URL` 指向服务器地址 `http://42.192.204.166`
- 容器对外暴露端口 `80`，访问 `http://42.192.204.166` 即可打开 NocoDB。
- 通过设置 `LANG=zh_CN.UTF-8`，界面默认语言为中文。

## 停止或更新

- 停止服务：`docker compose -f docker-compose/simple-deploy.yml down`
- 重新部署：重新执行 `./deploy.sh`
