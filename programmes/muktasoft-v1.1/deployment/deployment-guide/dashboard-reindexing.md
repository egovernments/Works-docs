# Dashboard Reindexing

## Overview

Dashboard reindexing can be used to reindex both indices for wage bills and muster-roll after adding the "gender" field to the additional details of an individual. The subsequent sections provide the steps on how to reindex both indices.

## Reindex Elastic Search Indices - Steps

* In elastic search, backup the original-index and create a new migrate-index.
* Define a new migrate topic in the indexer and point to the migrate-index
* Check python3 installed locally
* Run a Kafka client and port-forward elastic search and point Kafka bootstrap servers to elastic search port (localhost:9200)
* Run an indexer service with indexer files.
* Fetch the data from services through API either in bulk or through a single input search
* Create an insert request for the indexer with bulk or single data.
* Push the insert request to the migrate-topic
* Check the migrate-index data
* Delete the original-index, create a new original index, and migrate the data from the migrate-index to the original–index.

## Services To Reindex

* expense-bill-index
* muster-inbox

## Reindexing Scripts

Refer to [Reindex](https://github.com/odisha-muktasoft/MUKTA\_IMPL/tree/UAT/utilities/reindex), run the migrate scripts with python3.



