---
title: odysee.com
---

# Odysee API documentation - odysee.com
This is unofficial documentation for the Odysee API.

## `GET` /$/api/content/v2/get

### `200` OK
Response shortened and channel IDs removed.

```json
{
  "status": "success",
  "data": {
    "en": {
      "categories": {
        "FEATURED": {
          "channelIds": [],
          "name": "popculture",
          "sortOrder": 10,
          "icon": "Pop Culture",
          "label": "Pop Culture",
          "description": "Movies, TV, Comic Books, and all the other pop culture content on Odysee",
          "image": "",
          "channelLimit": "1",
          "daysOfContent": 180,
          "pageSize": 12
        },
        "ART": {
          "channelIds": [],
          "name": "artists",
          "sortOrder": 20,
          "icon": "Artists",
          "label": "Artists",
          "description": "Odysee's home for art, animation, comedy, and everything inbetween",
          "image": "",
          "channelLimit": "1",
          "daysOfContent": 180,
          "pageSize": 12
        },
        "PRIMARY_CONTENT": {
          "channelIds": [],
          "name": "education",
          "sortOrder": 30,
          "icon": "Education",
          "label": "Education",
          "description": "Who needs school when there's Odysee?",
          "image": "",
          "channelLimit": "1",
          "daysOfContent": 180,
          "pageSize": 12
        },
        "LIFESTYLE": {
          "channelIds": [],
          "name": "lifestyle",
          "sortOrder": 30,
          "icon": "Peace",
          "label": "Lifestyle",
          "description": "Odysee's home for lifestyle content - cooking, gardening, fitness, you name it",
          "image": "",
          "channelLimit": "1",
          "daysOfContent": 180,
          "pageSize": 12
        },
        "MUSIC": {
          "channelIds": [],
          "name": "music",
          "sortOrder": 40,
          "icon": "MusicCategory",
          "label": "Music",
          "description": "Get your groove on with Odysee",
          "image": "https://player.odycdn.com/speech/category-music:8.jpg",
          "channelLimit": "1",
          "daysOfContent": 720,
          "pageSize": 12
        },
        "GAMING": {
          "channelIds": [],
          "name": "gaming",
          "sortOrder": 60,
          "icon": "Gaming",
          "label": "Gaming",
          "description": "Pew pew bzzz gaming on Odysee",
          "image": "https://player.odycdn.com/speech/category-gaming:5.jpg",
          "channelLimit": "1",
          "daysOfContent": 180,
          "pageSize": 12,
          "tags": [
            "gaming"
          ],
          "searchLanguages": [
            "en"
          ]
        },
        "TECHNOLOGY": {
          "channelIds": [],
          "name": "tech",
          "sortOrder": 80,
          "icon": "Speaker",
          "label": "Tech",
          "description": "Hardware, software, startups, photography on Odysee",
          "image": "",
          "channelLimit": "1",
          "daysOfContent": 180,
          "pageSize": 12
        },
        "FINANCE": {
          "channelIds": [],
          "name": "finance",
          "sortOrder": 100,
          "icon": "DollarSign",
          "label": "Finance 2.0",
          "description": "Crypto, Money, Economics, Markets on Odysee",
          "image": "https://player.odycdn.com/speech/category-finance:c.jpg",
          "channelLimit": "1",
          "daysOfContent": 180,
          "pageSize": 12
        },
        "UNIVERSE": {
          "channelIds": [],
          "name": "universe",
          "sortOrder": 60,
          "icon": "Universe",
          "label": "Universe",
          "channelLimit": "1",
          "daysOfContent": 180,
          "pageSize": 12
        },
        "NEWS_AND_POLITICS": {
          "hideByDefault": true,
          "channelIds": [],
          "name": "news",
          "sortOrder": 90,
          "icon": "Aperature",
          "label": "News & Politics",
          "description": "Stay up to date with all that's happening around the world on Odysee",
          "image": "",
          "channelLimit": "1",
          "daysOfContent": 180,
          "pageSize": 12
        },
        "WILD_WEST": {
          "hideByDefault": true,
          "name": "wildwest",
          "sortOrder": 999,
          "icon": "WildWest",
          "label": "Wild West",
          "description": "Boosted by user credits, this is what the community promotes on Odysee",
          "image": "https://player.odycdn.com/speech/category-wildwest:1.jpg",
          "channelLimit": "1",
          "searchLanguages": [
            "en"
          ],
          "excludedChannelIds": []
        }
      },
      "meme": {
        "text": "don't worry about the vase",
        "url": "https://odysee.com/@Odysee:8?view=discussion"
      },
      "announcement": ""
    },
    "fr": {
      "categories": {
        
      }
    }
  }
}
```