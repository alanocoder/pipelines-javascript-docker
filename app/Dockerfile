# syntax=docker/dockerfile:1

FROM node:12.18.1
ENV NODE_ENV=production

RUN apt-get -y install python3-pip
RUN pip3 install ansible

WORKDIR /app

COPY ["package.json", "package-lock.json*", "./"]

RUN npm install --production

COPY . .

EXPOSE 8080
CMD [ "node", "server.js" ]
