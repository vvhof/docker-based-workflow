FROM ruby:2.2

RUN apt-get update && apt-get install -y git \
	&& wget -qO- https://get.docker.com/ | sh \
 	&& rm -rf /var/lib/apt/lists/*

RUN mkdir /app
WORKDIR /app
ADD ["Gemfile", "Gemfile.lock", "/app/"]
RUN bundle install
ADD . /app
RUN chmod +x /app/event_converter.rb
ENTRYPOINT ruby /app/event_converter.rb
