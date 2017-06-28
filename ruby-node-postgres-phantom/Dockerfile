FROM renra/ruby-node-postgres:ruby2.1.7-node4.5.0-postgres9.4

RUN apt-get -qq -y update

RUN apt-get install -qq -y  \
  libicu-dev \
  libfontconfig1-dev \
  libjpeg-dev \
  libfreetype6

RUN npm install -g phantomjs@1.9.8
