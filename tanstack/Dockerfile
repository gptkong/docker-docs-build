FROM node:22-alpine

RUN mkdir -p /tanstack
WORKDIR /tanstack

RUN apk add --no-cache git

RUN git clone https://github.com/gptkong/tanstack.com.git
RUN git clone https://github.com/TanStack/query.git
RUN git clone https://github.com/TanStack/router.git
RUN git clone https://github.com/TanStack/table.git

WORKDIR /tanstack/tanstack.com

RUN npm install -g pnpm
RUN pnpm i
RUN pnpm build

EXPOSE 3000

CMD ["node", ".output/server/index.mjs"]