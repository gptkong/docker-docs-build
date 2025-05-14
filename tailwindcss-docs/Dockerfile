FROM node:22-alpine AS base

RUN apk add --no-cache git

RUN corepack enable && corepack prepare pnpm@latest --activate

WORKDIR /app

RUN git clone https://github.com/tailwindlabs/tailwindcss.com.git .

RUN pnpm install --frozen-lockfile

RUN pnpm build

EXPOSE 3000

CMD ["pnpm","run", "start"]