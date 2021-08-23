# pull official base image
FROM node:14.16.0-alpine3.13

# add/switch to non-root user
RUN addgroup app && adduser -S -G app app
USER app

# set working directory
WORKDIR /usr/src/app

# install dependencies
COPY package*.json ./
RUN npm install

# copy project
COPY . .

# declare port
EXPOSE 8080