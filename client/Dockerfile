# Write client Dockerfile here
# For instructions, see https://github.com/SnowSuno/wheel-assignment-solution#1-dockerfile-%EC%9E%91%EC%84%B1

# build
FROM node:16-alpine as builder
WORKDIR /usr/src/app

COPY package*.json ./
RUN npm install
COPY . .

RUN npm run build

# serve
FROM nginx:alpine
COPY --from=builder /usr/src/app/build /usr/share/nginx/html
COPY nginx.conf /etc/nginx/nginx.conf
