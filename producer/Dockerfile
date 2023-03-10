FROM node:16.17.0-alpine3.16 as base

WORKDIR /app
COPY package.json ./
RUN npm install
COPY . .


FROM base as dev

WORKDIR /app
COPY --from=base /app .
RUN apk add bash curl -q
RUN npm install --include=dev


FROM base as prod
WORKDIR /app
RUN npm install typescript@4.8.2 -g
RUN npm install
RUN tsc
CMD ["npm", "start"]
