FROM elasticsearch:7.2.0

ENV script.painless.regex.enabled=true
ENV node.ml=false
ENV xpack.ml.enabled=false
ENV discovery.type=single-node
ENV xpack.security.enabled=true

RUN printf "y" | /usr/share/elasticsearch/bin/elasticsearch-keystore create

ARG es_password

RUN printf $es_password | /usr/share/elasticsearch/bin/elasticsearch-keystore add --stdin "bootstrap.password"
