FROM debian:latest

RUN apt-get -y update && apt-get -y install python curl postgresql-client && \
  apt-get install -qy locales locales-all && \
  rm -rf /var/lib/apt/lists/*

RUN locale-gen en_GB.UTF-8

ENV LC_ALL=en_GB.UTF-8
ENV LANG=en_GB.UTF-8
ENV LANGUAGE=en_GB.UTF-8

ENV version=346.0.0
ENV download_target=google-cloud-sdk-${version}-linux-x86_64.tar.gz
ENV dir /google-cloud-sdk/bin

RUN curl -O https://dl.google.com/dl/cloudsdk/channels/rapid/downloads/${download_target} && \
  tar xz -f ${download_target} && \
  rm -rf ${download_target} && \
  curl -O https://dl.google.com/cloudsql/cloud_sql_proxy.linux.amd64 && \
  mv cloud_sql_proxy.linux.amd64 ${dir}/cloud_sql_proxy && \
  chmod +x ${dir}/cloud_sql_proxy && \
  ln -s ${dir}/cloud_sql_proxy /usr/local/bin/cloud_sql_proxy && \
  ln -s ${dir}/gcloud /usr/local/bin/gcloud && \
  ${dir}/gcloud components install beta
