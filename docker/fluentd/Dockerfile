FROM fluent/fluentd:latest
MAINTAINER shigemk2 <i.am.shige@gmail.com>
USER root
WORKDIR /home/fluent
ENV PATH /home/fluent/.gem/ruby/2.2.0/bin:$PATH
RUN apk --update add ca-certificates ruby ruby-dev ruby-irb build-base jemalloc-dev mariadb-dev
RUN gem install fluent-plugin-elasticsearch && \
    gem install fluent-plugin-mysql-replicator

COPY fluent.conf /fluent/etc/fluent.conf
EXPOSE 24224
CMD fluentd -c /fluentd/etc/$FLUENTD_CONF -p /fluentd/plugins $FLUENTD_OPT