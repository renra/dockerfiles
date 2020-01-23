FROM golang:1.14-rc-buster

RUN apt -y update && apt -y install build-essential git

WORKDIR /opt
RUN git clone https://github.com/gohugoio/hugo.git
WORKDIR /opt/hugo
RUN go install --tags extended
WORKDIR /go
