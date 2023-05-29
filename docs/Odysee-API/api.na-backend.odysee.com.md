---
title: api.na-backend.odysee.com
---

> **⚠️ DEPRECATED:** Use official documentation at https://lbry.tech/api/sdk

# Odysee API documentation - api.na-backend.odysee.com
This is an unofficial documentation for the Odysee API. api.na-backend.odysee.com is used for video metadata and video streams, api.odysee.com is used for data such as like/dislike counts and view counts.

## `GET` /api/v2/status

### `200` OK
```json
{
  "timestamp": "2021-07-03 00:29:19.5246211 +0000 UTC",
  "services": {
    "lbrynet": [
      {
        "name": "lbrynet-b-17",
        "status": "ok"
      }
    ]
  },
  "general_state": "ok"
}
```

## `POST` /api/v1/proxy?m=status

### JSON Data
```json
{
    "jsonrpc": "2.0",
    "method": "status",
    "params": {},
    "id": 1625272172600
}
```

### `200` OK
```json
{
  "jsonrpc": "2.0",
  "result": {
    "blob_manager": {
      "connections": {
        "incoming_bps": {},
        "outgoing_bps": {},
        "time": 0,
        "total_incoming_mbs": 0,
        "total_outgoing_mbs": 0
      },
      "finished_blobs": 0
    },
    "connection_status": {
      "code": "connected",
      "message": "No connection problems detected"
    },
    "installation_id": "692EAWhtoqDuAfQ6KHMXxFxt8tkhmt7sfprEMHWKjy5hf6PwZcHDV542VHqRnFnTCD",
    "is_running": true,
    "skipped_components": [
      "hash_announcer",
      "blob_server",
      "dht"
    ],
    "startup_status": {
      "blob_manager": true,
      "blockchain_headers": true,
      "database": true,
      "exchange_rate_manager": true,
      "peer_protocol_server": true,
      "stream_manager": true,
      "upnp": true,
      "wallet": true
    },
    "stream_manager": {
      "managed_files": 1
    },
    "upnp": {
      "aioupnp_version": "0.0.13",
      "dht_redirect_set": false,
      "external_ip": "127.0.0.1",
      "gateway": "No gateway found",
      "peer_redirect_set": false,
      "redirects": {}
    },
    "wallet": {
      "best_blockhash": "3d77791b9d87609a004b398e638bcdc91650247ee4448a2b30bf8474668d0ad3",
      "blocks": 0,
      "blocks_behind": 0,
      "is_encrypted": false,
      "is_locked": false
    }
  },
  "id": 1625272172600
}
```

## `POST` /api/v1/proxy?m=resolve
Resolves a LBRY URL.

### JSON Data

#### Video
```json
{
    "jsonrpc": "2.0",
    "method": "resolve",
    "params": {
        "urls": [
            "lbry://@jordanisgreat505#3/how-to-make-chicken-noodle-oinion-soup#9"
        ],
        "include_purchase_receipt": true,
        "include_is_my_output": true
    },
    "id": 1625272172800
}
```

#### Channel
```json
{
    "jsonrpc": "2.0",
    "method": "resolve",
    "params": {
        "urls": [
            "lbry://@SomeOrdinaryGamers#a"
        ],
        "include_purchase_receipt": true,
        "include_is_my_output": true
    },
    "id": 1625272172800
}
```

#### Articles
```json
{
    "jsonrpc": "2.0",
    "method": "resolve",
    "params": {
        "urls": [
            "lbry://@Odysee:8/axxl-on-odysee:c"
        ],
        "include_purchase_receipt": true,
        "include_is_my_output": true
    },
    "id": 1625272172800
}
```

### `200` OK

#### Video
```json
{
  "jsonrpc": "2.0",
  "result": {
    "lbry://@jordanisgreat505#3/how-to-make-chicken-noodle-oinion-soup#9": {
      "address": "bDwAYeNLZwt42dkvZi7ijVC99sTSSvwvjb",
      "amount": "0.005",
      "canonical_url": "lbry://@jordanisgreat505#3/how-to-make-chicken-noodle-oinion-soup#9",
      "claim_id": "9e9a5448d0afbe13bc7cd129acb35a290233487f",
      "claim_op": "update",
      "confirmations": 71132,
      "height": 917608,
      "is_channel_signature_valid": true,
      "is_my_output": false,
      "meta": {
        "activation_height": 902112,
        "creation_height": 902112,
        "creation_timestamp": 1611546078,
        "effective_amount": "0.005",
        "expiration_height": 3004512,
        "is_controlling": true,
        "reposted": 0,
        "support_amount": "0.0",
        "take_over_height": 902112,
        "trending_global": 0.0,
        "trending_group": 0,
        "trending_local": 0.0,
        "trending_mixed": 0.0
      },
      "name": "how-to-make-chicken-noodle-oinion-soup",
      "normalized_name": "how-to-make-chicken-noodle-oinion-soup",
      "nout": 0,
      "permanent_url": "lbry://how-to-make-chicken-noodle-oinion-soup#9e9a5448d0afbe13bc7cd129acb35a290233487f",
      "short_url": "lbry://how-to-make-chicken-noodle-oinion-soup#9",
      "signing_channel": {
        "address": "bDwAYeNLZwt42dkvZi7ijVC99sTSSvwvjb",
        "amount": "0.005",
        "canonical_url": "lbry://@jordanisgreat505#3",
        "claim_id": "3d248260e4d89cf4292c9d193560525f9a792512",
        "claim_op": "update",
        "confirmations": 71131,
        "has_signing_key": false,
        "height": 917609,
        "meta": {
          "activation_height": 902097,
          "claims_in_channel": 450,
          "creation_height": 902097,
          "creation_timestamp": 1611543696,
          "effective_amount": "0.005",
          "expiration_height": 3004497,
          "is_controlling": true,
          "reposted": 0,
          "support_amount": "0.0",
          "take_over_height": 902097,
          "trending_global": 0.0,
          "trending_group": 0,
          "trending_local": 0.0,
          "trending_mixed": 0.0
        },
        "name": "@jordanisgreat505",
        "normalized_name": "@jordanisgreat505",
        "nout": 0,
        "permanent_url": "lbry://@jordanisgreat505#3d248260e4d89cf4292c9d193560525f9a792512",
        "short_url": "lbry://@jordanisgreat505#3",
        "timestamp": 1614001671,
        "txid": "e9f99e66057025b8aada3b64acf7d004bb14fe035550a117cc48a185ae755ef8",
        "type": "claim",
        "value": {
          "cover": {
            "url": "https://thumbnails.lbry.com/banner-UCX6jiEzG7fNe1OXdzrGJxMQ"
          },
          "description": "hello peeps i make videos daily about video games real life things\n\nThanks to ♤ACE♤Freeflier181 for the profile pic and watermark. please go check her out for your own!\nLink https://freeflier181.deviantart.com/\n\nThanks to Not Cboy for the new channel banner!\n",
          "public_key": "3056301006072a8648ce3d020106052b8104000a03420004cead14e4a4f8502eb2622eef73a796bd1eb82f440f51523f9eda2dea75e317fd75d714b394fd6c6813f40432fa0aaeff705762771a8ecd5900b5dbae155dcffe",
          "public_key_id": "bPea6CzhHXogBcmy7SWahuFTefrC4UfHP7",
          "thumbnail": {
            "url": "https://thumbnails.lbry.com/UCX6jiEzG7fNe1OXdzrGJxMQ"
          },
          "title": "jordanisgreat 505"
        },
        "value_type": "channel"
      },
      "timestamp": 1614001625,
      "txid": "6119090be4c52277bb520ed27207748c4850e6540357ecb8efd942ffcf841c66",
      "type": "claim",
      "value": {
        "description": "\n...\nhttps://www.youtube.com/watch?v=pmTNVZL7KSk",
        "license": "Copyrighted (contact publisher)",
        "release_time": "1568073600",
        "source": {
          "hash": "aae9dd9b29f90923f34b8e48d29d7e0cb036334a5cd132c2cb8724c437f2146287ef810c742742ca43b32556cb34678b",
          "media_type": "video/mp4",
          "name": "how-to-make-chicken-noodle.mp4",
          "sd_hash": "09d9b2079ca3aaf4484b6a29fe3e03db7bc3934ba74d23ec3525d0a9022496806ef2335b8fbf582a60768822f7a848fe",
          "size": "4455260"
        },
        "stream_type": "video",
        "thumbnail": {
          "url": "https://thumbnails.lbry.com/pmTNVZL7KSk"
        },
        "title": "How to make chicken noodle oinion soup part 3",
        "video": {
          "duration": 25,
          "height": 720,
          "width": 1280
        }
      },
      "value_type": "stream"
    }
  },
  "id": 0
}
```

#### Channel
```json
{
  "jsonrpc": "2.0",
  "result": {
    "lbry://@SomeOrdinaryGamers#a": {
      "address": "bU66vJDJy3GwC6zu9E21bM4ME94hNAmzfV",
      "amount": "0.005",
      "canonical_url": "lbry://@SomeOrdinaryGamers#a",
      "claim_id": "a8cca58a9a49b08a1325be5fe76646ea85201dbd",
      "claim_op": "update",
      "confirmations": 24170,
      "has_signing_key": false,
      "height": 965486,
      "is_my_output": false,
      "meta": {
        "activation_height": 965412,
        "claims_in_channel": 2071,
        "creation_height": 965412,
        "creation_timestamp": 1621587132,
        "effective_amount": "5547.638718",
        "expiration_height": 3067812,
        "is_controlling": true,
        "reposted": 0,
        "support_amount": "5547.633718",
        "take_over_height": 965412,
        "trending_global": 0.0,
        "trending_group": 0,
        "trending_local": 0.0,
        "trending_mixed": -0.028158480301499367
      },
      "name": "@SomeOrdinaryGamers",
      "normalized_name": "@someordinarygamers",
      "nout": 0,
      "permanent_url": "lbry://@SomeOrdinaryGamers#a8cca58a9a49b08a1325be5fe76646ea85201dbd",
      "short_url": "lbry://@SomeOrdinaryGamers#a",
      "timestamp": 1621598500,
      "txid": "a8b547777a9ade157448f9508c61804ba4bf426e1c42b733a3ffe867afa22196",
      "type": "claim",
      "value": {
        "cover": {
          "url": "https://thumbnails.lbry.com/banner-UCtMVHI3AJD4Qk4hcbZnI9ZQ"
        },
        "description": "Let's Play's, Commentaries, Reviews, Hardcore Raging ... we're just a team of Ordinary Gamers... what did YOU expect???",
        "public_key": "3056301006072a8648ce3d020106052b8104000a03420004b63167b08a00a1a31ee38ae437e5c44abb606821eda2edc9898b9c71418afa729845eeee5756a7f1f590ca4f4c4343b9d0b867767833f7fb6290589733391a1d",
        "public_key_id": "bFSKg3r7mxAdSo5JYivr1mzqvbByyVhApp",
        "thumbnail": {
          "url": "https://thumbnails.lbry.com/UCtMVHI3AJD4Qk4hcbZnI9ZQ"
        },
        "title": "SomeOrdinaryGamers"
      },
      "value_type": "channel"
    }
  },
  "id": 0
}
```

#### Article
```json
{
  "jsonrpc": "2.0",
  "result": {
    "lbry://@Odysee:8/axxl-on-odysee:c": {
      "address": "bLjszZEJBxUCe2zrprf3hHZmK2r3kbmK6V",
      "amount": "50.0",
      "canonical_url": "lbry://@Odysee#8/axxl-on-odysee#c",
      "claim_id": "c80d4c55bb2b3ecba911097f192ccbe9c5ce2ef3",
      "claim_op": "update",
      "confirmations": 48104,
      "height": 1006034,
      "is_channel_signature_valid": true,
      "is_my_output": false,
      "meta": {
        "activation_height": 1006034,
        "creation_height": 1006032,
        "creation_timestamp": 1628008731,
        "effective_amount": "62.018",
        "expiration_height": 3108434,
        "is_controlling": true,
        "reposted": 0,
        "support_amount": "12.018",
        "take_over_height": 1006032,
        "trending_global": 0.0,
        "trending_group": 0,
        "trending_local": 0.0,
        "trending_mixed": 0.0
      },
      "name": "axxl-on-odysee",
      "normalized_name": "axxl-on-odysee",
      "nout": 0,
      "permanent_url": "lbry://axxl-on-odysee#c80d4c55bb2b3ecba911097f192ccbe9c5ce2ef3",
      "short_url": "lbry://axxl-on-odysee#c",
      "signing_channel": {
        "address": "bWmRCqPEgrnoMaXzwZ6wGtaY7BVcBCTJFx",
        "amount": "1.0",
        "canonical_url": "lbry://@Odysee#8",
        "claim_id": "80d2590ad04e36fb1d077a9b9e3a8bba76defdf8",
        "claim_op": "update",
        "confirmations": 138653,
        "has_signing_key": false,
        "height": 915485,
        "meta": {
          "activation_height": 916714,
          "claims_in_channel": 48,
          "creation_height": 831298,
          "creation_timestamp": 1600203894,
          "effective_amount": "1689.57096",
          "expiration_height": 3017885,
          "is_controlling": true,
          "reposted": 1,
          "support_amount": "1688.57096",
          "take_over_height": 919358,
          "trending_global": 0.0,
          "trending_group": 0,
          "trending_local": 0.0,
          "trending_mixed": 0.0
        },
        "name": "@Odysee",
        "normalized_name": "@odysee",
        "nout": 0,
        "permanent_url": "lbry://@Odysee#80d2590ad04e36fb1d077a9b9e3a8bba76defdf8",
        "short_url": "lbry://@Odysee#8",
        "timestamp": 1613674567,
        "txid": "6f2e8b3799f919aee9154f465f653f632c76bd062b23dcf84f0b9098f87ccce9",
        "type": "claim",
        "value": {
          "cover": {
            "url": "https://spee.ch/5/99ef192b3b366563.jpg"
          },
          "email": "hello@odysee.com",
          "languages": [
            "en"
          ],
          "public_key": "3056301006072a8648ce3d020106052b8104000a034200047c1024948871d1dcdf92a3ad987d5e94d8cab2e35ca19a85407be566c7af2b4a51d4e4ff7250041cfc26ee83e128f2831e75de043b942832e345879a0ac13dba",
          "public_key_id": "bQcmWRk69UkGQEib8WwrTCpq533QnFWwEX",
          "tags": [
            "odysee",
            "lbry",
            "news",
            "blockchain",
            "education"
          ],
          "thumbnail": {
            "url": "https://spee.ch/9/45245681a50082f7.jpg"
          },
          "title": "Odysee",
          "website_url": "odysee.com"
        },
        "value_type": "channel"
      },
      "timestamp": 1628009077,
      "txid": "858c42a00a659a948083e9997df16545a1eb0a1e9f765a5a0235182c972b8dbf",
      "type": "claim",
      "value": {
        "languages": [
          "en"
        ],
        "license": "None",
        "release_time": "1628008557",
        "source": {
          "hash": "058b182f95e3433b540e08865f160855eb41a65fa269aff2ed5b1a07c0bf5b7b3ffc9c1de4a570873d9f93c2602bcd5a",
          "media_type": "text/markdown",
          "name": "axxl-on-odysee.md",
          "sd_hash": "5fcc569c4c087eff097fa17dd738298f3fa658f4b21737e2ba02aa9586691f012c403e21f115c2c36bf808e48977763b",
          "size": "1106"
        },
        "stream_type": "document",
        "tags": [
          "axxl",
          "odysee"
        ],
        "thumbnail": {
          "url": "https://spee.ch/1/0e4d2ae15b8553bb.png"
        },
        "title": "Unprettiest Human Worldwide is now on Odysee"
      },
      "value_type": "stream"
    }
  },
  "id": 0
}
```

## `POST` /api/v1/proxy?m=version

### JSON Data
```json
{
    "jsonrpc": "2.0",
    "method": "version",
    "params": {},
    "id": 1625272173800
}
```

### `200` OK
```json
{
  "jsonrpc": "2.0",
  "result": {
    "build": "release",
    "desktop": "Unknown",
    "distro": {
      "codename": "bionic",
      "id": "ubuntu",
      "like": "debian",
      "version": "18.04",
      "version_parts": {
        "build_number": "",
        "major": "18",
        "minor": "04"
      }
    },
    "lbrynet_version": "0.99.0",
    "os_release": "4.14.193-149.317.amzn2.x86_64",
    "os_system": "Linux",
    "platform": "Linux-4.14.193-149.317.amzn2.x86_64-x86_64-with-Ubuntu-18.04-bionic",
    "processor": "x86_64",
    "python_version": "3.7.10",
    "version": "0.99.0"
  },
  "id": 0
}
```

## `POST` /api/v1/proxy?m=get
Get video stream URLs.

### JSON Data
```json
{
    "jsonrpc":"2.0",
    "method":"get",
    "params": {
        "uri": "lbry://@jordanisgreat505#3/how-to-make-chicken-noodle-oinion-soup#9",
        "save_file": false
    },
    "id":1625272174700
}
```

### `200` OK
```json
{
  "jsonrpc": "2.0",
  "result": {
    "streaming_url": "https://cdn.lbryplayer.xyz/api/v4/streams/free/how-to-make-chicken-noodle-oinion-soup/9e9a5448d0afbe13bc7cd129acb35a290233487f/09d9b2"
  },
  "id": 1625272174700
}
```

## `POST` /api/v1/proxy?m=comment_react_list
Get likes/dislikes for comments.

### JSON Data
```json
{
    "jsonrpc": "2.0",
    "method": "comment_react_list",
    "params": {
        "comment_ids": "92e04bebad630bd19138ef5fb922ce00a53daa39e8a0c8da9d34bafdf2de3940,beaa7141304adaf9fd54b2c4072b40867db7707510af6272770e6b6da103ac73"
    },
    "id": 1625437715900
}
```

### `200` OK
```json
{
  "jsonrpc": "2.0",
  "result": {
    "others_reactions": {
      "15f3272aa085ac16771459ad33b5a3f195af5932458ec130407794a957989870": {
        "": 0,
        "bones": 0,
        "creator_like": 0,
        "creators_like": 0,
        "dislike": 0,
        "frozen_tom": 0,
        "like": 0,
        "likes": 0,
        "mind_blown": 0
      },
      "3e2bd8f9fed0943a0895c428476473e6fab21afb694ec54a161f1a6bd0e493c3": {
        "": 0,
        "bones": 0,
        "creator_like": 0,
        "creators_like": 0,
        "dislike": 5,
        "frozen_tom": 0,
        "like": 1,
        "likes": 0,
        "mind_blown": 0
      }
    }
  },
  "id": 0
}
```

## `POST` /api/v1/proxy?m=claim_search

### JSON Data
```json
{
    "jsonrpc": "2.0",
    "method": "claim_search",
    "params":{
        "page_size": 30,
        "page": 1,
        "no_totals": true,
        "not_tags": ["tag"],
        "claim_type": ["stream", "collection"],
        "order_by": ["release_time | effective_amount | trending_group/trending_mixed"],
        "fee_amount": "<=0",
        "channel_ids": ["2332c0df0bd5e046db04fe7e3e79f756d35a1523"],
        "release_time": "<1626737820",
        "include_purchase_receipt": true
    },
    "id": 1626737833900
}
```

### `200` OK
```json
{
  "jsonrpc": "2.0",
  "result": {
    "blocked": {
      "channels": [],
      "total": 0
    },
    "items": [
      {
        "address": "bDymdcd6R9mceNmkaMGAdRjifLR3W9xCSb",
        "amount": "0.01",
        "canonical_url": "lbry://@DistroTube#2/to-protect-yourself,-never-give-your-dna#c",
        "claim_id": "c104793f74d9fd7793170f1fd262baec216a1d85",
        "claim_op": "create",
        "confirmations": 90,
        "height": 997927,
        "is_channel_signature_valid": true,
        "meta": {
          "activation_height": 997927,
          "creation_height": 997927,
          "creation_timestamp": 1626722365,
          "effective_amount": "47.0565573",
          "expiration_height": 3100327,
          "is_controlling": true,
          "reposted": 1,
          "support_amount": "47.0465573",
          "take_over_height": 997927,
          "trending_global": 0.0,
          "trending_group": 0,
          "trending_local": 0.0,
          "trending_mixed": 5.676791667938232
        },
        "name": "to-protect-yourself,-never-give-your-dna",
        "normalized_name": "to-protect-yourself,-never-give-your-dna",
        "nout": 0,
        "permanent_url": "lbry://to-protect-yourself,-never-give-your-dna#c104793f74d9fd7793170f1fd262baec216a1d85",
        "short_url": "lbry://to-protect-yourself,-never-give-your-dna#c",
        "signing_channel": {
          "address": "bDymdcd6R9mceNmkaMGAdRjifLR3W9xCSb",
          "amount": "0.005",
          "canonical_url": "lbry://@DistroTube#2",
          "claim_id": "2332c0df0bd5e046db04fe7e3e79f756d35a1523",
          "claim_op": "update",
          "confirmations": 5008,
          "has_signing_key": false,
          "height": 993009,
          "meta": {
            "activation_height": 695996,
            "claims_in_channel": 936,
            "creation_height": 695996,
            "creation_timestamp": 1578488436,
            "effective_amount": "41818.005",
            "expiration_height": 2798396,
            "is_controlling": true,
            "reposted": 0,
            "support_amount": "41818.0",
            "take_over_height": 695996,
            "trending_global": 0.0,
            "trending_group": 0,
            "trending_local": 0.0,
            "trending_mixed": -0.013612883165478706
          },
          "name": "@DistroTube",
          "normalized_name": "@distrotube",
          "nout": 0,
          "permanent_url": "lbry://@DistroTube#2332c0df0bd5e046db04fe7e3e79f756d35a1523",
          "short_url": "lbry://@DistroTube#2",
          "timestamp": 1625947295,
          "txid": "cb40029fb6d79fc88c80ce3c9a0c1b614c8087b0e6fc41678ff80d3e1a400dae",
          "type": "claim",
          "value": {
            "cover": {
              "url": "https://spee.ch/1/59fe91a43bd9d9db.png"
            },
            "description": "",
            "locations": [
              {
                "country": "US"
              }
            ],
            "public_key": "",
            "public_key_id": "",
            "thumbnail": {
              "url": "https://spee.ch/e/b18cc0e2d8c9707d.jpg"
            },
            "title": "DistroTube",
            "website_url": "www.distrotube.com"
          },
          "value_type": "channel"
        },
        "timestamp": 1626722365,
        "txid": "",
        "type": "claim",
        "value": {
          "description": "description",
          "languages": ["en"],
          "license": "Copyrighted (contact publisher)",
          "release_time": "1626721201",
          "source": {
            "hash": "",
            "media_type": "video/mp4",
            "name": "to-protect-yourself-never-give.mp4",
            "sd_hash": "",
            "size": "153053012"
          },
          "stream_type": "video",
          "tags": ["tags"],
          "thumbnail": {
            "url": "https://thumbnails.lbry.com/4kDPDio4MYw"
          },
          "title": "To Protect Yourself, Never Give Your DNA Or Biometric Data",
          "video": {
            "duration": 415,
            "height": 1080,
            "width": 1920
          }
        },
        "value_type": "stream"
      },
    ]
  }
}
```