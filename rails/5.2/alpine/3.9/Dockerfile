FROM ruby:2.5-alpine3.9

RUN apk add --update alpine-sdk nodejs npm tzdata

RUN gem install rails -v 5.2.2.1
RUN gem install nokogiri

WORKDIR /app
