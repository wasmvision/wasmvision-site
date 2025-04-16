---
title: "Using the Datastore"
linkTitle: "Using the Datastore"
type: "docs"
weight: 30
description: >
  How to use the wasmVision Datastore.
---

wasmVision provides access to a configurable key-value store for saving and retrieving data associated with specific processors.

## In-memory

By default, wasmVision uses an in-memory data store.

When using wasmVision, this is configured by using the `--datastorage=memory` flag.

## BoltDB

wasmVision can use BoltDB as a processor datastore backend.

When using wasmVision, this is configured by using the `--datastorage=boltdb` flag.

Set the `WASMVISION_STORAGE_BOLTDB_FILENAME` environment variable to set the BoltDB database file to use.

Set the `WASMVISION_STORAGE_BOLTDB_FILEMODE` environment variable to set the BoltDB database file mode to use, if needed.

## Redis

wasmVision can use Redis, or other KV stores that are compatible with Redis, as a processor datastore backend.

When using wasmVision, this is configured by using the `--datastorage=redis` flag.

Set the `WASMVISION_STORAGE_REDIS_URL` environment variable to set the Redis server URL to use.

