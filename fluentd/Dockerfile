# FROM fluent/fluentd:v1.15-1

# # Use root account to use apk

# # below RUN includes plugin as examples elasticsearch is not required
# # you may customize including plugins as you wish
# RUN apk add --no-cache --update --virtual .build-deps \
#     sudo build-base ruby-dev \
#     && RUN ["gem", "install", "fluent-plugin-elasticsearch", "--no-document", "--version", "6.3.1"]\
#     && sudo gem install fluent-plugin-elasticsearch \
#     && sudo gem sources --clear-all \
#     && apk del .build-deps \
#     && rm -rf /tmp/* /var/tmp/* /usr/lib/ruby/gems/*/cache/*.gem

FROM fluent/fluentd:v1.15-1
USER root
RUN gem install elasticsearch -v 7.6.0
# RUN gem install fluent-plugin-elasticsearch -v 7.6.0
RUN gem install fluent-plugin-elasticsearch -v 4.1.1
RUN gem install fluent-plugin-rewrite-tag-filter
RUN gem install fluent-plugin-multi-format-parser
USER fluent