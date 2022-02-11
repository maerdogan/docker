FROM alpine

RUN apk update && apk add busybox-extras
 
CMD exec /bin/bash  "trap : TERM INT; sleep infinity & wait"
