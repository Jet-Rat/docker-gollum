FROM ruby

RUN apt-get -y update \
	&& apt-get -y install libicu-dev \
	&& gem install gollum \
	&& gem install github-markdown org-ruby \
	&& mkdir /wiki \
	&& rm -rf /var/lib/apt/lists/*

COPY .git /wiki/.git

VOLUME /wiki

WORKDIR /wiki

EXPOSE 80
CMD ["gollum", "--port", "80"]
