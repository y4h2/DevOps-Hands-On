FROM golang:1.13.5-alpine3.10 as build-env

WORKDIR /app
COPY . .
RUN apk add --update --no-cache ca-certificates git &&\
    go mod download

RUN CGO_ENABLED=0 GOOS=linux GOARCH=amd64 go build -o /app/app

# min
FROM scratch
EXPOSE 2112

COPY --from=build-env /app/app /app/app
ENTRYPOINT ["/app/app"]