
---
title: "Datastore"
linkTitle: "Datastore"
type: "docs"
weight: 55
description: >
  About the wasmVision Datastore.
---

wasmVision provides access to a data store for saving and retrieving information associated either with specific image frames, or else with specific processors.

## Datastore Architecture

```mermaid
flowchart TD
    subgraph datastore
        Frames[Frame data]
        Processors[Processor data]
        Datastorage[Datastorage interface]
        Memstore[In-memory datastore]
        BoltDB
        Redis
        NATS[NATS message queue]
        Frames-->Memstore
        Processors-->Datastorage
        Datastorage-->Memstore
        Datastorage-->BoltDB
        Datastorage-->Redis
        Datastorage-->NATS
    end
```

Frame data is specific to an individual frame. The lifespan of this data is a single pass thru each processor. As a result, the only storage for frame data is in-memory.

Processor data is specific to an individual processor. The lifespan of this data is multiple frame processing cycles. Data storage for Processor data can be any backend that supports the `Datastorage` interface.

Current backends:

- In-Memory (default)
- [BoltDB](https://github.com/etcd-io/bbolt)
- [Redis](https://github.com/redis/redis) or compatible key-value stores
- [NATS](https://github.com/nats-io) message queue

## Datastore Usage

See [Datastore Usage](/docs/guides/datastore) for information on how to use different datastore backends with wasmVision.

## Datastore API

See [Platform API](/docs/reference/platform#a-idwasmvision_platform_datastoreaimport-interface-wasmvisionplatformdatastore) for information on how to call the datastore from your own custom Processors.
