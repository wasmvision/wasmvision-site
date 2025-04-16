---
title: "Using the Datastore"
linkTitle: "Using the Datastore"
type: "docs"
weight: 30
description: >
  How to use the wasmVision Datastore.
---

wasmVision provides access to a configurable key-value store for saving and retrieving data associated with specific processors.

See [Platform API - Datastore](/docs/reference/platform#a-idwasmvision_platform_datastoreaimport-interface-wasmvisionplatformdatastore) for information on how to call the datastore from your own custom Processors.

## In-memory

By default, wasmVision uses an in-memory data store.

When using wasmVision, this is configured by using the `--datastorage=memory` flag.

## BoltDB

wasmVision can use BoltDB as a processor datastore backend.

When using wasmVision, this is configured by using the `--datastorage=boltdb` flag.

### Environment

`WASMVISION_STORAGE_BOLTDB_FILENAME` - BoltDB database file to use.

`WASMVISION_STORAGE_BOLTDB_FILEMODE` - BoltDB database file mode to use, if needed.

## Redis

wasmVision can use Redis, or other KV stores that are compatible with Redis, as a processor datastore backend.

When using wasmVision, this is configured by using the `--datastorage=redis` flag.

### Environment

`WASMVISION_STORAGE_REDIS_URL` - Redis server URL to use.

## NATS

wasmVision can use the [NATS message queue](https://nats.io/) as a processor datastore backend.

With this backend, only `Set` operations can be used, since they are sending messages and not necessarily persisting those messages in any database.

When using wasmVision, this is configured by using the `--datastorage=nats` flag.

### Environment

`WASMVISION_STORAGE_NATS_URL` - NATS server URL to use.

`WASMVISION_STORAGE_NATS_USER_CREDENTIALS` - NATS user credentials.

`WASMVISION_STORAGE_NATS_NKEY_FILE` - NATS nkey file.

`WASMVISION_STORAGE_NATS_CERT_FILE` - NATS certificate.

`WASMVISION_STORAGE_NATS_KEY_FILE` - NATS key file.

`WASMVISION_STORAGE_NATS_CA_CERT` - NATS CA certificate.
