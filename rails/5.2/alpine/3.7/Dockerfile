FROM ruby:2.5-alpine3.7

RUN apk add --update alpine-sdk nodejs tzdata

RUN gem install rails -v 5.2 --no-ri --no-rdoc

WORKDIR /app
