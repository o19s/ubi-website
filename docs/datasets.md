# Datasets

This page lists datasets and data generation utilities for use with UBI.

When working to integrate with UBI it can be helpful to have data in the UBI format to design and develop against.

Refer to the [Samples](https://github.com/o19s/ubi/tree/main/samples) for JSON files illustrating events and queries in the UBI format.

## UBI Data Generator

The [UBI Data Generator](https://github.com/opensearch-project/user-behavior-insights/tree/main/ubi-data-generator) generates UBI data from the [Amazon ESCI dataset](https://github.com/amazon-science/esci-data). The generated UBI data can be exported as CSV and imported into a search engine index.

## UBI Chorus Data Generator

The [UBI Chorus Data Generator](https://github.com/o19s/opensearch-search-quality-evaluation/tree/main/data/ubi-chorus-data-generator) creates fake, random UBI data and indexes it into OpenSearch. The randomly generated data is useful for development and debugging of UBI tools and plugins.