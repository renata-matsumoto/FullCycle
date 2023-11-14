FROM golang:1.21-alpine3.18 as builder

WORKDIR /app

COPY . .

RUN go build -o /main main.go

EXPOSE 8080

FROM scratch

WORKDIR /

COPY --from=builder /main /main

EXPOSE 8080

ENTRYPOINT [ "/main" ]

