# syntax=docker/dockerfile:1

FROM node:18.1.0
ENV NODE_ENV=production

ENV LANG en_US.UTF-8
ENV LC_ALL en_US.UTF-8

RUN apt-get update
RUN apt-get -y install python3 python3-nacl python3-pip libffi-dev
RUN pip3 install ansible
RUN ansible --version

WORKDIR /app

COPY ["package.json", "package-lock.json*", "./"]

RUN npm install --production

COPY . .

EXPOSE 8080
CMD [ "node", "server.js" ]
