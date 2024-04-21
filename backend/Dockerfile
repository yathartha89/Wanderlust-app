FROM node:21 AS backend_multistage

WORKDIR /app

COPY . .

RUN npm install

FROM node:21-slim

WORKDIR /app

COPY --from=backend_multistage /app . 

COPY .env.sample .env

EXPOSE 5000

CMD ["npm", "start"]
