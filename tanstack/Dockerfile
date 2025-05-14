# 使用 Node.js 22 Alpine 镜像，Alpine 是一个轻量级的 Linux 发行版
FROM node:22-alpine

# 创建 tanstack 目录并设置为工作目录
RUN mkdir -p /tanstack
WORKDIR /tanstack

# 安装 git，因为 Alpine 镜像默认不包含 git
RUN apk add --no-cache git

# 拉取各个项目
RUN git clone https://github.com/gptkong/tanstack.com.git
RUN git clone https://github.com/TanStack/query.git
RUN git clone https://github.com/TanStack/router.git
RUN git clone https://github.com/TanStack/table.git

# 进入 tanstack.com 目录
WORKDIR /tanstack/tanstack.com

# 安装依赖，使用 pnpm
RUN npm install -g pnpm
RUN pnpm i
RUN pnpm build

# 暴露 3000 端口
EXPOSE 3000

# 运行开发服务器
CMD ["node", ".output/server/index.mjs"]