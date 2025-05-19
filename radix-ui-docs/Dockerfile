FROM node:22-alpine

RUN apk add --no-cache git

WORKDIR /app

RUN git clone https://github.com/radix-ui/website.git

WORKDIR /app/website

RUN npm install -g pnpm

RUN pnpm install

RUN pnpm run build

EXPOSE 3000

CMD ["pnpm", "run", "start"]