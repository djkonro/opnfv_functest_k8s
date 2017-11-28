FROM opnfv/functest-core

ENV GOPATH=/home/go

#use local k8s clone for testing
COPY kubernetes $GOPATH/src/k8s.io/kubernetes

RUN apk --no-cache add --update make bash go \
        grep gcc rsync linux-headers musl-dev findutils \
        && cd $GOPATH/src/k8s.io/kubernetes && \
        make WHAT=test/e2e/e2e.test
