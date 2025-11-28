FROM node:22-alpine


EXPOSE 8080

WORKDIR /app

COPY package*.json ./

RUN npm install

COPY . .

CMD ["node", "server.js"]

