FROM alpine:latest as certs
RUN apk --update add ca-certificates

FROM golang:latest

ARG USER_UID=10001
USER ${USER_UID}

COPY --from=certs /etc/ssl/certs/ca-certificates.crt /etc/ssl/certs/ca-certificates.crt
COPY otelcontribcol /otelcontribcol
ENTRYPOINT ["/otelcontribcol"]
EXPOSE 4317 4318 8888
