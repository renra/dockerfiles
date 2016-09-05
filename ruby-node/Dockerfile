FROM debian:jessie

RUN apt-get -qyy update
RUN apt-get -qyy install build-essential git git-core libcurl3

# Ruby compilation from source

# STEP 1 #
#ENV RUBYDIR /ruby
#
#WORKDIR ${RUBYDIR}
#RUN curl http://cache.ruby-lang.org/pub/ruby/2.1/ruby-2.1.7.tar.gz | tar xvz
#
#WORKDIR ${RUBYDIR}/ruby-2.1.7
#
#RUN ./configure
#RUN make
#RUN make install
#
#WORKDIR /

# STEP 2 #
# docker cp all ruby files into the host together with /usr/local/lib

#COPY ruby/bin/erb /usr/local/bin/
#COPY ruby/bin/gem /usr/local/bin/
#COPY ruby/bin/irb /usr/local/bin/
#COPY ruby/bin/rake /usr/local/bin/
#COPY ruby/bin/rdoc /usr/local/bin/
#COPY ruby/bin/ri /usr/local/bin/
#COPY ruby/bin/ruby /usr/local/bin/
#COPY ruby/bin/testrb /usr/local/bin/
#COPY lib /usr/local/lib

### ###

# node.js compilation from source

# STEP 3 #
#RUN apt-get -y -qq install python
#
#ENV NODEDIR /node
#
#WORKDIR ${NODEDIR}
#RUN curl http://nodejs.org/dist/v4.5.0/node-v4.5.0.tar.gz | tar xvz
#WORKDIR ${NODEDIR}/node-v4.5.0
#
#RUN ./configure
#RUN make
#RUN make install

#WORKDIR /

# STEP 4 #
# docker cp all node files into the host and then copy it back to a fresh container

#COPY node/node /usr/local/bin/node
#
#COPY node/lib /usr/local/lib/node_modules
#COPY node/include /usr/local/include/node
#RUN ln -s /usr/local/lib/node_modules/npm/bin/npm-cli.js /usr/local/bin/npm
