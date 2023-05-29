---
title: lighthouse.odysee.tv
---

# Odysee API documentation - lighthouse.odysee.tv
lighthouse.odysee.tv is used for searching Odysee.

> ⚠️ Requests to these endpoints require extra headers to avoid being blocked. See [api/search.go](https://codeberg.org/librarian/librarian/src/branch/main/api/search.go#L36) for an example.

## `GET` /search
Search Odysee for channels and videos.

### Query parameters
* `REQUIRED` s: Search query (string) (3-99999 characters)
* size: Amount of search results to get (number, default: 9)
* from: Use to get next page of results (number)
* claimType: The type of claim to search for (accepts list, (file,channel): file, channel, default: file,channel)
* nsfw: Show NSFW videos (boolean)
* free_only: Show paid videos (boolean)
* related_to: Claim ID of video to get related videos (string)

### `200` OK
```
[
  {
    "claimId": "2332c0df0bd5e046db04fe7e3e79f756d35a1523",
    "name": "@DistroTube"
  }
]
```

### `400` Bad Request
```
{
  "success": false,
  "error": "S: cannot be blank.",
  "data": null
}
```

## `GET` /autocomplete

### Query parameters
* `REQUIRED` s: Search query (string)


### `200` OK
```
[
  "searchnu-searchqu-software-entfernen",
  "searchsploit-searching-for-exploits",
  "SearchFunctionHangUp",
  "search1",
  "searchblackbox-net-history",
  "CRYM---Searchlights",
  "searchblackbox-review-1",
  "torrent-search-searching-bittorrent",
  "searchthat-net-v7",
  "searchthat-new-design"
]
```

### `400` Bad Request
```
{
  "success": false,
  "error": "S: cannot be blank.",
  "data": null
}
```