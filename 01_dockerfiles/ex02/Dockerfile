FROM ruby

LABEL name="ft-rails"

RUN apt-get update && apt-get -y upgrade; \
	apt-get install build-essential nodejs -y; \
	gem install rails;

RUN mkdir /opt/app
WORKDIR /opt/app

ONBUILD COPY app/ /opt/app
ONBUILD RUN bundle install
ONBUILD RUN rake db:migrate
ONBUILD RUN rake db:seed
