FROM alpine:3.10.3

RUN apk add --update \
    curl \
    unzip \
    && rm -rf /var/cache/apk/*

ARG VERSION=0.12.12

RUN mkdir terraform-build && \
  cd /terraform-build && \
  curl https://releases.hashicorp.com/terraform/0.12.12/terraform_${VERSION}_linux_amd64.zip > terraform.zip && \
  unzip terraform.zip && \
  rm terraform.zip && \
  mv terraform /usr/local/bin && \
  cd ../ && \
  rmdir terraform-build
