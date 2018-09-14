FROM renra/elixir:1.7-stretch

RUN apt-get -qq -y update && \
  apt-get install -qy inotify-tools && \
  rm -rf /var/lib/apt/lists/*

RUN yes | mix local.hex && \
  yes | mix archive.install https://github.com/phoenixframework/archives/raw/master/phx_new-1.3.2.ez

CMD ["bin/bash"]
