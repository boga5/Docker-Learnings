#stage 1 pulling the code form Azure DevOps
FROM alpine:latest as pull_code
RUN apk add git
COPY ./.ssh/id_rsa ~/.ssh/
RUN git clone clt-adeb547c-ba74-4d1d-954f-57d8cebb4e40@vs-ssh.visualstudio.com:v3/clt-adeb547c-ba74-4d1d-954f-57d8cebb4e40/FearUp/FearUp /boga_app/
RUN pwd && ls -la 

#stage 2 pulling the node.js image from Docker Hub
FROM node:alpine as build_code
COPY --from=pull_code /app/PearUp_Web /web
WORKDIR /web
RUN npm install . && npm build . && ls -la
RUN ng serve

