FROM golang:1.18.1 AS stage1

WORKDIR /app
COPY go.mod ./
COPY main.go ./

RUN go build -o /full-go

FROM gcr.io/distroless/base-debian10

WORKDIR /

COPY --from=stage1 /full-go /full-go

CMD ["/full-go"]