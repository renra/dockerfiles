FROM alpine as builder

RUN apk update && apk add dumb-init

FROM busybox

COPY --from=builder /usr/bin/dumb-init /usr/bin/dumb-init
ENTRYPOINT ["/usr/bin/dumb-init", "--"]
