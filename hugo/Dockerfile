FROM golang:1.14-rc-buster

RUN apt -y update && apt -y install build-essential git

RUN mkdir -p /go/src
WORKDIR /go/src
RUN git clone https://github.com/gohugoio/hugo.git
WORKDIR /go/src/hugo
RUN go install --tags extended
WORKDIR /go
