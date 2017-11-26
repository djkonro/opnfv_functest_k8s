FROM golang:1.9.2-alpine3.6

#use local k8s clone for testing
COPY kubernetes $GOPATH/src/k8s.io/kubernetes

RUN apk --no-cache add --update make bash \
        grep gcc rsync linux-headers musl-dev findutils \
        && cd $GOPATH/src/k8s.io/kubernetes && \
        make WHAT=test/e2e/e2e.test
