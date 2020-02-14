FROM node:10-alpine
RUN yarn install -g
RUN npm rebuild node-sass
RUN apk upgrade --update --no-cache \
    && apk add git