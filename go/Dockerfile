##
## Build
##
FROM golang:1.16-buster AS build

WORKDIR /app

COPY go/main.go ./main.go

RUN go build -o /ping ./main.go

##
## Deploy
##

FROM gcr.io/distroless/base-debian10

WORKDIR /app

COPY --from=build /ping /ping

ENTRYPOINT ["/ping"]
