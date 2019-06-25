# Elasticsearch dockerfiles used on DITAS

## Blueprint Elasticsearch
Elasticsearch used to store blueprints information. User and pass must be defined at build time.

```
docker build -t elasticsearch_blueprint --build-arg es_user=YOUR_USER --build-arg es_pass=YOUR_PASS .
docker run -p 50014:9200 -p 50015:9300 --restart unless-stopped --log-opt max-size=100m -d elasticsearch_blueprint
```

## Metrics Elasticsearch
Elasticsearch used to store metrics information. User and pass must be defined at build time.

```
docker build -t elasticsearch_metrics --build-arg es_user=YOUR_USER --build-arg es_pass=YOUR_PASS .
docker run -p 50035:9200 -p 50036:9300 --restart unless-stopped --log-opt max-size=100m -d elasticsearch_metrics
```