FROM golang:1.9.2-alpine3.6

COPY kubernetes src/k8s.io/kubernetes #use local k8s clone for testing

RUN apk --no-cache add --update make bash gcc rsync
