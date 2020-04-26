FROM ruby:2.5.1
MAINTAINER zia <zkamran@student.42.fr>
RUN apt-get -y update && \
	apt-get -y upgrade && \
	apt-get -y install nodejs sqlite3 libsqlite3-dev && \
	gem install rails bundler && \
	apt-get clean && \
	rm -rf /var/lib/apt/lists/*
COPY app /opt/app
WORKDIR /opt/app
ONBUILD RUN bundle update && bundle install
ONBUILD RUN rake db:migrate
ONBUILD RUN rake db:seed
#
