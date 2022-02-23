# Debugging ElasticSearch Health

### Queries:

- Make a health check to get important cluster stats:
```
GET _cat/health?v
```

- Shows the health status, number of documents, and disk usage for each index:

```
GET /_cat/indices?v
```

- Chooses the first unassigned shard that it finds and explains why it cannot be allocated to a node:
```
GET /_cluster/allocation/explain
```


### Bibliographic References:

> https://docs.aws.amazon.com/opensearch-service/latest/developerguide/handling-errors.html#troubleshooting-dashboards-configure-anonymous-access