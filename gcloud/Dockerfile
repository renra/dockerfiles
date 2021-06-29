FROM debian:latest

RUN apt-get -y update && apt-get -y install python curl postgresql-client

RUN curl -O https://dl.google.com/dl/cloudsdk/channels/rapid/downloads/google-cloud-sdk-346.0.0-linux-x86_64.tar.gz
RUN tar xz -f google-cloud-sdk-346.0.0-linux-x86_64.tar.gz

ENV dir /google-cloud-sdk/bin
RUN ${dir}/gcloud components install beta

RUN curl -O https://dl.google.com/cloudsql/cloud_sql_proxy.linux.amd64 && mv cloud_sql_proxy.linux.amd64 ${dir}/cloud_sql_proxy && chmod +x ${dir}/cloud_sql_proxy

RUN ln -s ${dir}/cloud_sql_proxy /usr/local/bin/cloud_sql_proxy
RUN ln -s ${dir}/gcloud /usr/local/bin/gcloud
