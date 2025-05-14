FROM node:22-alpine

RUN apk add --no-cache git curl

WORKDIR /app

RUN git clone https://github.com/lucide-icons/lucide.git

WORKDIR /app/lucide

RUN npm install -g pnpm

RUN pnpm install

WORKDIR /app/lucide/docs

RUN pnpm run build

EXPOSE 4173

CMD ["pnpm", "run", "docs:preview"]