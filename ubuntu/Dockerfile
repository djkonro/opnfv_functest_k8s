FROM ubuntu:latest

ENV PATH=/usr/lib/go-1.9/bin:$PATH
ENV GOROOT=/usr/lib/go-1.9
ENV GOPATH=/home/go

#use local k8s clone for testing
COPY kubernetes $GOPATH/src/k8s.io/kubernetes

RUN mkdir $GOPATH/bin && mkdir $GOPATH/pkg && apt-get update && apt-get install software-properties-common -y && add-apt-repository ppa:gophers/archive && apt-get update && apt-get install make rsync bash golang-1.9-go -y
