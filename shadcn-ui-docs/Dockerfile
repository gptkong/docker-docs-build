# 使用 Alpine 作为基础镜像，Alpine 是一个非常小的 Linux 发行版
FROM node:22-alpine

# 安装 git，因为 Alpine 默认不包含 git
RUN apk add --no-cache git

# 设置工作目录
WORKDIR /app

# 克隆指定的 GitHub 仓库
RUN git clone https://github.com/shadcn-ui/ui.git

# 进入克隆的仓库目录
WORKDIR /app/ui

# 安装 pnpm（Alpine 镜像中默认没有 pnpm）
RUN npm install -g pnpm

# 安装项目依赖
RUN pnpm install

# 进入 www 目录（假设仓库中有 www 目录）
WORKDIR /app/ui/apps/www

# 构建项目
RUN pnpm run build

# 暴露 3333 端口
EXPOSE 3333

# 启动项目
CMD ["pnpm", "run", "start"]