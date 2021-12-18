FROM golang as buildando

WORKDIR /app
ADD . /app
RUN go mod init meugo && go build -o meugo

FROM alpine
WORKDIR /app
COPY --from=buildando /app/meugo /app

ENTRYPOINT ./meugo 