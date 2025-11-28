FROM node:22-alpine

EXPOSE 8081

WORKDIR /app

COPY package*.json ./

RUN npm install

COPY . .

CMD ["npx", "ng", "serve", "--host", "0.0.0.0", "--port", "8081", "--disable-host-check"]
