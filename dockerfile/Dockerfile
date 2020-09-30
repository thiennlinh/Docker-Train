FROM ubuntu:18.04

RUN apt-get update && apt-get install -y wget curl \
    build-essential git git-core \
    zlib1g-dev libssl-dev libreadline-dev libyaml-dev libsqlite3-dev sqlite3 libxml2-dev libxslt1-dev

RUN cd /tmp &&\
  wget -O ruby-install-0.6.1.tar.gz https://github.com/postmodern/ruby-install/archive/v0.6.1.tar.gz &&\
  tar -xzvf ruby-install-0.6.1.tar.gz &&\
  cd ruby-install-0.6.1/ &&\
  make install

RUN ruby-install ruby 2.7.0

ENV PATH /opt/rubies/ruby-2.7.0/bin:$PATH

RUN echo "install: --no-document\nupdate: --no-document" > ~/.gemrc

RUN gem install bundler

CMD [ "ruby", "--version" ]
