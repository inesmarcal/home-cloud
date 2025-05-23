FROM node:23.11.1-alpine3.21 as builder

WORKDIR /usr/src/app/client

COPY ["package*.json","."]

RUN npm ci

COPY [".", "."]

RUN npm run build

FROM node:23.11.1-alpine3.21

WORKDIR /usr/src/app/client

COPY --from=builder /usr/src/app/client/build .

RUN npm i -g serve

CMD ["serve", "-s", "build", "-l", "3000" ]
