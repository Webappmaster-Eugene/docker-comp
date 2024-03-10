FROM golang:alpine as build
WORKDIR /go/bin
COPY . .
RUN nCGO_ENABLED=0 GOOS=linux GOARCH=amd64 go build

FROM scratch
COPY --from=build /go/bin/docker-go /go/bin/docker-go
ENTRYPOINT 'go/bin/docker-go'
EXPOSE 9000