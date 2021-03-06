# Following API
***


| Endpoint | Description |
| ---- | --------------- |
| [GET /following/user](/user/following.md#get-followinguser) | Returns a list of channels a user is following. |
| [PUT /following/user](/user/following.md#put-followinguser) | Motify following notifications. |
| [GET /following/user/:channel](/user/following.md#getfollowinguserchannel) | Returns following information for channel. |

## `GET /following/user`

| Parameter | Required? | Type | Description |
| --- | --- | --- | --- |
| sort | No | string | Valid Sort: date_added, user_name, user_id, follower_notify |
| user_name | Yes | string | User's user name |
| offset | No | int | offsets the results by the given amount |
| limit | No | int | Limits the results |
| reverse | No | boolean | Reverses the results |

Returns a list of channels a user is following.

### Example URL

https://www.hitbox.tv/api/following/user?user_name=test-account

### Example Response 

```javascript
{
   "request":{
      "this":"/following/user"
   },
   "following":[
      {
         "followers":"41",
         "user_name":"test-account",
         "user_id":"123",
         "user_logo":"/static/img/channel/test-account_54731f215b60c_large.jpg",
         "user_logo_small":"/static/img/channel/test-account_54731f215b60c_small.jpg",
         "follow_id":"123",
         "follower_user_id":"278723",
         "follower_notify":"1",
         "date_added":"2014-07-04 02:35:48"
      },
      {
         "followers":"7",
         "user_name":"RandomChannel",
         "user_id":"124",
         "user_logo":"/static/img/channel/RandomChannel_53f4e837eb388_large.png",
         "user_logo_small":"/static/img/channel/RandomChannel_53f4e837eb388_small.png",
         "follow_id":"124",
         "follower_user_id":"278723",
         "follower_notify":"1",
         "date_added":"2015-01-02 01:55:25"
      },
      ...
   ],
   "max_results":"2"
}
```


## `PUT /following/user`

| Parameter | Required? | Type | Description |
| --- | --- | --- | --- |
| user_name | Yes | string | User's user name |
| authToken | Yes | string | User's auth token |

### Example URL

https://www.hitbox.tv/api/following/user?authToken=SuperSecret&user_name=Test-Account

### Example PUT Payload

```javascript
{
    "following":[
        {
            "followers":"17",
            "user_name":"Test-Admin",
            "user_id":"278723",
            "user_logo":"\/static\/img\/channel\/Hitakashi_5600a327a9a4e_large.png",
            "user_logo_small":"\/static\/img\/channel\/Hitakashi_5600a327a9a4e_small.png",
            "follow_id":"278723",
            "follower_user_id":"278723",
            "follower_notify":"0",
            "date_added":"2015-09-23 22:25:50"
        },
        ...
    ]
}
```

### Example Response

You will get an echo back with what you sent.

```javascript
{
    "following":[
        {
            "followers":"17",
            "user_name":"Test-Admin",
            "user_id":"278723",
            "user_logo":"\/static\/img\/channel\/Hitakashi_5600a327a9a4e_large.png",
            "user_logo_small":"\/static\/img\/channel\/Hitakashi_5600a327a9a4e_small.png",
            "follow_id":"278723",
            "follower_user_id":"278723",
            "follower_notify":"0",
            "date_added":"2015-09-23 22:25:50"
        },
        ...
    ]
}
```

## `GET /following/user/:channel`

| Parameter | Required? | Type | Description |
| --- | --- | --- | --- |
| user_name | Yes | string | User's user name |

## Example URL

https://www.hitbox.tv/api/following/user/test-account?user_name=test-account

### Example Response

```javascript
{
   "following":{
      "follow_id":"278723",
      "follower_user_id":"278723",
      "follower_notify":"1"
   }
}
```

```javascript
{
   "success":false,
   "error":true,
   "error_msg":"not_following"
}
```