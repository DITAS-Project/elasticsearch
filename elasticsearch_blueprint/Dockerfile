FROM elasticsearch:2.4.6

RUN rm -rf /etc/elasticsearch
RUN ln -s /usr/share/elasticsearch/config /etc/elasticsearch

RUN /usr/share/elasticsearch/bin/plugin install license
RUN /usr/share/elasticsearch/bin/plugin install shield

ENV script.inline=true
ENV script.indexed=true

ARG es_user
ARG es_pass

RUN /usr/share/elasticsearch/bin/shield/esusers useradd $es_user -p $es_pass -r admin
