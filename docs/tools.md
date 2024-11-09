# Tools and Plugins

There are several available tools and plugins supporting UBI.

* [OpenSearch UBI plugin](https://www.github.com/opensearch-project/user-behavior-insights)
* [Elasticsearch UBI Plugin](https://github.com/o19s/user-behavior-insights-elasticsearch)
* [Apache Solr implementation](https://github.com/apache/solr/pull/2452)

## UBI Plugin for OpenSearch 

The [OpenSearch UBI plugin](https://www.github.com/opensearch-project/user-behavior-insights) facilitates persisting client-side events (e.g. item clicks, scroll depth) and OpenSearch queries for the purpose of analyzing the data to improve search relevance and user experience. The concepts of UBI and this plugin project was originally proposed in the [OpenSearch UBI RFC](https://github.com/opensearch-project/OpenSearch/issues/12084).

To use the plugin, first [download](https://github.com/opensearch-project/user-behavior-insights/releases) the release appropriate for your version of OpenSearch. Next, install the plugin:

```
bin/opensearch-plugin install file:/opensearch-ubi-1.0.0-os2.14.0.zip
```

With the plugin installed, you can now capture OpenSearch queries:

```
curl -s http://localhost:9200/ecommerce/_search -H "Content-Type: application/json" -d'
 {
  "ext": {
   "ubi": {
    }
   },
   "query": {
     "match": {
       "name": "toner"
     }
   }
 }'
```

And you can send client-side events to OpenSearch:

```
curl -s http://localhost:9200/ecommerce/_search -H "Content-Type: application/json" -d'
 {
  "ext": {
   "ubi": {
    }
   },
   "query": {
     "match": {
       "name": "toner"
     }
   }
 }'
```

To see these events, check the `ubi_queries` and `ubi_events` indexes:

```
curl http://localhost:9200/ubi_queries/_search
curl http://localhost:9200/ubi_events/_search
```

## UBI Plugin for Elasticsearch

The [Elasticsearch UBI Plugin](https://github.com/o19s/user-behavior-insights-elasticsearch) is a fork of the OpenSearch UBI plugin. This plugin provides similar core functionality but other functionality will differ.

To use the plugin, first [download](hhttps://github.com/o19s/user-behavior-insights-elasticsearch/releases) the release appropriate for your version of Elasticsearch. Next, install the plugin:

```
bin/elasticsearch-plugin install file:/elasticsearch-ubi-1.0.0-es2.14.0.zip
```

With the plugin installed, you can now capture OpenSearch queries:

```
curl -s http://localhost:9200/ecommerce/_search -H "Content-Type: application/json" -d'
 {
  "ext": {
   "ubi": {
    }
   },
   "query": {
     "match": {
       "name": "toner"
     }
   }
 }'
```

And you can send client-side events to OpenSearch:

```
curl -s http://localhost:9200/ecommerce/_search -H "Content-Type: application/json" -d'
 {
  "ext": {
   "ubi": {
    }
   },
   "query": {
     "match": {
       "name": "toner"
     }
   }
 }'
```

To see these events, check the `ubi_queries` and `ubi_events` indexes:

```
curl http://localhost:9200/ubi_queries/_search
curl http://localhost:9200/ubi_events/_search
```