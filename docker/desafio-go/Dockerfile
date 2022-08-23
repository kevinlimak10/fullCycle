FROM golang:alpine AS builder

WORKDIR /go/src/app

COPY . .

RUN go mod init && \
    go build -o hello .


FROM hello-world:latest

COPY --from=builder /go/src/app/hello /go/src/app/hello

CMD [ "/go/src/app/hello"]
