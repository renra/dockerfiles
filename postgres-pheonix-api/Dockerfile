FROM elixir:1.5.1-slim

RUN apt-get -qq -y update && \
  yes | mix local.hex && \
  yes | mix archive.install https://github.com/phoenixframework/archives/raw/master/phx_new.ez


