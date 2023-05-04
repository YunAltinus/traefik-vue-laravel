FROM node:18-alpine

WORKDIR /var/www/html

COPY package*.json yarn.lock ./
COPY vite.config.js ./vite.config.js

RUN yarn

# COPY ./ ./

ENV HOST=0.0.0.0

EXPOSE 5173

CMD ["yarn", "dev", "--host"]