# syntax=docker/dockerfile:1.4
FROM --platform=$BUILDPLATFORM node:18-alpine AS development

WORKDIR /var/www/html

COPY package*.json yarn.lock ./
COPY vite.config.js ./vite.config.js

RUN yarn

# COPY ./ ./

ENV HOST=0.0.0.0

EXPOSE 5173

CMD ["yarn", "dev", "--host"]