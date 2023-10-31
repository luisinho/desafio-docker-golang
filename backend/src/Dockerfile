FROM golang:alpine AS builder

WORKDIR /app

COPY go.mod ./

COPY main.go ./

RUN CGO_ENABLED=0 go build -ldflags '-s -w' main.go

FROM scratch

WORKDIR /

COPY --from=builder /app /

CMD ["./main"]