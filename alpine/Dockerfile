FROM golang:1.9.2-alpine3.6

FROM opnfv/functest-core 

ENV GOPATH=/home/go
ENV GOROOT=/usr/local/go
ENV PATH=$PATH:$GOROOT/bin
COPY --from=0 /usr/local/go /usr/local/go

RUN apk --no-cache add --update make bash gcc \
        grep rsync linux-headers musl-dev findutils && \
		git clone https://github.com/kubernetes/kubernetes $GOPATH/src/k8s.io/kubernetes\
        && cd $GOPATH/src/k8s.io/kubernetes && \
        make WHAT=test/e2e/e2e.test
