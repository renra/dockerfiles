FROM renra/ruby-node-postgres:ruby2.1.7-node4.5.0-postgres9.4.12

RUN apt-get -qq -y update && \
  apt-get install -qq -y  \
  libicu-dev \
  libfontconfig1-dev \
  libjpeg-dev \
  libfreetype6 && \
  rm -rf /var/lib/apt/lists/*

RUN npm install -g phantomjs@2.1
