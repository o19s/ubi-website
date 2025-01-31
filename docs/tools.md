# UBI Tools and Plugins

There are several tools and plugins available to support UBI data capture and analysis.

* :material-link: [Amazon OpenSearch Ingestion blueprint](#amazon-opensearch-ingestion-blueprint) for creating Amazon OpenSearch Ingestion pipeline to support persisting UBI events and queries.
* :material-link: [OpenSearch UBI plugin](#ubi-plugin-for-opensearch) for facilitating the capture of UBI queries and events in OpenSearch.
* :material-link: [Elasticsearch UBI Plugin](#ubi-plugin-for-elasticsearch) for facilitating the capture of UBI queries and events in Elasticsearch.
* :material-link: [Apache Solr implementation](https://github.com/apache/solr/pull/2452) for facilitating the capture of UBI queries and events in Apache Solr.

## Amazon OpenSearch Ingestion Blueprint

The Amazon OpenSearch Ingestion UBI blueprint is a pre-defined configuration that allows for creating an OpenSearch Ingestion pipeline that ingests UBI queries and events.

* [The AWS OpenSearch Ingestion blueprint yaml](https://github.com/o19s/opensearch-search-quality-evaluation/blob/main/osi/blueprint.yaml)
* [Terraform scripts for creating the full Amazon OpenSearch Ingestion pipeline](https://github.com/o19s/opensearch-search-quality-evaluation/tree/main/osi)

The blueprint creates a pipeline that facilitates receiving and storing UBI queries and events. The blueprint creates:

* An S3 sink for UBI queries and events.
* An OpenSearch sink for UBI queries and events.

UBI queries and events that are received via an HTTP source are routed to one of the above sinks based on the value of the `type` value in the received JSON. For example, the script below sends a UBI `event` to the pipeline:

### Sending Queries and Events to the Pipeline

The example commands below uses `awscurl` from the [awscurl](https://github.com/okigan/awscurl) open source project.

The following command illustrates how to send a UBI `event` to the pipeline:

```
awscurl \
	--service osis \
	--region ${AWS_REGION} \
	--profile ${AWS_PROFILE} \
	-X POST \
	-H "Content-Type: application/json" \
	-d '[{"type": "event", "action_name": "click", "query_id": "99999999-4455-6677-8899-aabbccddeeff", "event_attributes": {"position": {"ordinal": 1}, "object": {"object_id": "1234", "object_id_field": "ean", "user_id": "abc"}}}]' \
	https://${OSIS_PIPELINE_ENDPOINT_URL}/ubi
```

And the similar command below sends a UBI `query` to the pipeline:

```
awscurl \
	--service osis \
	--region ${AWS_REGION} \
	--profile ${AWS_PROFILE} \
	-X POST \
	-H "Content-Type: application/json" \
	-d '[{"type": "query", "user_query": "computer", "query_id": "00112233-4455-6677-8899-aabbccddeeff"}]' \
	https://${OSIS_PIPELINE_ENDPOINT_URL}/ubi
```

Note the `type` property in the body of each request. The `type` property is used by the pipeline to route the request to either a query or event sink.

After this query and event are sent, they will be delivered to the appropriate sink and viewable in the Amazon S3 bucket and in the Amazon OpenSearch index.

### Viewing the UBI Events and Queries

Once UBI queries and events are sent to the pipeline and received, the pipeline will store the queries and events in an S3 bucket and in an OpenSearch index. The example command below illustrates how to search the `ubi_events` index to view the indexed UBI events.

```
awscurl \
	"https://${OPENSEARCH_ENDPOINT}/ubi_events/_search" \
	-X GET \
	--region ${AWS_REGION} \
	--service es \
	--profile ${AWS_PROFILE} | jq
```

Indexed queries can be viewed by changing the `ubi_events` index to the `ubi_queries` index.

## UBI Plugin for OpenSearch

The [OpenSearch UBI plugin](https://www.github.com/opensearch-project/user-behavior-insights) facilitates persisting client-side events (e.g. item clicks, scroll depth) and OpenSearch queries for the purpose of analyzing the data to improve search relevance and user experience. The concepts of UBI and this plugin project was originally proposed in the [OpenSearch UBI RFC](https://github.com/opensearch-project/OpenSearch/issues/12084).

Note that the UBI plugin is *not* required to use UBI. You can use any method of persisting queries and events into OpenSearch. The [UBI JavaScript Collector](https://github.com/opensearch-project/user-behavior-insights/blob/main/ubi-javascript-collector/ubi.js) is an example.

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

Note that the UBI plugin is *not* required to use UBI. You can use any method of persisting queries and events into Elasticsearch. The [UBI JavaScript Collector](https://github.com/opensearch-project/user-behavior-insights/blob/main/ubi-javascript-collector/ubi.js) is an example.

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