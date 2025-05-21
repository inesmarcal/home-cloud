FROM node:23.11.1-alpine3.21

WORKDIR /usr/src/app/server

COPY package*.json ./

RUN npm install

COPY . .

CMD ["npm", "start"]
