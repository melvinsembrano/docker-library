FROM ruby:2.6-alpine3.9

RUN apk add --update alpine-sdk nodejs npm tzdata

RUN gem install rails -v 6.0.0.rc1
RUN gem install nokogiri

WORKDIR /app
