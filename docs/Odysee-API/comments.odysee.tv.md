---
title: comments.odysee.tv
---

# Odysee API Documentation - comments.odysee.tv
Odysee comments API.

## `POST` /api/v2?m=comment.List
List comments for a claim.

### JSON Data
```json
{
  "jsonrpc": "2.0",
  "id": 1,
  "method": "comment.List",
  "params": {
    "page": 1,
    "page_size": 10,
    "top_level": true,
    "sort_by: 3, # 3 - Best, 2 - Controversial, 0 - New
    "parent_id": "parent comment ID", # For comment replies
    "claim_id": "463e63afb35a319f260b36ef8d5c3dc41a98ce28",
    "channel_id": "ecf0a6be99030d0ad4e10aec11d2c0bab94246ae",
    "channel_name": "@MusicARetro"
  }
}
```

### `200` OK
```json
{
  "jsonrpc": "2.0",
  "result": {
    "page": 1,
    "page_size": 600,
    "total_pages": 1,
    "total_items": 3,
    "total_filtered_items": 3,
    "items": [
      {
        "comment": "otimo",
        "comment_id": "cf646d91c2c98a9471954b63bc51cf8c78f86fa1c734fb0c65e49ed0ded3799b",
        "claim_id": "463e63afb35a319f260b36ef8d5c3dc41a98ce28",
        "timestamp": 1613902598,
        "signature": "",
        "signing_ts": "1613902598",
        "is_hidden": false,
        "is_pinned": false,
        "channel_id": "d177dcbe8cfd1b6e58797ea573ba856a2be759c0",
        "channel_name": "@joseavf1",
        "channel_url": "lbry://@joseavf1#d177dcbe8cfd1b6e58797ea573ba856a2be759c0",
        "support_amount": 0
      }, {
        "comment":"True. Always entertaining content.",
        "comment_id":"49357e258bf3b69574ead22e43144630c94ca73950b84cc7280f99c610b559a2",
        "claim_id":"93b951fc1f8c7af3def41073c539ec957c3c562a",
        "timestamp":1625274573,
        "parent_id":"fafae646a3c1ae2e3f4631b77733ef5a6e197f052228d8ae09aa642aa2ddff34",
        "signature":"",
        "signing_ts":"1625274572",
        "is_hidden":false,
        "is_pinned":false,
        "channel_id":"0db3cea9230c2506e266df053a5a8aca8dc39214",
        "channel_name":"@VoidHeart",
        "channel_url":"lbry://@VoidHeart#0db3cea9230c2506e266df053a5a8aca8dc39214",
        "replies":1,
        "support_amount":0
      }
    ],
    "has_hidden_comments": false
  },
  "id": 1
}
```

## `POST` /api/v2?m=reaction.List
Get comment reactions.

### JSON Data
```json
{
  "jsonrpc": "2.0",
  "id": 1,
  "method": "reaction.List",
  "params": {
    "comment_ids": "commentId,commentId2" # Comma-separated list of comment IDs
    }
  }
```

### `200` OK
```json
{
  "jsonrpc": "2.0",
  "result": {
    "others_reactions": {
      "062d9b51b099db7c4bba2e3aa2811badc901cf116f6fb6cdb68e0a636784fa14": {
        "": 0,
        "bones": 0,
        "creator_like": 0,
        "creators_like": 0,
        "dislike": 0,
        "frozen_tom": 0,
        "like": 1,
        "likes": 0,
        "mind_blown": 0
      }
    }
  },
  "id": 1
}
```

## `POST` /api/v2?m=comment.Create
Create a comment.

### JSON Data
```json
{
  "method": "comment.Create",
  "id": 1,
  "jsonrpc": "2.0",
  "params": {
    "channel_id": "81bec0b66ff34a1378581751958f5b98f9043d17",
    "channel_name": "@vertbyqb",
    "claim_id": "2ba7ec34033a42c76468cdfc463943e5de7e364a",
    "parent_id": "", # Optional, for replies
    "comment": "l test",
    "signature": "lbrynet channel sign --channel_name=@channel --hexdata=hexdata", # hexdata is the hex encoded version of the comment. TO-DO: Document signing API
    "signing_ts": "1642638072"
  }
}
```

### `200` OK
```json
{
  "jsonrpc": "2.0",
  "result": {
    "comment": "l test",
    "comment_id": "c20a24a3fa050d0b3cd851be1dcf27d3091bcee2e770784fba7d70f3502964d5",
    "claim_id": "2ba7ec34033a42c76468cdfc463943e5de7e364a",
    "timestamp": 1642638103,
    "parent_id": "ef31674ca10560c5c1ad41f9b2e2de80af80fe73121047e96a7ba1f28dd00525",
    "signature": "f37dcadda088b77a6ee17271e8d27b2b67820b22bc2752c066864fa9ebfaa33f9ea9d98cf7e7b3209b519e0ca66ea65a62d5738b9d028f42e0c7a420a2b603bf",
    "signing_ts": "1642638072",
    "channel_id": "81bec0b66ff34a1378581751958f5b98f9043d17",
    "channel_name": "@vertbyqb",
    "channel_url": "lbry://@vertbyqb#81bec0b66ff34a1378581751958f5b98f9043d17",
    "currency": "",
    "support_amount": 0,
    "is_hidden": false,
    "is_pinned": false,
    "is_fiat": false
  },
  "id": 1
}
```

## `POST` /api/v2?m=comment.Abandon
Abandon a comment.

### JSON Data
```json
{
  "method": "comment.Abandon",
  "id": 1,
  "jsonrpc": "2.0",
  "params": {
    "channel_id": "81bec0b66ff34a1378581751958f5b98f9043d17",
    "channel_name": "@vertbyqb",
    "claim_id": "2ba7ec34033a42c76468cdfc463943e5de7e364a",
    "comment_id": "3eb5e2719a0e70d987eef586234e3fafd31eaafca14f9cc14048accf1ba4aef4",
    "signature": "lbrynet channel sign --channel_name=@channel --hexdata=hexdata", # hexdata is the hex encoded version of the comment_id. TO-DO: Document signing API
    "signing_ts": "1642638072"
  }
}
```

### `200` OK
```json
{
    "jsonrpc": "2.0",
    "result":
    {
        "comment": "Test",
        "comment_id": "3eb5e2719a0e70d987eef586234e3fafd31eaafca14f9cc14048accf1ba4aef4",
        "claim_id": "f334b6d4f4b42620d5abfe07ad1100cf1d597a9f",
        "timestamp": 1649613454,
        "signature": "2945092ad56d8997d5537bd77bd7420b16004e7fa41d2fc639dfe10b0601f2548cb9ce8b6d8ebb024175e8ba62035f11052fdc2c5b3b089c92134bfdba9abd61",
        "signing_ts": "1649613454",
        "channel_id": "ebec8cc32a98cfed2902f572bad62c3c0378def2",
        "channel_name": "@MorsMortium",
        "channel_url": "lbry://@MorsMortium#ebec8cc32a98cfed2902f572bad62c3c0378def2",
        "currency": "",
        "support_amount": 0,
        "is_hidden": false,
        "is_pinned": false,
        "is_fiat": false,
        "abandoned": true
    },
    "id": 1
}
```

## `POST` /api/v2?m=comment.Edit
Edit a comment.

### JSON Data
```json
{
    "id": 1,
    "jsonrpc": "2.0",
    "method": "comment.Edit",
    "params": {
        "comment_id": "3eb5e2719a0e70d987eef586234e3fafd31eaafca14f9cc14048accf1ba4aef4",
        "comment": "Test",
        "channel_name": "@MorsMortium",
        "channel_id": "ebec8cc32a98cfed2902f572bad62c3c0378def2",
        "signature": "lbrynet channel sign --channel_name=@channel --hexdata=hexdata", # hexdata is the hex encoded version of the comment. TO-DO: Document signing API
    "signing_ts": "1642638072"
    }
}
```

### `200` OK
```json
{
    "jsonrpc": "2.0",
    "result":
    {
        "comment": "Testggggggddfsdsd",
        "comment_id": "bc91909960cb7b74c09777d9291bebf208e0a6e32801fbbe64acfd809cbb8218",
        "claim_id": "f334b6d4f4b42620d5abfe07ad1100cf1d597a9f",
        "timestamp": 1649615106,
        "signature": "90080fa06bbe51530a224f604be850a851110248e50d5aa682b776f12f097fe78d68775816addfad49277243c6968f40cfd259ceb56d7f209ed923186705560a",
        "signing_ts": "1649615106",
        "channel_id": "ebec8cc32a98cfed2902f572bad62c3c0378def2",
        "channel_name": "@MorsMortium",
        "channel_url": "lbry://@MorsMortium#ebec8cc32a98cfed2902f572bad62c3c0378def2",
        "currency": "",
        "support_amount": 0,
        "is_hidden": false,
        "is_pinned": false,
        "is_fiat": false
    },
    "id": 1
}
```