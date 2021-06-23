---
title: "Blobs API"
description: "Blobs API Reference"
lead: "Blobs API Reference"
date: 2021-06-09T13:32:57+01:00
lastmod: 2021-06-09T13:32:57+01:00
draft: false
images: []
menu: 
  docs:
    parent: "api-reference"
weight: 103
toc: true
---

## Upload a Blob

Upload the blob stored at /path/to/file:

```bash
$ curl -v -X POST \
    -H "@$BEARER_TOKEN_FILE" \
    -H "content_type=image/jpg" \
    -F "file=@/path/to/file" \
    $URL/archivist/v1/blobs
```

The response is:

```json
{
    "identity": "blobs/08838336-c357-460d-902a-3aba9528dd22",
    "hash": {
        "alg": "SHA256",
        "value": "xxxxxxxxxxxxxxxxxxxxxxx"
    },
    "mime_type": "image/jpeg",
    "timestamp_accepted": "2019-11-07T15:31:49Z",
    "size": 31424
}
```

## Retrieve a Blob

Retrieve a specific Attachment

```bash
$ curl -v \
    -H "@$BEARER_TOKEN_FILE" \
    -H "content_type=image/jpg" \
    -F "file=@/path/to/file" \
    $URL/archivist/v1/blobs/08838336-c357-460d-902a-3aba9528dd22
```

The response is:

```json
{
    "identity": "blobsV1/08838336-c357-460d-902a-3aba9528dd22",
    "hash": {
        "alg": "SHA256",
        "value": "xxxxxxxxxxxxxxxxxxxxxxx"
    },
    "mime_type": "image/jpeg",
    "timestamp_accepted": "2019-11-07T15:31:49Z",
    "size": 31424
}
```