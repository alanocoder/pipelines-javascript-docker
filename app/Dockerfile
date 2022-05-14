# syntax=docker/dockerfile:1

FROM node:12.18.1
ENV NODE_ENV=production

WORKDIR /app

RUN python3 --version
RUN uname -a
RUN ls /
RUN python3 -m pip install ansible

COPY ["package.json", "package-lock.json*", "./"]

RUN npm install --production

COPY . .

EXPOSE 8080
CMD [ "node", "server.js" ]
