FROM node:22-alpine

RUN apk add --no-cache git

WORKDIR /app

RUN git clone https://github.com/shadcn-ui/ui.git

WORKDIR /app/ui

RUN npm install -g pnpm

RUN pnpm install

WORKDIR /app/ui/apps/www

RUN pnpm run build

EXPOSE 3333

CMD ["pnpm", "run", "start"]