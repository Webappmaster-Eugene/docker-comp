FROM golang:alpine as build
WORKDIR /opt/app
ADD . .
RUN nCGO_ENABLED=0 GOOS=linux GOARCH=amd64 go build
CMD ["node", "./dist/apps/main.js"]

FROM scratch
WORKDIR /opt/app
ADD package.json ./
RUN npm install --only=prod