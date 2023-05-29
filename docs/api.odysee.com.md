---
title: api.odysee.com
---

# Odysee API documentation - api.odysee.com
This is an unofficial documentation for the Odysee API. api.odysee.com is used for view counts and video blocks. For metadata and video streams, api.na-backend.odysee.com is used.

## `GET` /file/list_blocked
Lists blocked claim IDs (for DMCA or other reasons).

### `200` OK
```
{
  "success": true,
  "error": null,
  "data": {
    "outpoints": [
      "...:0",
    ],
  }
}
```

## `GET` /file/view_count
Get view counts of videos.

### Query parameters
* `REQUIRED` auth_token: Authentication token
* `REQUIRED` claim_id: Claim ID of the video

### `200` OK
```
{
  "success": true,
  "error": null,
  "data": [
    239
  ]
}
```

### `401` Unauthorized
```
{
  "success": false,
  "error": "authentication required",
  "data": null
}
```

### `400` Bad Request
```
{
  "success": false,
  "error": "claim_id: cannot be blank.",
  "data": null
}
```

## `POST` /user/new
Create a new account.

### Form Data
```
auth_token: ""
language: "en"
app_id: "odyseecom692EAWhtoqDuAfQ6KHMXxFxt8tkhmt7sfprEMHWKjy5hf6PwZcHDV542V"
```

### `200` OK
```json
{
  "success": true,
  "error": null,
  "data": {
    "id": 179611504,
    "language": "en",
    "given_name": null,
    "family_name": null,
    "created_at": "2021-07-04T15:59:44Z",
    "updated_at": "2021-07-04T15:59:44Z",
    "invited_by_id": null,
    "invited_at": null,
    "invites_remaining": 0,
    "invite_reward_claimed": false,
    "is_reward_approved": false,
    "is_email_enabled": true,
    "manual_approval_user_id": null,
    "reward_status_change_trigger": null,
    "settings": null,
    "prev_settings": null,
    "publish_id": null,
    "country": null,
    "is_odysee_user": false,
    "location": null,
    "auth_token": "AUTH_TOKEN"
  }
}
```

## `GET` /subscription/sub_count
Get the sub count of a channel.

### Query parameters
* `REQUIRED` auth_token: Authentication token
* `REQUIRED` claim_id: Claim ID of the video

### `200` OK
```json
{
  "success": true,
  "error": null,
  "data": [
    34213
  ]
}
```

### `400` Bad Request
```json
{
  "success": false,
  "error": "claim_id: cannot be blank.",
  "data": null
}
```

### `401` Unauthorized
```json
{
  "success": false,
  "error": "authentication required",
  "data": null
}
```

## `GET` /yt/resolve
Get LBRY claim or channel IDs from YouTube video/channel IDs.

### Query parameters
* video_ids: YouTube video ID (multiple accepted, comma-seperated)
* channel_ids: YouTube channel ID (multiple accepted, comma-seperated)

### `200` OK
```json
{
  "success": true,
  "error": null,
  "data": {
    "videos": {
      "5JvLV2-ngCI": "@AlphaNerd#8/how-ssh-works-2#6",
      "12eoipnmdq": "" # Invalid or non-synced videos will return null
    },
    "channels": {
      "UC5UAwBUum7CPN5buc-_N1Fw": "@TheLinuxExperiment#e5d96ea3720b01cca537c6d90f38e8c11ff06a0a"
    }
  }
}
```