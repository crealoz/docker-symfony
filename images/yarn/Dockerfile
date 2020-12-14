ARG SRC_PATH_CONTAINER=$SRC_PATH_CONTAINER

FROM node:10-alpine
RUN yarn install -g
RUN npm rebuild node-sass
RUN cd ${SRC_PATH_CONTAINER}
RUN npm install gulp
RUN apk upgrade --update --no-cache \
    && apk add git