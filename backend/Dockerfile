FROM ruby:3.4.4-slim-bookworm

RUN apt-get update -qq \
    && apt-get install -y --no-install-recommends \
    build-essential \
    libpq-dev \
    nodejs \
    libyaml-dev \
    && rm -rf /var/lib/apt/lists/*

WORKDIR /app

COPY Gemfile Gemfile.lock ./

RUN gem install rails && bundle install

COPY . .

CMD ["rails", "s"]