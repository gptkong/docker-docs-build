FROM node:22-alpine AS builder

RUN apk add --no-cache git

WORKDIR /app

RUN git clone -b v6.0.0 https://github.com/vitejs/docs-cn.git

WORKDIR /app/docs-cn

RUN npm install -g pnpm

RUN pnpm install

RUN pnpm run build

FROM nginx:alpine

COPY --from=builder /app/docs-cn/.vitepress/dist /usr/share/nginx/html

EXPOSE 80

CMD ["nginx", "-g", "daemon off;"]
