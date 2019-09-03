FROM elasticsearch:6.8.0

# Enable security
ENV discovery.type single-node
ENV xpack.security.enabled true

ARG es_user
ARG es_pass

# Set Password for superuser
RUN elasticsearch-keystore create
RUN echo $es_pass | elasticsearch-keystore add bootstrap.password --stdin
RUN elasticsearch-users useradd $es_user -p $es_pass -r superuser
