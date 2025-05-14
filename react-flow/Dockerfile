FROM node:22-alpine

RUN apk add --no-cache git

WORKDIR /app

RUN git clone https://github.com/xyflow/web.git

WORKDIR /app/web

RUN npm install -g pnpm

RUN pnpm install

RUN pnpm run build

WORKDIR /app/web/sites/reactflow.dev

EXPOSE 3000

CMD ["pnpm", "run", "start"]