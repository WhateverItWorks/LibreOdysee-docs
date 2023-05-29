---
title: api.odysee.live
---

# Odysee API documentation - api.odysee.live
This is an unofficial documentation for the Odysee API. api.odysee.live is used for live streams.

> ⚠️ Requests for live video streams require extra headers to avoid being blocked. See [proxy/live.go](https://codeberg.org/librarian/librarian/src/branch/main/proxy/live.go#L24) for an example.

## `GET` /livestream/is_live
Gets data about the livestream.

### Query parameters
* `channel_claim_id` - Claim ID of the channel

### `200` OK
```json
{
  "success": true,
  "error": null,
  "data": {
    "Live": true,
    "Start": "2022-04-23T20:12:24Z",
    "VideoURL": "https://cloud.odysee.live/content/496730b88e41e74742fba5b6365435e5622dce92/master.m3u8",
    "ThumbnailURL": "",
    "ViewerCount": 9,
    "ChannelClaimID": "496730b88e41e74742fba5b6365435e5622dce92",
    "ActiveClaim": {
      "ClaimID": "5d500bc4a741d14908507b5960280b1d0d1a0fc7",
      "ReleaseTime": "2022-04-08T11:38:47Z"
    },
    "PastClaims": [
      {
        "ClaimID": "5d500bc4a741d14908507b5960280b1d0d1a0fc7",
        "ReleaseTime": "2022-04-08T11:38:47Z"
      },
      {
        "ClaimID": "63a0c26587209371a462118d72a249382f01f5cf",
        "ReleaseTime": "2022-03-26T12:26:17Z"
      }
    ],
    "FutureClaims": null
  }
}
```

## `GET` wss://sockety.odysee.com/ws/commentron
WebSocket for live chat.

### Query Parameters
* `id` - Claim ID of the channel
* `category` - Claim ID of the channel

### Messages
TO-DO