FROM node:21 AS frontend-multistage

WORKDIR /app

COPY . .

RUN npm install

FROM node:21-slim

WORKDIR /app

COPY --from=frontend-multistage /app .

COPY .env.sample .env.local

EXPOSE 5173

CMD ["npm", "run", "dev", "--", "--host"]
