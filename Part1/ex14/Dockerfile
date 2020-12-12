FROM ruby:2.6.0

RUN bundle config --global frozen 1
WORKDIR /usr/src/app
RUN apt-get update && apt-get install -y nodejs 
COPY Gemfile Gemfile.lock ./
RUN gem install bundler
RUN bundle install
COPY . .
RUN rails db:migrate
EXPOSE 3000

CMD ["rails", "s"]


