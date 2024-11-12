# User Behavior Insights

## Welcome to User Behavior Insights!

![logo](img/ubi.png)

User Behavior Insights, or UBI, is a [data standard](standard.md) along with a collection of [tools and search engine plugins](tools.md) created to help search engineers gain and utilize an improved understanding of users' actions.

### UBI in Action!

Learn more about UBI through conference presentations. If you have talked about UBI let us know so we can link your talk here, too.

* :material-link: UBI at OpenSearchCon EU 2024 - [Watch the presentation](https://www.youtube.com/watch?v=dH7SPHKpxo0)
* :material-link: UBI at Haystack Conference 2024 - [Your Search Engine Needs a Memory! (presentation and slides)](https://haystackconf.com/us2024/talk-15/)
* :material-link: UBI at MICES 2024 - [Watch the presentation](https://youtu.be/8_4VRtMWtSY) and see the [slides](https://mices.co/slides/user-behavior%20insights-mices-2024.pdf)
* :material-link: UBI at Haystack EU 2024 - [Leveraging User Behavior Insights to Enhance Search Relevance (presentation and slides)](https://haystackconf.com/eu2024/talk-1/)

### Help Getting Started

For questions or help getting started, reach out to [help@ubisearch.dev](mailto:help@ubisearch.dev) or join us in the `#ubi` channel of the [Relevance Slack workspace](https://opensourceconnections.com/slack) and we will be glad to help!

## Purpose and Goals

Many Search teams struggle with understanding "Why is my user doing this". They have great understanding of an incoming query and the results returned, but no ability to connect that information with an indicator of success, such as a click through event or add to cart event.

There are many tools out there for tracking web events, e.g. Google Analytics, but each is a bit different, and each tends to focus on the general case rather than the specific needs of search teams. 

The User Behavior Insights [standard](standard.md) attempts to provide a search focused standard that can operate across many platforms. We currently have [plugins](https://www.ubisearch.dev/tools/) for OpenSearch, Elasticsearch and Solr, but we hope that many other search platforms adopt UBI - [get in touch](mailto:help@ubisearch.dev)  if you'd like to help.  

Once you have this tracking data, you can potentially use it to:

* develop a deeper understanding of what your users are doing
* create search relevance metrics
* tune search parameters automatically 
* balance between different approaches to search (e.g. lexical and/or semantic)

## Reference Implementation

A full reference implementation, showing UBI tracking search events on an e-commerce website, using OpenSearch is available at [chorus-opensearch-edition](https://github.com/o19s/chorus-opensearch-edition). Check out the [Quick Start](quickstart.md) for details on getting up and running with an example environment.

## Sponsored & Led By

| Person                                                    | Affiliation                                                     | Contact                        |
|-----------------------------------------------------------|-----------------------------------------------------------------|--------------------------------|
| Eric Pugh                                                 | [OpenSource Connections](https://www.opensourceconnections.com) | epugh@opensourceconnections.com |
| Jeff Zemerick | [Mountain Fog](https://www.jeffzemerick.dev/)                   | jeff.zemerick@mtnfog.com       |
| Stavros Macrakis                                          | [Amazon OpenSearch](https://www.opensearch.org/)                | macrakis@amazon.com                               |
| Charlie Hull                                              | Independent                                                     | thesearchjuggler@gmail.com     |

## What UBI Powers

Are you or your organization using UBI? Let us know! We'd [love to hear about it](mailto:help@ubisearch.dev) and tell your success story here.
