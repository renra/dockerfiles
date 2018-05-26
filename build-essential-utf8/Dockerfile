FROM renra/build-essential:stretch

RUN apt-get -qy update && \
  apt-get install -qy locales locales-all && \
  rm -rf /var/lib/apt/lists/*

RUN locale-gen en_GB.UTF-8

ENV LC_ALL=en_GB.UTF-8
ENV LANG=en_GB.UTF-8
ENV LANGUAGE=en_GB.UTF-8
