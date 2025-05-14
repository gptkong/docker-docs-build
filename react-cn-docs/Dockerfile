FROM node:22-alpine

RUN apk add --no-cache git curl

WORKDIR /app

RUN git clone https://github.com/reactjs/zh-hans.react.dev.git

WORKDIR /app/zh-hans.react.dev

RUN yarn

RUN yarn run build

EXPOSE 3000

CMD ["yarn", "run", "start"]