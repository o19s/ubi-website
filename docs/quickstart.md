# Quick Start

![Chorus](img/chorus_plus_ubi.png)

The Chorus project provides a UBI reference implementation that you can use to build on or model your search stack. Chorus uses OpenSearch, but the instructions generally apply also to Elasticsearch.

First, clone the Chorus repository.

```
git clone https://github.com/o19s/chorus-opensearch-edition.git
```

Next, the quickstart script will launch OpenSearch, download and index the sample product data for the `ecommerce` index:

```
./quickstart.sh
```

**TODO: Insert some steps here.**

When finished, you can clean up the Docker resources:

```
docker compose down -v
```