# Write client Dockerfile here
# For instructions, see https://github.com/SnowSuno/wheel-assignment-solution#1-dockerfile-%EC%9E%91%EC%84%B1

# build
FROM node:16-alpine
WORKDIR /usr/src/app

COPY package*.json ./
RUN npm install && npm install -g serve
COPY . .

RUN npm run build

# serve
EXPOSE 3000
ENTRYPOINT ["serve", "-s", "build", "-l", "3000"]
