# 使用官方的Alpine Linux作为基础镜像
FROM alpine:latest

# 为了clone仓库，需要安装git
RUN apk add --no-cache git

# 克隆特定的分支到一个临时目录
RUN git clone --branch gh-pages --depth=1 https://github.com/alibaba/hooks.git /tmp/hooks

# 创建一个新的阶段来构建最小的Nginx镜像
FROM nginx:alpine

# 将克隆的内容复制到Nginx的html目录
COPY --from=0 /tmp/hooks /usr/share/nginx/html

# 添加自定义Nginx配置
COPY nginx.conf /etc/nginx/conf.d/default.conf

# 暴露Nginx的默认端口
EXPOSE 80

# 启动Nginx服务器
CMD ["nginx", "-g", "daemon off;"]