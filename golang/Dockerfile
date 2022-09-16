FROM golang:alpine as builder

WORKDIR /app

RUN go mod init hello

COPY ./hello.go .

RUN go build ./hello.go && \
    rm go.mod && \
    rm hello.go

FROM scratch

WORKDIR /app

COPY --from=builder /app /app

CMD [ "./hello" ]
