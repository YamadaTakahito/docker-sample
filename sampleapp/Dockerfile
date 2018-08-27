# baseとなるimageはruby:2.5.0
FROM ruby:2.5.0

# appというディレクトリを作成
ENV LANG C.UTF-8
ENV ROOT_PATH /app
RUN mkdir $ROOT_PATH

WORKDIR $ROOT_PATH

# javascript系のgemとmysqlのためにinstall
RUN apt-get update && apt-get install -y nodejs mysql-client

ADD Gemfile $ROOT_PATH/Gemfile
ADD Gemfile.lock $ROOT_PATH/Gemfile.lock
RUN gem install bundler
RUN bundle install --jobs=4
