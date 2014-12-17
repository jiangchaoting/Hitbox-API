# Stream Stats API
***

| Endpoint | Description |
| ---- | --------------- |
| [GET /streamstats/:user/:startTime/:endTime](/streamstats.md#get-streamstatsuserstarttimeendtime) | Returns stream stats |

## `GET /streamstats/:user/:startTime/:endTime`

Returns stream stats between `:startTime` and `:endTime`  (These are Epoch time stamps)

| Parameter | Required? | Type | Description |
| --- | --- | --- | --- |
| authToken | Yes | string | User's Auth Token |

### Example URL

https://www.hitbox.tv/api/streamstats/test-account/1416182400000/1418860799000

### Example Response 

Even if it fails:
```json
{
   "channel":"test-account",
   "startTime":"1416182400000",
   "endTime":"1418860799000",
   "step":86400000,
   "maxviewer":2,
   "maxfollower":2,
   "maxregistered":2,
   "maxembed":0,
   "maxsubscriber":0,
   "maxandroid":0,
   "maxios":0,
   "maxchromecast":0,
   "maxweb":2,
   "totalads":0,
   "timeline":{
      "viewer":[
         [
            1416873600000,
            2
         ],
         [
            1417132800000,
            1
         ],
         [
            1418169600000,
            1
         ],
         [
            1418342400000,
            1
         ],
         [
            1418428800000,
            1
         ],
         [
            1418515200000,
            0
         ]
      ],
      "viewer_avg":[
         [
            1416873600000,
            0
         ],
         [
            1417132800000,
            0
         ],
         [
            1418169600000,
            0
         ],
         [
            1418342400000,
            1
         ],
         [
            1418428800000,
            1
         ],
         [
            1418515200000,
            0
         ]
      ],
      "follower":[
         [
            1416873600000,
            2
         ],
         [
            1417132800000,
            1
         ],
         [
            1418169600000,
            1
         ],
         [
            1418342400000,
            1
         ],
         [
            1418428800000,
            1
         ],
         [
            1418515200000,
            0
         ]
      ],
      "registered":[
         [
            1416873600000,
            2
         ],
         [
            1417132800000,
            1
         ],
         [
            1418169600000,
            1
         ],
         [
            1418342400000,
            1
         ],
         [
            1418428800000,
            1
         ],
         [
            1418515200000,
            0
         ]
      ],
      "embed":[
         [
            1416873600000,
            0
         ],
         [
            1417132800000,
            0
         ],
         [
            1418169600000,
            0
         ],
         [
            1418342400000,
            0
         ],
         [
            1418428800000,
            0
         ],
         [
            1418515200000,
            0
         ]
      ],
      "subscriber":[
         [
            1416873600000,
            0
         ],
         [
            1417132800000,
            0
         ],
         [
            1418169600000,
            0
         ],
         [
            1418342400000,
            0
         ],
         [
            1418428800000,
            0
         ],
         [
            1418515200000,
            0
         ]
      ],
      "android":[
         [
            1416873600000,
            0
         ],
         [
            1417132800000,
            0
         ],
         [
            1418169600000,
            0
         ],
         [
            1418342400000,
            0
         ],
         [
            1418428800000,
            0
         ],
         [
            1418515200000,
            0
         ]
      ],
      "ios":[
         [
            1416873600000,
            0
         ],
         [
            1417132800000,
            0
         ],
         [
            1418169600000,
            0
         ],
         [
            1418342400000,
            0
         ],
         [
            1418428800000,
            0
         ],
         [
            1418515200000,
            0
         ]
      ],
      "chromecast":[
         [
            1416873600000,
            0
         ],
         [
            1417132800000,
            0
         ],
         [
            1418169600000,
            0
         ],
         [
            1418342400000,
            0
         ],
         [
            1418428800000,
            0
         ],
         [
            1418515200000,
            0
         ]
      ],
      "web":[
         [
            1416873600000,
            2
         ],
         [
            1417132800000,
            1
         ],
         [
            1418169600000,
            1
         ],
         [
            1418342400000,
            1
         ],
         [
            1418428800000,
            1
         ],
         [
            1418515200000,
            0
         ]
      ],
      "ads":[
         [
            1416873600000,
            0
         ],
         [
            1417132800000,
            0
         ],
         [
            1418169600000,
            0
         ],
         [
            1418342400000,
            0
         ],
         [
            1418428800000,
            0
         ],
         [
            1418515200000,
            0
         ]
      ],
      "views":[
         [
            1416873600000,
            7
         ],
         [
            1417132800000,
            17
         ],
         [
            1418169600000,
            23
         ],
         [
            1418342400000,
            24
         ],
         [
            1418428800000,
            25
         ],
         [
            1418515200000,
            25
         ]
      ]
   }
}
```