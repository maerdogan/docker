FROM docker.io/alpine:latest

RUN apk update && apk add busybox-extras

CMD exec /bin/bash  "trap : TERM INT; sleep infinity & wait"
