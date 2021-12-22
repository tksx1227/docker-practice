FROM ruby:2.5
RUN apt-get update && apt-get install -y \
    build-essential \
    libpq-dev \
    nodejs \
    postgresql-client \
    yarn
WORKDIR /rails-app
COPY Gemfile Gemfile.lock /rails-app/
RUN bundle install
