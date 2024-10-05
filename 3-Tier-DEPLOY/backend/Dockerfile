FROM node:14.15.4-alpine3.12 AS build

WORKDIR /app

COPY package*.json ./

RUN npm install

COPY . .

FROM gcr.io/distroless/nodejs:14 AS production

WORKDIR /app


COPY --from=build /app /app


EXPOSE 8082


CMD ["index.js"]