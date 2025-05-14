FROM node:22-alpine

RUN apk add --no-cache git curl

# 设置工作目录
WORKDIR /app

# 克隆指定的 GitHub 仓库
RUN git clone https://github.com/reactjs/zh-hans.react.dev.git

WORKDIR /app/zh-hans.react.dev

# 安装项目依赖
RUN yarn

# 构建项目
RUN yarn run build

# 暴露 3333 端口
EXPOSE 3000

# 启动项目
CMD ["yarn", "run", "start"]