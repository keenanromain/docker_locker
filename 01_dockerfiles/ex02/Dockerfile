FROM ruby

RUN apt-get update -y && \
	apt-get install build-essential -y && \
	apt-get install nodejs -y

RUN mkdir /opt/app
WORKDIR /opt/app
RUN gem install rails

EXPOSE 3000

ONBUILD COPY . /opt/app
ONBUILD WORKDIR /opt/app

ONBUILD RUN bundle install
ONBUILD RUN rails db:migrate
ONBUILD RUN rails db:seed
