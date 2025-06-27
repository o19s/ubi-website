# UBI News

## [UBI released in OpenSearch 3.1](https://opensearch.org/blog/get-started-with-opensearch-3-1/) - June 24, 2025

OpenSearch 3.1 releases with `opensearch-ubi` plugin included and new Search Relevance Workbench that delivers implicit judgments using UBI data.

## [Amazon OpenSearch Ingestion blueprint](tools.md#amazon-opensearch-ingestion-blueprint) - January 27, 2025

A blueprint yaml is now available for creating an Amazon OpenSearch Ingestion pipeline to facilitate persisting of UBI queries and events.

## [OpenSearch 2.18.0.1 UBI Plugin](https://github.com/opensearch-project/user-behavior-insights/releases/tag/2.18.0.1) - November 19, 2024

* Adding an API endpoint to initialize the plugin and create the UBI indexes
* Add query_id to the events mapping
* Change user_query to be a keyword

## [OpenSearch 2.18.0.0 UBI Plugin](https://github.com/opensearch-project/user-behavior-insights/releases/tag/2.18.0.0) - November 15, 2024

* Capturing application in the events
* Changing the timestamp to strict_date_time for consistency
* Handling msearch requests

## UBI 1.2.0 Announced - October 25, 2024

This release introduces a formal application element to both queries and events so you can distingus different sources of queries and their follow on events. Think type-ahead and search as two common applications.  We also formalize that the timestamps are ISO 8601 formatted. 

Learn more about the changes in version 1.2 of the UBI standard at [https://github.com/o19s/ubi/releases/tag/v1.2.0](https://github.com/o19s/ubi/releases/tag/v1.2.0).

## Initial UBI Plugin for Elasticsearch - October 9, 2024

The initial code for a [UBI plugin for Elasticsearch](https://github.com/o19s/user-behavior-insights-elasticsearch) is now available.

## OpenSearch 2.17.1 UBI Plugin - October 4, 2024

The UBI plugin for OpenSearch 2.17.1 is now available.

See what's new and download it at [https://github.com/opensearch-project/user-behavior-insights/releases/tag/2.17.1.0](https://github.com/opensearch-project/user-behavior-insights/releases/tag/2.17.1.0).

## UBI 1.1.0 Announced - August 31, 2024

First release with third party users looking to leverage UBI. This release is primarily adding things we initially decided to skip, and being more relaxed in our requirements for validation.

Learn more about the changes in version 1.1.0 of the UBI standard at [https://github.com/o19s/ubi/releases/tag/v1.1.0](https://github.com/o19s/ubi/releases/tag/v1.1.0).

## OpenSearch 2.16.0 UBI Plugin - August 20, 2024

The UBI plugin for OpenSearch 2.16.0 is now available.

See what's new and download it at [https://github.com/opensearch-project/user-behavior-insights/releases/tag/2.16.0.0](https://github.com/opensearch-project/user-behavior-insights/releases/tag/2.16.0.0).

## OpenSearch 2.15.0 UBI Plugin - June 27, 2024

The UBI plugin for OpenSearch 2.15.0 is now available.

See what's new and download it at [https://github.com/opensearch-project/user-behavior-insights/releases/tag/2.15.0.0](https://github.com/opensearch-project/user-behavior-insights/releases/tag/2.15.0.0).

## UBI 1.0.0 Announced - June 14, 2024

This is the first release of the User Behavior Insights specification that supports tracking of user queries and subsequent actions. Using this schema allows you to validate that your query data and event data are UBI compliant.

Learn more about the changes in version 1.0.0 of the UBI standard at [https://github.com/o19s/ubi/releases/tag/v1.0.0](https://github.com/o19s/ubi/releases/tag/v1.0.0).
