FROM golang:1.19.1 AS build

WORKDIR /app

COPY go.mod ./

COPY main.go ./

RUN CGO_ENABLED=0 go build -o /full-go

FROM alpine:latest

WORKDIR /

COPY --from=build /full-go /full-go

CMD ["/full-go"]