
---
title: "MCP"
linkTitle: "MCP"
type: "docs"
weight: 55
description: >
  Using wasmVision an an MCP Server
---

wasmVision includes experimental support for the [Model Context Protocol (MCP)](https://modelcontextprotocol.info/) by providing a [(MCP) Server](https://modelcontextprotocol.info/specification/draft/server/).

The MCP server implementation uses the "HTTP with SSE" transport to facilitate being used in various networking related scenarios.

## Using the MCP Server

To turn on the MCP server, use the `wasmvision run` command with the `--mcp-server=true` flag.

You can also set the port to be used for the MCP server with the `--mcp-port` flag. For example, `--mcp-port=http://192.168.1.13:1313`
