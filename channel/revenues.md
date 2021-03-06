# Revenues Stats API
***

| Endpoint | Description |
| ---- | --------------- |
| [GET /revenues/:type/:user](/channel/revenues.md#get-revenuestypeuser) | Returns Revenues stats |
| [GET /payments/balance/:user](/channel/revenues.md#get-paymentsbalanceuser) | Get Payment Balance |
| [GET /transactions/history/:user](/channel/revenues.md#get-transactionshistoryuser) | Get Transaction History |
| [GET /payments/settings/:user](/channel/revenues.md#get-paymentssettingsuser) | Get Payment Settings |

## `GET /revenues/:type/:user`

| Parameter | Required? | Type | Description |
| --- | --- | --- | --- |
| authToken | Yes | string | User's Auth Token |
| endDate | Yes | Date | Date in YYYY-MM-DD |
| startDate | Yes | Date | Date in YYYY-MM-DD |

Returns revenues for given channel between `startDate` and `endDate`.

`:type` should either be `team` or `channel`

`:user` should be either a user when `:type` is `channel`, or a team name when `:type` is `team`

I have truncated each array to just one property.

### Example URL

https://www.hitbox.tv/api/revenues/channel/test-account?authToken=SuperSecret&endDate=2015-04-08&startDate=2015-03-07

### Example User Response 

Non-Parter Info: (I assume Partners follow the same layout)
```javascript
{
   "request":{
      "this":"/revenues/channel/test-account",
      "type":"channel",
      "user":"test-account"
   },
   "revenues":{
      "summary":{
         "currency":"EUR",
         "total_earnings":0,
         "max_earnings":null,
         "viewed_hours":0,
         "unique_user":0
      },
      "plans":[

      ],
      "timeline":[
         [
            1427673600000,
            0
         ]
      ],
      "daily":{
         "2015-03-30":{
            "earnings":0
         }
      },
      "groups":{
         "1425686400000":[
            null,
            null
         ]
      },
      "live":{
         "1425686400000":null
      },
      "total":{
         "1425686400000":null
      },
      "timeline_ads":[
         [
            1425686400000,
            null
         ]
      ],
      "timeline_subs":[
         [
            1425686400000,
            null
         ]
      ],
      "subs":{
         "1425686400000":null
      },
      "top":{
         "countries":[

         ],
         "content":{
            "live":{
               "earnings":0
            },
            "video":{
               "earnings":0
            },
            "subscriptions":{
               "earnings":0
            }
         }
      }
   }
}
```

### Example Team Response

```javascript
{
    "request":{
        "this":"/revenues/team/TestTeam",
        "type":"team",
        "user":"TestTeam"
    },
    "team":{
        "revenues":{
            "summary":{
                "currency":"USD"
            },
            "plans":[
                {
                    "plan_id":"1",
                    "plan_name":"TestTeam",
                    "plan_group_id":"1",
                    "plan_user_id":null,
                    "plan_countries":"Australia,Belgium,Canada,Denmark,Finland,France,Luxembourg,Netherlands,Norway,Sweden,United Kingdom,United States",
                    "plan_cpm":"0.00",
                    "plan_currency":"USD",
                    "plan_date_added":"2015-01-12 00:00:00"
                },
                {
                    "plan_id":"2",
                    "plan_name":"TestTeam",
                    "plan_group_id":"1",
                    "plan_user_id":null,
                    "plan_countries":"*",
                    "plan_cpm":"0.00",
                    "plan_currency":"USD",
                    "plan_date_added":"2015-01-12 00:00:00"
                },
                {
                    "plan_id":"3",
                    "plan_name":"TestTeam",
                    "plan_group_id":"1",
                    "plan_user_id":null,
                    "plan_countries":"Austria,Germany,Switzerland",
                    "plan_cpm":"0.00",
                    "plan_currency":"USD",
                    "plan_date_added":"2015-01-12 00:00:00"
                }
            ],
            "members":{
                "1":{
                    "summary":{
                        "last_updated":"2015-11-11 00:00:00",
                        "total_earnings":0,
                        "max_earnings":null,
                        "sub_earnings":0,
                        "live_earnings":0,
                        "video_earnings":0
                    },
                    "timeline":[
                        [
                            1444435200000,
                            0
                        ]
                    ],
                    "daily":{
                        "2015-10-10":{
                            "earnings":0
                        }
                    }
                },
				...
            }
        },
        "info":{
            "group_id":"1",
            "founder_name":"TestAdmin",
            "group_name":"TestTeam",
            "group_display_name":"Test Team",
            "group_text":"The Best Team Description.",
            "group_logo_small":"/static/img/teams/logo_54c643249d_small.png",
            "group_logo_large":"/static/img/teams/logo_54c643249d_large.png",
            "group_cover":null,
            "members_total":1
        },
        "members":[
            {
                "followers":"113",
                "user_id":"1",
                "user_name":"TestAdmin",
                "user_status":"1",
                "user_logo":"/static/img/channel/TestAdmin_53cda133184df_large.png",
                "user_cover":"/static/img/channel/cover_52f62514d614b.png",
                "user_logo_small":"/static/img/channel/TestAdmin_53cda133184df_small.png",
                "user_email":"example@example.com",
                "revenues":{
                    "summary":{
                        "last_updated":"2015-11-11 00:00:00",
                        "total_earnings":0.00,
                        "max_earnings":0.00,
                        "sub_earnings":0.00,
                        "live_earnings":0,
                        "video_earnings":0
                    },
                    "timeline":[
                        [
                            1444435200000,
                            0
                        ]
                    ],
                    "daily":{
                        "2015-10-10":{
                            "earnings":0
                        }
                    }
                }
            },
			...
        ],
        "summary":{
            "currency":"USD"
        }
    }
}
```

## `GET /payments/balance/:user`

| Parameter | Required? | Type | Description |
| --- | --- | --- | --- |
| authToken | Yes | string | User's Auth Token |

Returns balance for `user`. Broadcaster Only.

### Example URL

https://www.hitbox.tv/api/payments/balance/test-account?authToken=SuperSecret

### Example Response

```javascript
[
    {
        "user_id":"1",
        "plan_currency":"EUR",
        "minDate":"2015-08",
        "maxDate":"2015-09",
        "sub_earnings":"0.00",
        "live_earnings":"0.00",
        "video_earnings":"0.00",
        "min_threshold":"0.00",
        "special_credits":"0.00"
    }
]
```

## `GET /transactions/history/:user`

| Parameter | Required? | Type | Description |
| --- | --- | --- | --- |
| authToken | Yes | string | User's Auth Token |

Returns transaction history for `user`. Broadcaster Only.

### Example URL

https://www.hitbox.tv/api/transaction/history/test-account?authToken=SuperSecret

### Example Response

```javascript
{
    "request":{
        "this":"/transactions/history/test-account",
        "user":"test-account"
    },
    "orders":[
        {
            "breakdown":[
                {
                    "payorder_id":"1",
                    "currency":"EUR",
                    "month_disp":"2015-07",
                    "credit_date":"2015-07-31",
                    "reason":"Revenue share",
                    "amount":"0.00"
                }
            ],
            "order_id":0,
            "status":"Verified",
            "order_date":null,
            "period_start":"2015-04-01",
            "period_end":"2015-07-31",
            "order_amount":"0.00",
            "order_ccy":"EUR",
            "order_error":null,
            "publicorderident":"00000-000000-000000-0",
            "pay_date":"2015-01-1"
        }
    ]
}
```

## `GET /payments/settings/:user`

| Parameter | Required? | Type | Description |
| --- | --- | --- | --- |
| authToken | Yes | string | User's Auth Token |

Returns payment settings for `user`. Information is always blanked out by hitbox as '*****'. Broadcaster Only.

### Example URL

https://www.hitbox.tv/api/payments/settings/test-account?authToken=SuperSecret

### Example Response

```javascript
{
    "user_name":"test-account",
    "user_partner":"4",
    "group_partner":"0",
    "team_name":"bestteam",
    "emailverified":"1",
    "partner_type":"migrated",
    "settings_status":"Missing payment details",
    "user_id":"1",
    "date_added":"",
    "country":"",
    "currency":"",
    "paypal_recipient":"****",
    "bank_IBAN":"****",
    "bank_SWIFT":"****",
    "first_name":"****",
    "last_name":"****",
    "legal_name":"****",
    "address1":"****",
    "address2":"****",
    "address3":"****",
    "address4":"****",
    "mobile":"****",
    "postcode":"****",
    "city":"****",
    "region":"****",
    "birthDay":"",
    "birthMonth":"",
    "birthYear":"",
    "birth_date":"****",
    "tax_code":"****",
    "vat_code":"****"
}
```