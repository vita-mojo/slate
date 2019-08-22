---
title: Order service
language_tabs:
  - ruby: Ruby
  - python: Python
  - javascript: JavaScript
toc_footers: []
includes: []
search: true
highlight_theme: darkula
headingLevel: 2

---

<h1 id="order-service">Order service v0.0.1</h1>

> Scroll down for code samples, example requests and responses. Select a language for code samples from the tabs above or the mobile navigation menu.

order-service backend api endpoints documentations

Base URLs:

 License: MIT

# Authentication

* API Key (api_key)
    - Parameter Name: **authorization**, in: header. 

<h1 id="order-service-healthcheck">Healthcheck</h1>

## Check API healthcheck

<a id="opIdGET_healthcheck"></a>

> Code samples

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json; charset=utf-8'
}

result = RestClient.get '/healthcheck',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json; charset=utf-8'
}

r = requests.get('/healthcheck', params={

}, headers = headers)

print r.json()

```

```javascript
var headers = {
  'Accept':'application/json; charset=utf-8'

};

$.ajax({
  url: '/healthcheck',
  method: 'get',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

`GET /healthcheck`

> Example responses

> 200 Response

```json
{}
```

<h3 id="check-api-healthcheck-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|none|Inline|

<h3 id="check-api-healthcheck-responseschema">Response Schema</h3>

<aside class="success">
This operation does not require authentication
</aside>

<h1 id="order-service-commands">commands</h1>

## CommandsPlaceOrder

<a id="opIdCommandsPlaceOrder"></a>

> Code samples

```ruby
require 'rest-client'
require 'json'

headers = {
  'Content-Type' => 'application/json; charset=utf-8',
  'Accept' => 'application/json; charset=utf-8',
  'x-requested-from' => 'string',
  'store' => 'string',
  'authorization' => 'API_KEY'
}

result = RestClient.post '/v1/commands/create',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Content-Type': 'application/json; charset=utf-8',
  'Accept': 'application/json; charset=utf-8',
  'x-requested-from': 'string',
  'store': 'string',
  'authorization': 'API_KEY'
}

r = requests.post('/v1/commands/create', params={

}, headers = headers)

print r.json()

```

```javascript
var headers = {
  'Content-Type':'application/json; charset=utf-8',
  'Accept':'application/json; charset=utf-8',
  'x-requested-from':'string',
  'store':'string',
  'authorization':'API_KEY'

};

$.ajax({
  url: '/v1/commands/create',
  method: 'post',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

`POST /v1/commands/create`

> Body parameter

```json
{
  "required": [
    "payment",
    "user",
    "bundles"
  ],
  "type": "object",
  "properties": {
    "payment": {
      "required": [
        "price",
        "totalAmount"
      ],
      "type": "object",
      "properties": {
        "price": {
          "type": "number"
        },
        "vatAmount": {
          "type": "number"
        },
        "discount": {
          "type": "number"
        },
        "subtotalAmount": {
          "type": "number"
        },
        "totalAmount": {
          "type": "number"
        }
      }
    },
    "takeaway": {
      "type": "boolean"
    },
    "isAsap": {
      "type": "boolean"
    },
    "timeSlot": {
      "properties": {
        "uuid": {
          "type": "string"
        },
        "slot": {
          "type": "string"
        }
      },
      "required": [
        "uuid",
        "slot"
      ],
      "type": "object"
    },
    "table": {
      "type": "string"
    },
    "note": {
      "type": "string"
    },
    "user": {
      "required": [
        "name",
        "email",
        "extUserUUID"
      ],
      "type": "object",
      "properties": {
        "name": {
          "type": "string"
        },
        "email": {
          "type": "string"
        },
        "extUserUUID": {
          "type": "string"
        }
      }
    },
    "bundles": {
      "type": "array",
      "items": {
        "required": [
          "uuid",
          "basketUUID",
          "vatAmount",
          "taxExempt",
          "vatRateEatIn",
          "vatRateTakeaway",
          "menuUUID",
          "category",
          "name",
          "price",
          "finalPrice",
          "subtotalAmount",
          "hasModifiers",
          "type",
          "straightToPickup",
          "isGrouped",
          "itemTypes"
        ],
        "type": "object",
        "properties": {
          "uuid": {
            "type": "string"
          },
          "vatAmount": {
            "type": "number"
          },
          "taxExempt": {
            "type": "number"
          },
          "vatRateEatIn": {
            "type": "number"
          },
          "vatRateTakeaway": {
            "type": "number"
          },
          "promotion": {
            "required": [
              "uuid",
              "name",
              "value",
              "type"
            ],
            "type": "object",
            "properties": {
              "uuid": {
                "type": "string"
              },
              "name": {
                "type": "string"
              },
              "value": {
                "type": "number"
              },
              "type": {
                "type": "string"
              }
            }
          },
          "basketUUID": {
            "type": "string"
          },
          "menuUUID": {
            "type": "string"
          },
          "category": {
            "required": [
              "uuid",
              "name"
            ],
            "type": "object",
            "properties": {
              "uuid": {
                "type": "string"
              },
              "name": {
                "type": "string"
              }
            }
          },
          "name": {
            "type": "string"
          },
          "price": {
            "type": "number"
          },
          "priceEatIn": {
            "type": "number"
          },
          "finalPrice": {
            "type": "number"
          },
          "discount": {
            "type": "number"
          },
          "subtotalAmount": {
            "type": "number"
          },
          "totalAmount": {
            "type": "number"
          },
          "hasModifiers": {
            "type": "boolean"
          },
          "hasEatInPrice": {
            "type": "boolean"
          },
          "type": {
            "type": "string"
          },
          "straightToPickup": {
            "type": "boolean"
          },
          "isGrouped": {
            "type": "boolean"
          },
          "itemTypes": {
            "type": "array",
            "items": {
              "required": [
                "uuid",
                "name",
                "ticketGroup",
                "maxRestriction",
                "minRestriction",
                "items"
              ],
              "type": "object",
              "properties": {
                "uuid": {
                  "type": "string"
                },
                "name": {
                  "type": "string"
                },
                "kitchenZone": {
                  "required": [
                    "uuid",
                    "name",
                    "slug",
                    "sortOrderOnPrint",
                    "capacity"
                  ],
                  "properties": {
                    "uuid": {},
                    "name": {},
                    "slug": {},
                    "sortOrderOnPrint": {},
                    "capacity": {}
                  },
                  "type": "object"
                },
                "ticketGroup": {
                  "type": "string"
                },
                "maxRestriction": {
                  "type": "integer"
                },
                "minRestriction": {
                  "type": "integer"
                },
                "items": {
                  "type": "array",
                  "items": {
                    "required": [],
                    "type": "object",
                    "properties": {}
                  }
                }
              }
            }
          }
        }
      }
    }
  }
}
```

<h3 id="commandsplaceorder-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|x-requested-from|header|string|true|Request come from (kiosk, online, pos)|
|store|header|string|true|Store uuid|
|body|body|[OrderCreation](#schemaordercreation)|true|none|

> Example responses

> 200 Response

```json
{
  "payload": {
    "uuid": "7577a8ad-f021-4183-8f6b-6c51edb12c5e",
    "status": "pending",
    "payment": {
      "price": 0,
      "discount": 0,
      "totalAmount": 20.75,
      "till": "n1"
    },
    "takeaway": false,
    "isAsap": true,
    "timeSlot": null,
    "table": "12",
    "note": null,
    "user": {
      "name": "POS USER or Kiosk customer name",
      "email": "test@vitamojo.com",
      "extUserUUID": "43e0da9a-caa3-4304-819d-67a0a6f54af9"
    },
    "bundles": [
      {
        "uuid": "a545487-caa3-4304-819d-67a0a6f54af9",
        "basketUUID": "43e0da9a-caa3-4304-819d-67a0a6f54af9",
        "menuUUID": "sfcsdr5334538gh112",
        "taxExempt": null,
        "vatRateEatIn": 18,
        "vatRateTakeaway": 20,
        "category": {
          "uuid": "c545487-caa3-4304-819d-67a0a6f54af9",
          "name": "Coffee"
        },
        "name": "Latte",
        "price": null,
        "finalPrice": 6.1,
        "hasModifiers": true,
        "type": "customised",
        "straightToPickup": true,
        "isGrouped": true,
        "itemTypes": [
          {
            "uuid": "7dca7821-9022-4353-9240-dc3a70efa1b5",
            "name": "Base Coffee",
            "ticketGroup": null,
            "maxRestriction": 1,
            "minRestriction": 1,
            "items": [
              {
                "customizations": [
                  {
                    "type": "radio",
                    "uuid": "18540e47-70ee-4dee-890d-b687cfa35058",
                    "text": "size",
                    "variations": [
                      {
                        "uuid": "e54e0bab-eadb-4643-9fe4-3320b70ac099",
                        "unit": null,
                        "price": 2.2,
                        "step": 0,
                        "type": "radio",
                        "value": "12oz",
                        "printText": "size: 12oz"
                      },
                      {
                        "uuid": "67d81a32-75c5-4499-a244-7d99769ee9d9",
                        "unit": null,
                        "price": 2.5,
                        "step": 1,
                        "type": "radio",
                        "value": "16oz",
                        "printText": "size: 16oz"
                      }
                    ],
                    "current": 0,
                    "meta": {
                      "text": "size",
                      "default_value": "12oz"
                    }
                  },
                  {
                    "type": "range",
                    "uuid": "a112ad96-2a3d-4bee-8335-8e615a8fd1f6",
                    "current": 1,
                    "text": "Sugar",
                    "meta": {},
                    "variations": [
                      {
                        "uuid": "a45f000b-c0b6-4550-aed6-b7aa7ceef5b6",
                        "type": "range",
                        "text": "0 grams",
                        "price": 0,
                        "step": 0,
                        "value": 0,
                        "unit": {
                          "slug": "pinch",
                          "name": "Pinch",
                          "value": "1"
                        }
                      },
                      {
                        "uuid": "b97b7da1-cea6-48a8-b596-35d83fe8c053",
                        "type": "range",
                        "text": "100 grams",
                        "price": 10,
                        "step": 50,
                        "value": 50,
                        "unit": {
                          "slug": "pinch",
                          "name": "Pinch",
                          "value": "1"
                        }
                      }
                    ]
                  },
                  {
                    "type": "checkbox-group",
                    "uuid": "826a0522-6b49-11e8-8bcc-02f6c2788b90",
                    "text": "coffee extra",
                    "variations": [
                      {
                        "uuid": "817237f9-47fb-4cab-bfa9-1a752217ea41",
                        "unit": null,
                        "step": 0,
                        "value": "Syrup Shot",
                        "printText": "Syrup Shot: yes",
                        "price": 0.8,
                        "type": "checkbox-group"
                      },
                      {
                        "uuid": "6f77fb5e-792c-4f87-ac0a-b4eae94febd7",
                        "unit": null,
                        "step": 1,
                        "value": "Expresso Shot",
                        "printText": "Expresso Shot: yes",
                        "price": 0.9,
                        "type": "checkbox-group"
                      }
                    ],
                    "current": [
                      0,
                      1
                    ],
                    "meta": {
                      "text": "coffee extra"
                    }
                  }
                ],
                "price": 0,
                "taxExempt": 0,
                "vatRateEatIn": 18,
                "vatRateTakeaway": 20,
                "finalPrice": 0,
                "name": "Latte",
                "kitchenZone": {
                  "uuid": "16029865-d27a-413a-bf11-1819c043f63d",
                  "name": "Kitchen zone X",
                  "slug": "Kitchen zone X",
                  "sortOrderOnPrint": 1,
                  "capacity": 1000
                },
                "straightToPickup": false,
                "itemUUID": "ce16765c-1b62-4bbc-908c-8c27b159bf1c",
                "uuid": "16029865-d27a-413a-bf11-1819c043f63d"
              }
            ]
          }
        ]
      },
      {
        "uuid": "b545487-caa3-4304-819d-67a0a6f54af9",
        "basketUUID": "dc77bc12-f21a-462b-ad3f-f3045f895e3c",
        "menuUUID": "sfcsdr5334538gh112",
        "taxExempt": null,
        "vatRateEatIn": 18,
        "vatRateTakeaway": 20,
        "category": {
          "uuid": "c345487-caa3-4304-819d-67a0a6f54af9",
          "name": "Full English"
        },
        "name": "Full English",
        "price": null,
        "finalPrice": 14.65,
        "hasModifiers": true,
        "type": "customised",
        "straightToPickup": false,
        "isGrouped": false,
        "itemTypes": [
          {
            "uuid": "1523b582-faa7-4845-b2a0-405791da07be",
            "name": "Base Full English",
            "ticketGroup": null,
            "minRestriction": 1,
            "maxRestriction": 1,
            "items": [
              {
                "customizations": [
                  {
                    "type": "radio",
                    "uuid": "876b34ad-45654-4ds7-cdd8-bfc47686d999",
                    "text": "egg type",
                    "variations": [
                      {
                        "unit": null,
                        "step": 0,
                        "value": "poached",
                        "printText": "egg type: poached",
                        "price": 0,
                        "uuid": "3b9e0e94-4467-4608-a6b1-173feedfa0af",
                        "type": "radio"
                      },
                      {
                        "unit": null,
                        "step": 1,
                        "value": "scrambled",
                        "printText": "egg type: scrambled",
                        "price": 0,
                        "uuid": "43f26e1a-5472-43e1-b01a-d8be85f5c583",
                        "type": "radio"
                      },
                      {
                        "unit": null,
                        "step": 2,
                        "value": "fried",
                        "printText": "egg type: fried",
                        "price": 0,
                        "uuid": "0f814f7b-6f75-4d69-98c3-f654af550ae7",
                        "type": "radio"
                      },
                      {
                        "unit": null,
                        "step": 3,
                        "value": "boiled",
                        "printText": "egg type: boiled",
                        "price": 0,
                        "uuid": "1e276108-ba4d-462a-8565-7eafd28a6f6a",
                        "type": "radio"
                      }
                    ],
                    "current": 0,
                    "meta": {
                      "text": "egg type",
                      "default_value": "poached"
                    }
                  }
                ],
                "taxExempt": 1,
                "vatRateEatIn": 18,
                "vatRateTakeaway": 20,
                "price": 6.95,
                "kitchenZone": {
                  "uuid": "16029865-d27a-413a-bf11-1819c043f63d",
                  "name": "Kitchen zone X",
                  "slug": "Kitchen zone X",
                  "sortOrderOnPrint": 1,
                  "capacity": 1000
                },
                "finalPrice": 6.95,
                "name": "Full English",
                "straightToPickup": false,
                "itemUUID": "18814528-e2e5-4f87-aa49-cbf2198487ed",
                "uuid": "d40b5e1c-67cd-4269-8199-4bc48c2e65b0"
              }
            ]
          },
          {
            "uuid": "9eebe588-3388-49fb-afd1-a0accaedcddb",
            "name": "Extra Full english",
            "ticketGroup": null,
            "maxRestriction": null,
            "minRestriction": null,
            "items": [
              {
                "customizations": [],
                "price": 1,
                "finalPrice": 1,
                "name": "Avocado",
                "kitchenZone": null,
                "straightToPickup": false,
                "itemUUID": "e2b764d2-956f-41a9-b690-cb90b94395f0",
                "uuid": "947a4f59-aa78-4a3c-acbd-1287aeff7e82"
              },
              {
                "customizations": [],
                "price": 1,
                "finalPrice": 1,
                "kitchenZone": null,
                "name": "Cumberland sausage",
                "straightToPickup": false,
                "itemUUID": "9963d242-9301-4a13-bb72-c2252c5e6a29",
                "uuid": "caa15e68-dc06-41e8-9b8d-9039a74938de"
              }
            ]
          }
        ]
      }
    ]
  }
}
```

> 400 Response

```json
{
  "status": 0,
  "message": "string"
}
```

<h3 id="commandsplaceorder-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Response Order entity|[Order](#schemaorder)|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad request|[BadRequest](#schemabadrequest)|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Unautorized|[UnautorizedException](#schemaunautorizedexception)|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Not found|[NotFound](#schemanotfound)|
|503|[Service Unavailable](https://tools.ietf.org/html/rfc7231#section-6.6.4)|Service unavailable|[ServiceUnavailable](#schemaserviceunavailable)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
api_key
</aside>

## CommandsSendEmailReceipt

<a id="opIdCommandsSendEmailReceipt"></a>

> Code samples

```ruby
require 'rest-client'
require 'json'

headers = {
  'Content-Type' => 'application/json',
  'Accept' => 'application/json',
  'x-requested-from' => 'string',
  'store' => 'string',
  'authorization' => 'API_KEY'
}

result = RestClient.post '/v1/commands/email-receipt',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json',
  'x-requested-from': 'string',
  'store': 'string',
  'authorization': 'API_KEY'
}

r = requests.post('/v1/commands/email-receipt', params={

}, headers = headers)

print r.json()

```

```javascript
var headers = {
  'Content-Type':'application/json',
  'Accept':'application/json',
  'x-requested-from':'string',
  'store':'string',
  'authorization':'API_KEY'

};

$.ajax({
  url: '/v1/commands/email-receipt',
  method: 'post',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

`POST /v1/commands/email-receipt`

> Body parameter

```json
{
  "orderUUID": "string",
  "email": "string",
  "optIn": true
}
```

<h3 id="commandssendemailreceipt-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|x-requested-from|header|string|true|Request come from (kiosk, online, pos)|
|store|header|string|true|Store uuid|
|body|body|[OrderSendEmail](#schemaordersendemail)|true|none|

> Example responses

> 400 Response

```json
{
  "status": 0,
  "message": "string"
}
```

<h3 id="commandssendemailreceipt-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|204|[No Content](https://tools.ietf.org/html/rfc7231#section-6.3.5)|No content|None|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad request|[BadRequest](#schemabadrequest)|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Unautorized|[UnautorizedException](#schemaunautorizedexception)|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Not found|[NotFound](#schemanotfound)|
|503|[Service Unavailable](https://tools.ietf.org/html/rfc7231#section-6.6.4)|Service unavailable|[ServiceUnavailable](#schemaserviceunavailable)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
api_key
</aside>

## CommandsCancelOrder

<a id="opIdCommandsCancelOrder"></a>

> Code samples

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json',
  'authorization' => 'API_KEY'
}

result = RestClient.put '/v1/commands/cancel/{entityUUID}',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json',
  'authorization': 'API_KEY'
}

r = requests.put('/v1/commands/cancel/{entityUUID}', params={

}, headers = headers)

print r.json()

```

```javascript
var headers = {
  'Accept':'application/json',
  'authorization':'API_KEY'

};

$.ajax({
  url: '/v1/commands/cancel/{entityUUID}',
  method: 'put',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

`PUT /v1/commands/cancel/{entityUUID}`

<h3 id="commandscancelorder-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|entityUUID|path|string|true|none|

> Example responses

> 200 Response

```json
{
  "entityUUID": "string"
}
```

<h3 id="commandscancelorder-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Response Order UUID|[EntityUUID](#schemaentityuuid)|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad request|[BadRequest](#schemabadrequest)|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Unautorized|[UnautorizedException](#schemaunautorizedexception)|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Not found|[NotFound](#schemanotfound)|
|503|[Service Unavailable](https://tools.ietf.org/html/rfc7231#section-6.6.4)|Service unavailable|[ServiceUnavailable](#schemaserviceunavailable)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
api_key
</aside>

## CommandsUpdateOrderStatus

<a id="opIdCommandsUpdateOrderStatus"></a>

> Code samples

```ruby
require 'rest-client'
require 'json'

headers = {
  'Content-Type' => 'application/json',
  'Accept' => 'application/json',
  'authorization' => 'API_KEY'
}

result = RestClient.put '/v1/commands/change-status/{entityUUID}',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json',
  'authorization': 'API_KEY'
}

r = requests.put('/v1/commands/change-status/{entityUUID}', params={

}, headers = headers)

print r.json()

```

```javascript
var headers = {
  'Content-Type':'application/json',
  'Accept':'application/json',
  'authorization':'API_KEY'

};

$.ajax({
  url: '/v1/commands/change-status/{entityUUID}',
  method: 'put',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

`PUT /v1/commands/change-status/{entityUUID}`

> Body parameter

```json
{
  "transitionAlias": "string",
  "orderStatus": "string"
}
```

<h3 id="commandsupdateorderstatus-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|[OrderStatus](#schemaorderstatus)|true|none|
|entityUUID|path|string|true|none|

> Example responses

> 200 Response

```json
{
  "entityUUID": "string"
}
```

<h3 id="commandsupdateorderstatus-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Response Order UUID|[EntityUUID](#schemaentityuuid)|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad request|[BadRequest](#schemabadrequest)|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Unautorized|[UnautorizedException](#schemaunautorizedexception)|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Not Found|[NotFound](#schemanotfound)|
|503|[Service Unavailable](https://tools.ietf.org/html/rfc7231#section-6.6.4)|Service unavailable|[ServiceUnavailable](#schemaserviceunavailable)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
api_key
</aside>

## CommandsOrderPaymentStatus

<a id="opIdCommandsOrderPaymentStatus"></a>

> Code samples

```ruby
require 'rest-client'
require 'json'

headers = {
  'Content-Type' => 'application/json',
  'Accept' => 'application/json; charset=utf-8',
  'authorization' => 'API_KEY'
}

result = RestClient.put '/v1/commands/payment-status/{orderUUID}',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json; charset=utf-8',
  'authorization': 'API_KEY'
}

r = requests.put('/v1/commands/payment-status/{orderUUID}', params={

}, headers = headers)

print r.json()

```

```javascript
var headers = {
  'Content-Type':'application/json',
  'Accept':'application/json; charset=utf-8',
  'authorization':'API_KEY'

};

$.ajax({
  url: '/v1/commands/payment-status/{orderUUID}',
  method: 'put',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

`PUT /v1/commands/payment-status/{orderUUID}`

> Body parameter

```json
{
  "provider": "string",
  "currency": "string",
  "status": "string",
  "till": "string",
  "meta": "string"
}
```

<h3 id="commandsorderpaymentstatus-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|[PaymentStatus](#schemapaymentstatus)|true|none|
|orderUUID|path|string|true|none|

> Example responses

> 200 Response

```json
{
  "currency": "GBP",
  "provider": "stripe",
  "status": "success",
  "till": "till1",
  "meta": null
}
```

> 400 Response

```json
{
  "status": 0,
  "message": "string"
}
```

<h3 id="commandsorderpaymentstatus-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Ok|[OrderPayment](#schemaorderpayment)|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad request|[BadRequest](#schemabadrequest)|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Unautorized|[UnautorizedException](#schemaunautorizedexception)|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Not found|[NotFound](#schemanotfound)|
|503|[Service Unavailable](https://tools.ietf.org/html/rfc7231#section-6.6.4)|Service unavailable|[ServiceUnavailable](#schemaserviceunavailable)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
api_key
</aside>

## CommandsOrderPromotUpdate

<a id="opIdCommandsOrderPromotUpdate"></a>

> Code samples

```ruby
require 'rest-client'
require 'json'

headers = {
  'Content-Type' => 'application/json',
  'Accept' => 'application/json',
  'store' => 'string',
  'authorization' => 'API_KEY'
}

result = RestClient.put '/v1/commands/change-promo/{entityUUID}',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json',
  'store': 'string',
  'authorization': 'API_KEY'
}

r = requests.put('/v1/commands/change-promo/{entityUUID}', params={

}, headers = headers)

print r.json()

```

```javascript
var headers = {
  'Content-Type':'application/json',
  'Accept':'application/json',
  'store':'string',
  'authorization':'API_KEY'

};

$.ajax({
  url: '/v1/commands/change-promo/{entityUUID}',
  method: 'put',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

`PUT /v1/commands/change-promo/{entityUUID}`

> Body parameter

```json
{
  "bundles": [
    {
      "uuid": "string",
      "finalPrice": 0,
      "subtotalAmount": 0,
      "promotion": {
        "uuid": "string",
        "name": "string",
        "value": 0,
        "type": "string"
      },
      "itemTypes": [
        {
          "items": [
            {
              "itemUUID": "string",
              "finalPrice": 0,
              "subtotalAmount": 0
            }
          ]
        }
      ]
    }
  ]
}
```

<h3 id="commandsorderpromotupdate-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|store|header|string|true|Store uuid|
|body|body|[OrderBundlesPromo](#schemaorderbundlespromo)|true|none|
|entityUUID|path|string|true|none|

> Example responses

> 200 Response

```json
{
  "entityUUID": "string"
}
```

<h3 id="commandsorderpromotupdate-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Response Order UUID|[EntityUUID](#schemaentityuuid)|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad request|[BadRequest](#schemabadrequest)|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Unautorized|[UnautorizedException](#schemaunautorizedexception)|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Not found|[NotFound](#schemanotfound)|
|503|[Service Unavailable](https://tools.ietf.org/html/rfc7231#section-6.6.4)|Service unavailable|[ServiceUnavailable](#schemaserviceunavailable)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
api_key
</aside>

## CommandsOrderTakeawayStatusChanged

<a id="opIdCommandsOrderTakeawayStatusChanged"></a>

> Code samples

```ruby
require 'rest-client'
require 'json'

headers = {
  'Content-Type' => 'application/json',
  'Accept' => 'application/json',
  'authorization' => 'API_KEY'
}

result = RestClient.put '/v1/commands/takeaway-status/{entityUUID}',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json',
  'authorization': 'API_KEY'
}

r = requests.put('/v1/commands/takeaway-status/{entityUUID}', params={

}, headers = headers)

print r.json()

```

```javascript
var headers = {
  'Content-Type':'application/json',
  'Accept':'application/json',
  'authorization':'API_KEY'

};

$.ajax({
  url: '/v1/commands/takeaway-status/{entityUUID}',
  method: 'put',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

`PUT /v1/commands/takeaway-status/{entityUUID}`

> Body parameter

```json
{
  "status": true
}
```

<h3 id="commandsordertakeawaystatuschanged-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|[OrderTakeawayFlag](#schemaordertakeawayflag)|true|none|
|entityUUID|path|string|true|none|

> Example responses

> 200 Response

```json
{
  "entityUUID": "string"
}
```

<h3 id="commandsordertakeawaystatuschanged-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Response Order UUID|[EntityUUID](#schemaentityuuid)|
|204|[No Content](https://tools.ietf.org/html/rfc7231#section-6.3.5)|No content|None|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad request|[BadRequest](#schemabadrequest)|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Unautorized|[UnautorizedException](#schemaunautorizedexception)|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Not found|[NotFound](#schemanotfound)|
|503|[Service Unavailable](https://tools.ietf.org/html/rfc7231#section-6.6.4)|Service unavailable|[ServiceUnavailable](#schemaserviceunavailable)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
api_key
</aside>

## CommandsOrderRemoveBundles

<a id="opIdCommandsOrderRemoveBundles"></a>

> Code samples

```ruby
require 'rest-client'
require 'json'

headers = {
  'Content-Type' => 'application/json',
  'Accept' => 'application/json',
  'authorization' => 'API_KEY'
}

result = RestClient.put '/v1/commands/remove-bundles/{orderUUID}',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json',
  'authorization': 'API_KEY'
}

r = requests.put('/v1/commands/remove-bundles/{orderUUID}', params={

}, headers = headers)

print r.json()

```

```javascript
var headers = {
  'Content-Type':'application/json',
  'Accept':'application/json',
  'authorization':'API_KEY'

};

$.ajax({
  url: '/v1/commands/remove-bundles/{orderUUID}',
  method: 'put',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

`PUT /v1/commands/remove-bundles/{orderUUID}`

> Body parameter

```json
{
  "basketUUIDs": [
    "string"
  ],
  "payment": {
    "price": 0,
    "totalAmount": 0,
    "subtotalAmount": 0
  }
}
```

<h3 id="commandsorderremovebundles-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|[OrderRemoveBundle](#schemaorderremovebundle)|true|none|
|orderUUID|path|string|true|none|

> Example responses

> 200 Response

```json
{
  "payload": {
    "orderUUID": "7577a8ad-f021-4183-8f6b-6c51edb12c5e"
  }
}
```

> 400 Response

```json
{
  "statusCode": 400,
  "message": "Please select store first!"
}
```

> 401 Response

```json
{
  "statusCode": 401,
  "message": {
    "statusCode": 401,
    "error": "Unauthorized"
  }
}
```

> 404 Response

```json
{
  "statusCode": 404,
  "message": "Cannot GET ..."
}
```

> 503 Response

```json
{
  "statusCode": 500,
  "message": "Internal server error!"
}
```

<h3 id="commandsorderremovebundles-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Response Order orderUUID|[OrderUUID](#schemaorderuuid)|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad request|[BadRequest](#schemabadrequest)|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Unautorized|[UnautorizedException](#schemaunautorizedexception)|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Not found|[NotFound](#schemanotfound)|
|503|[Service Unavailable](https://tools.ietf.org/html/rfc7231#section-6.6.4)|Service unavailable|[ServiceUnavailable](#schemaserviceunavailable)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
api_key
</aside>

<h1 id="order-service-queries">queries</h1>

## QueriesGetOrdersByStatuses

<a id="opIdQueriesGetOrdersByStatuses"></a>

> Code samples

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json',
  'store' => 'string',
  'authorization' => 'API_KEY'
}

result = RestClient.get '/v1/queries/orders',
  params: {
  'statuses[]' => 'array[string]'
}, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json',
  'store': 'string',
  'authorization': 'API_KEY'
}

r = requests.get('/v1/queries/orders', params={
  'statuses[]': [
  "string"
]
}, headers = headers)

print r.json()

```

```javascript
var headers = {
  'Accept':'application/json',
  'store':'string',
  'authorization':'API_KEY'

};

$.ajax({
  url: '/v1/queries/orders',
  method: 'get',
  data: '?statuses%5B%5D=string',
  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

`GET /v1/queries/orders`

Get Orders by Statuses

<h3 id="queriesgetordersbystatuses-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|store|header|string|true|Store uuid|
|statuses[]|query|array[string]|true|Order statuses (pending, confirmed, in-production, ready-to-collect, collected, cancelled, refunded, remake, unprocessed, till-paid, till-deleted)|

> Example responses

> 400 Response

```json
{
  "status": 0,
  "message": "string"
}
```

<h3 id="queriesgetordersbystatuses-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Order by Statuses|None|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad request|[BadRequest](#schemabadrequest)|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Unautorized|[UnautorizedException](#schemaunautorizedexception)|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Not found|[NotFound](#schemanotfound)|
|503|[Service Unavailable](https://tools.ietf.org/html/rfc7231#section-6.6.4)|Service unavailable|[ServiceUnavailable](#schemaserviceunavailable)|

<h3 id="queriesgetordersbystatuses-responseschema">Response Schema</h3>

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
api_key
</aside>

## QueriesGetHistoryOrders

<a id="opIdQueriesGetHistoryOrders"></a>

> Code samples

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json',
  'store' => 'string',
  'authorization' => 'API_KEY'
}

result = RestClient.get '/v1/queries/orders/history',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json',
  'store': 'string',
  'authorization': 'API_KEY'
}

r = requests.get('/v1/queries/orders/history', params={

}, headers = headers)

print r.json()

```

```javascript
var headers = {
  'Accept':'application/json',
  'store':'string',
  'authorization':'API_KEY'

};

$.ajax({
  url: '/v1/queries/orders/history',
  method: 'get',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

`GET /v1/queries/orders/history`

Get all orders in a time range

<h3 id="queriesgethistoryorders-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|store|header|string|true|Store uuid|
|search|query|string|false|Search order by (serialNumber, user.name, user.email)|
|startDate|query|string|false|Start datetime format (ISO format)|
|endDate|query|string|false|End datetime format (ISO format)|
|limit|query|number|false|Limit items per page|
|lastEvaluatedKey|query|string|false|Send Last evaluated key to get next page|

> Example responses

> 200 Response

```json
{
  "meta": {
    "extStoreUUID": "string",
    "search": "string",
    "startDate": "string",
    "endDate": "string",
    "lastEvaluatedKey": "string"
  },
  "payload": [
    {
      "source": "string",
      "uuid": "string",
      "user": {
        "name": "string",
        "email": "string",
        "extUserUUID": "string"
      },
      "serialNumber": "string",
      "status": "string",
      "payment": {
        "totalAmount": 0,
        "discount": 0,
        "price": 0
      },
      "createdAt": "string",
      "updatedAt": "string",
      "orderNumber": "string"
    }
  ]
}
```

<h3 id="queriesgethistoryorders-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Orders|[OrdersHistoryBody](#schemaordershistorybody)|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad request|[BadRequest](#schemabadrequest)|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Unautorized|[UnautorizedException](#schemaunautorizedexception)|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Not found|[NotFound](#schemanotfound)|
|503|[Service Unavailable](https://tools.ietf.org/html/rfc7231#section-6.6.4)|Service unavailable|[ServiceUnavailable](#schemaserviceunavailable)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
api_key
</aside>

## QueriesGetUserOrderHistory

<a id="opIdQueriesGetUserOrderHistory"></a>

> Code samples

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json',
  'authorization' => 'API_KEY'
}

result = RestClient.get '/v1/queries/orders/user-history',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json',
  'authorization': 'API_KEY'
}

r = requests.get('/v1/queries/orders/user-history', params={

}, headers = headers)

print r.json()

```

```javascript
var headers = {
  'Accept':'application/json',
  'authorization':'API_KEY'

};

$.ajax({
  url: '/v1/queries/orders/user-history',
  method: 'get',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

`GET /v1/queries/orders/user-history`

Get User order history by range of date or filtered by serialNumber

<h3 id="queriesgetuserorderhistory-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|search|query|string|false|Search order by (serialNumber, user.name, user.email)|
|startDate|query|string|false|Start datetime format (ISO format)|
|endDate|query|string|false|End datetime format (ISO format)|
|limit|query|number|false|Limit items per page|
|lastEvaluatedKey|query|string|false|Send Last evaluated key to get next page|

> Example responses

> 200 Response

```json
{
  "meta": {
    "search": "string",
    "startDate": "string",
    "endDate": "string",
    "lastEvaluatedKey": "string"
  },
  "payload": [
    {
      "payment": {
        "totalAmount": 0
      },
      "source": "string",
      "uuid": "string",
      "storeUUID": "string",
      "serialNumber": "string",
      "status": "string",
      "collectionDate": "string",
      "createdAt": "string",
      "updatedAt": "string",
      "bundles": [
        {
          "itemTypes": [
            {
              "name": "string",
              "ticketGroup": "string",
              "minRestriction": 0,
              "uuid": "string",
              "items": [
                {
                  "name": "string",
                  "itemUUID": "string",
                  "uuid": "string",
                  "price": 0,
                  "customizations": [
                    {}
                  ]
                }
              ],
              "maxRestriction": 0
            }
          ],
          "straightToPickup": true,
          "price": 0,
          "name": "string",
          "description": "string",
          "isGrouped": true,
          "isPrintable": true,
          "type": "string",
          "uuid": "string"
        }
      ]
    }
  ]
}
```

<h3 id="queriesgetuserorderhistory-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Orders|[UserOrdersHistoryBody](#schemauserordershistorybody)|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad request|[BadRequest](#schemabadrequest)|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Unautorized|[UnautorizedException](#schemaunautorizedexception)|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Not found|[NotFound](#schemanotfound)|
|503|[Service Unavailable](https://tools.ietf.org/html/rfc7231#section-6.6.4)|Service unavailable|[ServiceUnavailable](#schemaserviceunavailable)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
api_key
</aside>

## QueriesGetOrder

<a id="opIdQueriesGetOrder"></a>

> Code samples

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json; charset=utf-8',
  'authorization' => 'API_KEY'
}

result = RestClient.get '/v1/queries/find/{uuid}',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json; charset=utf-8',
  'authorization': 'API_KEY'
}

r = requests.get('/v1/queries/find/{uuid}', params={

}, headers = headers)

print r.json()

```

```javascript
var headers = {
  'Accept':'application/json; charset=utf-8',
  'authorization':'API_KEY'

};

$.ajax({
  url: '/v1/queries/find/{uuid}',
  method: 'get',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

`GET /v1/queries/find/{uuid}`

<h3 id="queriesgetorder-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|uuid|path|string|true|Order UUID|

> Example responses

> 200 Response

```json
{
  "payload": {
    "uuid": "7577a8ad-f021-4183-8f6b-6c51edb12c5e",
    "status": "pending",
    "payment": {
      "price": 0,
      "discount": 0,
      "totalAmount": 20.75,
      "till": "n1"
    },
    "takeaway": false,
    "isAsap": true,
    "timeSlot": null,
    "table": "12",
    "note": null,
    "user": {
      "name": "POS USER or Kiosk customer name",
      "email": "test@vitamojo.com",
      "extUserUUID": "43e0da9a-caa3-4304-819d-67a0a6f54af9"
    },
    "bundles": [
      {
        "uuid": "a545487-caa3-4304-819d-67a0a6f54af9",
        "basketUUID": "43e0da9a-caa3-4304-819d-67a0a6f54af9",
        "menuUUID": "sfcsdr5334538gh112",
        "taxExempt": null,
        "vatRateEatIn": 18,
        "vatRateTakeaway": 20,
        "category": {
          "uuid": "c545487-caa3-4304-819d-67a0a6f54af9",
          "name": "Coffee"
        },
        "name": "Latte",
        "price": null,
        "finalPrice": 6.1,
        "hasModifiers": true,
        "type": "customised",
        "straightToPickup": true,
        "isGrouped": true,
        "itemTypes": [
          {
            "uuid": "7dca7821-9022-4353-9240-dc3a70efa1b5",
            "name": "Base Coffee",
            "ticketGroup": null,
            "maxRestriction": 1,
            "minRestriction": 1,
            "items": [
              {
                "customizations": [
                  {
                    "type": "radio",
                    "uuid": "18540e47-70ee-4dee-890d-b687cfa35058",
                    "text": "size",
                    "variations": [
                      {
                        "uuid": "e54e0bab-eadb-4643-9fe4-3320b70ac099",
                        "unit": null,
                        "price": 2.2,
                        "step": 0,
                        "type": "radio",
                        "value": "12oz",
                        "printText": "size: 12oz"
                      },
                      {
                        "uuid": "67d81a32-75c5-4499-a244-7d99769ee9d9",
                        "unit": null,
                        "price": 2.5,
                        "step": 1,
                        "type": "radio",
                        "value": "16oz",
                        "printText": "size: 16oz"
                      }
                    ],
                    "current": 0,
                    "meta": {
                      "text": "size",
                      "default_value": "12oz"
                    }
                  },
                  {
                    "type": "range",
                    "uuid": "a112ad96-2a3d-4bee-8335-8e615a8fd1f6",
                    "current": 1,
                    "text": "Sugar",
                    "meta": {},
                    "variations": [
                      {
                        "uuid": "a45f000b-c0b6-4550-aed6-b7aa7ceef5b6",
                        "type": "range",
                        "text": "0 grams",
                        "price": 0,
                        "step": 0,
                        "value": 0,
                        "unit": {
                          "slug": "pinch",
                          "name": "Pinch",
                          "value": "1"
                        }
                      },
                      {
                        "uuid": "b97b7da1-cea6-48a8-b596-35d83fe8c053",
                        "type": "range",
                        "text": "100 grams",
                        "price": 10,
                        "step": 50,
                        "value": 50,
                        "unit": {
                          "slug": "pinch",
                          "name": "Pinch",
                          "value": "1"
                        }
                      }
                    ]
                  },
                  {
                    "type": "checkbox-group",
                    "uuid": "826a0522-6b49-11e8-8bcc-02f6c2788b90",
                    "text": "coffee extra",
                    "variations": [
                      {
                        "uuid": "817237f9-47fb-4cab-bfa9-1a752217ea41",
                        "unit": null,
                        "step": 0,
                        "value": "Syrup Shot",
                        "printText": "Syrup Shot: yes",
                        "price": 0.8,
                        "type": "checkbox-group"
                      },
                      {
                        "uuid": "6f77fb5e-792c-4f87-ac0a-b4eae94febd7",
                        "unit": null,
                        "step": 1,
                        "value": "Expresso Shot",
                        "printText": "Expresso Shot: yes",
                        "price": 0.9,
                        "type": "checkbox-group"
                      }
                    ],
                    "current": [
                      0,
                      1
                    ],
                    "meta": {
                      "text": "coffee extra"
                    }
                  }
                ],
                "price": 0,
                "taxExempt": 0,
                "vatRateEatIn": 18,
                "vatRateTakeaway": 20,
                "finalPrice": 0,
                "name": "Latte",
                "kitchenZone": {
                  "uuid": "16029865-d27a-413a-bf11-1819c043f63d",
                  "name": "Kitchen zone X",
                  "slug": "Kitchen zone X",
                  "sortOrderOnPrint": 1,
                  "capacity": 1000
                },
                "straightToPickup": false,
                "itemUUID": "ce16765c-1b62-4bbc-908c-8c27b159bf1c",
                "uuid": "16029865-d27a-413a-bf11-1819c043f63d"
              }
            ]
          }
        ]
      },
      {
        "uuid": "b545487-caa3-4304-819d-67a0a6f54af9",
        "basketUUID": "dc77bc12-f21a-462b-ad3f-f3045f895e3c",
        "menuUUID": "sfcsdr5334538gh112",
        "taxExempt": null,
        "vatRateEatIn": 18,
        "vatRateTakeaway": 20,
        "category": {
          "uuid": "c345487-caa3-4304-819d-67a0a6f54af9",
          "name": "Full English"
        },
        "name": "Full English",
        "price": null,
        "finalPrice": 14.65,
        "hasModifiers": true,
        "type": "customised",
        "straightToPickup": false,
        "isGrouped": false,
        "itemTypes": [
          {
            "uuid": "1523b582-faa7-4845-b2a0-405791da07be",
            "name": "Base Full English",
            "ticketGroup": null,
            "minRestriction": 1,
            "maxRestriction": 1,
            "items": [
              {
                "customizations": [
                  {
                    "type": "radio",
                    "uuid": "876b34ad-45654-4ds7-cdd8-bfc47686d999",
                    "text": "egg type",
                    "variations": [
                      {
                        "unit": null,
                        "step": 0,
                        "value": "poached",
                        "printText": "egg type: poached",
                        "price": 0,
                        "uuid": "3b9e0e94-4467-4608-a6b1-173feedfa0af",
                        "type": "radio"
                      },
                      {
                        "unit": null,
                        "step": 1,
                        "value": "scrambled",
                        "printText": "egg type: scrambled",
                        "price": 0,
                        "uuid": "43f26e1a-5472-43e1-b01a-d8be85f5c583",
                        "type": "radio"
                      },
                      {
                        "unit": null,
                        "step": 2,
                        "value": "fried",
                        "printText": "egg type: fried",
                        "price": 0,
                        "uuid": "0f814f7b-6f75-4d69-98c3-f654af550ae7",
                        "type": "radio"
                      },
                      {
                        "unit": null,
                        "step": 3,
                        "value": "boiled",
                        "printText": "egg type: boiled",
                        "price": 0,
                        "uuid": "1e276108-ba4d-462a-8565-7eafd28a6f6a",
                        "type": "radio"
                      }
                    ],
                    "current": 0,
                    "meta": {
                      "text": "egg type",
                      "default_value": "poached"
                    }
                  }
                ],
                "taxExempt": 1,
                "vatRateEatIn": 18,
                "vatRateTakeaway": 20,
                "price": 6.95,
                "kitchenZone": {
                  "uuid": "16029865-d27a-413a-bf11-1819c043f63d",
                  "name": "Kitchen zone X",
                  "slug": "Kitchen zone X",
                  "sortOrderOnPrint": 1,
                  "capacity": 1000
                },
                "finalPrice": 6.95,
                "name": "Full English",
                "straightToPickup": false,
                "itemUUID": "18814528-e2e5-4f87-aa49-cbf2198487ed",
                "uuid": "d40b5e1c-67cd-4269-8199-4bc48c2e65b0"
              }
            ]
          },
          {
            "uuid": "9eebe588-3388-49fb-afd1-a0accaedcddb",
            "name": "Extra Full english",
            "ticketGroup": null,
            "maxRestriction": null,
            "minRestriction": null,
            "items": [
              {
                "customizations": [],
                "price": 1,
                "finalPrice": 1,
                "name": "Avocado",
                "kitchenZone": null,
                "straightToPickup": false,
                "itemUUID": "e2b764d2-956f-41a9-b690-cb90b94395f0",
                "uuid": "947a4f59-aa78-4a3c-acbd-1287aeff7e82"
              },
              {
                "customizations": [],
                "price": 1,
                "finalPrice": 1,
                "kitchenZone": null,
                "name": "Cumberland sausage",
                "straightToPickup": false,
                "itemUUID": "9963d242-9301-4a13-bb72-c2252c5e6a29",
                "uuid": "caa15e68-dc06-41e8-9b8d-9039a74938de"
              }
            ]
          }
        ]
      }
    ]
  }
}
```

> 400 Response

> 401 Response

```json
{
  "status": 0,
  "message": "string"
}
```

<h3 id="queriesgetorder-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Order|[Order](#schemaorder)|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad request|[BadRequest](#schemabadrequest)|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Unautorized|[UnautorizedException](#schemaunautorizedexception)|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Not found|[NotFound](#schemanotfound)|
|503|[Service Unavailable](https://tools.ietf.org/html/rfc7231#section-6.6.4)|Service unavailable|[ServiceUnavailable](#schemaserviceunavailable)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
api_key
</aside>

<h1 id="order-service-reports">reports</h1>

## GetReportsByStore

<a id="opIdGetReportsByStore"></a>

> Code samples

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json',
  'store' => 'string',
  'authorization' => 'API_KEY'
}

result = RestClient.get '/v1/reports',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json',
  'store': 'string',
  'authorization': 'API_KEY'
}

r = requests.get('/v1/reports', params={

}, headers = headers)

print r.json()

```

```javascript
var headers = {
  'Accept':'application/json',
  'store':'string',
  'authorization':'API_KEY'

};

$.ajax({
  url: '/v1/reports',
  method: 'get',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

`GET /v1/reports`

Get Reports by Store

<h3 id="getreportsbystore-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|store|header|string|true|Store uuid|
|startDate|query|string|false|Start datetime format|
|endDate|query|string|false|End datetime format|
|limit|query|number|false|Limit|
|type|query|string|false|report type (x-report/z-report)|
|lastEvaluatedKey|query|string|false|Send Last evaluated key to get next page|

> Example responses

> 200 Response

```json
{
  "payload": {
    "items": [
      {
        "uuid": "ec410b01-936f-42c7-8e58-3824bdbde5b3",
        "createdAt": "2019-05-27T12:04:45.000Z",
        "fromDate": "2019-05-27T12:04:45.000Z",
        "type": "z_report"
      },
      {
        "uuid": "ec410b01-936f-42c7-8e58-3824bdbde5b3",
        "createdAt": "2019-05-27T12:04:45.000Z",
        "fromDate": "2019-05-27T12:04:45.000Z",
        "type": "x_report"
      }
    ],
    "meta": {
      "lastEvaluatedKey": "ec410b01-936f-42c7-8e58-3824bdbde5b3.1559289271470",
      "startDate": "2019-05-31T00:00:00.000+03:00",
      "endDate": "2019-05-31T23:59:59.999+03:00"
    }
  }
}
```

> 400 Response

```json
{
  "status": 0,
  "message": "string"
}
```

<h3 id="getreportsbystore-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Report by store|[OrderReports](#schemaorderreports)|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad request|[BadRequest](#schemabadrequest)|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Unautorized|[UnautorizedException](#schemaunautorizedexception)|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Not found|[NotFound](#schemanotfound)|
|503|[Service Unavailable](https://tools.ietf.org/html/rfc7231#section-6.6.4)|Service unavailable|[ServiceUnavailable](#schemaserviceunavailable)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
api_key
</aside>

## GetReportByUUID

<a id="opIdGetReportByUUID"></a>

> Code samples

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json',
  'authorization' => 'API_KEY'
}

result = RestClient.get '/v1/reports/{uuid}',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json',
  'authorization': 'API_KEY'
}

r = requests.get('/v1/reports/{uuid}', params={

}, headers = headers)

print r.json()

```

```javascript
var headers = {
  'Accept':'application/json',
  'authorization':'API_KEY'

};

$.ajax({
  url: '/v1/reports/{uuid}',
  method: 'get',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

`GET /v1/reports/{uuid}`

Get Report by UUID

<h3 id="getreportbyuuid-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|uuid|path|string|true|none|

> Example responses

> 200 Response

```json
{
  "payload": {
    "uuid": "ec410b01-936f-42c7-8e58-3824bdbde5b3",
    "createdAt": "2019-05-27T12:04:45.000Z",
    "fromDate": "2019-05-27T00:00:00.000Z",
    "refunds": 0,
    "discount": 0,
    "grossSales": 0,
    "totalTender": 0,
    "transactionsCount": 0,
    "vatableSales": 0,
    "nonVatableSales": 0,
    "paymentProviders": {
      "cash": 0,
      "stripe": 0
    },
    "tills": [
      {
        "id": "TM-M30",
        "refunds": 0,
        "discount": 0,
        "grossSales": 0,
        "totalTender": 0,
        "transactionsCount": 0,
        "vatableSales": 0,
        "nonVatableSales": 0,
        "paymentProviders": {
          "cash": 0,
          "stripe": 0
        }
      }
    ],
    "type": "z_report"
  }
}
```

> 400 Response

```json
{
  "status": 0,
  "message": "string"
}
```

<h3 id="getreportbyuuid-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Report by uuid|[OrderReport](#schemaorderreport)|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad request|[BadRequest](#schemabadrequest)|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Unautorized|[UnautorizedException](#schemaunautorizedexception)|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Not found|[NotFound](#schemanotfound)|
|503|[Service Unavailable](https://tools.ietf.org/html/rfc7231#section-6.6.4)|Service unavailable|[ServiceUnavailable](#schemaserviceunavailable)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
api_key
</aside>

## CreateReport

<a id="opIdCreateReport"></a>

> Code samples

```ruby
require 'rest-client'
require 'json'

headers = {
  'Content-Type' => 'application/json',
  'Accept' => 'application/json',
  'store' => 'string',
  'authorization' => 'API_KEY'
}

result = RestClient.post '/v1/reports/generate-report',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json',
  'store': 'string',
  'authorization': 'API_KEY'
}

r = requests.post('/v1/reports/generate-report', params={

}, headers = headers)

print r.json()

```

```javascript
var headers = {
  'Content-Type':'application/json',
  'Accept':'application/json',
  'store':'string',
  'authorization':'API_KEY'

};

$.ajax({
  url: '/v1/reports/generate-report',
  method: 'post',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

`POST /v1/reports/generate-report`

create report

> Body parameter

```json
{
  "type": "string"
}
```

<h3 id="createreport-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|store|header|string|true|Store uuid|
|body|body|[GenerateReport](#schemageneratereport)|true|none|

> Example responses

> 200 Response

```json
{
  "payload": {
    "uuid": "ec410b01-936f-42c7-8e58-3824bdbde5b3",
    "createdAt": "2019-05-27T12:04:45.000Z",
    "fromDate": "2019-05-27T00:00:00.000Z",
    "refunds": 0,
    "discount": 0,
    "grossSales": 0,
    "totalTender": 0,
    "transactionsCount": 0,
    "vatableSales": 0,
    "nonVatableSales": 0,
    "paymentProviders": {
      "cash": 0,
      "stripe": 0
    },
    "tills": [
      {
        "id": "TM-M30",
        "refunds": 0,
        "discount": 0,
        "grossSales": 0,
        "totalTender": 0,
        "transactionsCount": 0,
        "vatableSales": 0,
        "nonVatableSales": 0,
        "paymentProviders": {
          "cash": 0,
          "stripe": 0
        }
      }
    ],
    "type": "z_report"
  }
}
```

> 400 Response

```json
{
  "status": 0,
  "message": "string"
}
```

<h3 id="createreport-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Report by uuid|[OrderReport](#schemaorderreport)|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad request|[BadRequest](#schemabadrequest)|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Unautorized|[UnautorizedException](#schemaunautorizedexception)|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Not found|[NotFound](#schemanotfound)|
|503|[Service Unavailable](https://tools.ietf.org/html/rfc7231#section-6.6.4)|Service unavailable|[ServiceUnavailable](#schemaserviceunavailable)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
api_key
</aside>

<h1 id="order-service-pusher">pusher</h1>

## Get Authorized

<a id="opIdGet Authorized"></a>

> Code samples

```ruby
require 'rest-client'
require 'json'

headers = {
  'Content-Type' => 'application/json',
  'Accept' => 'application/json',
  'authorization' => 'API_KEY'
}

result = RestClient.post '/v1/pusher/auth',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json',
  'authorization': 'API_KEY'
}

r = requests.post('/v1/pusher/auth', params={

}, headers = headers)

print r.json()

```

```javascript
var headers = {
  'Content-Type':'application/json',
  'Accept':'application/json',
  'authorization':'API_KEY'

};

$.ajax({
  url: '/v1/pusher/auth',
  method: 'post',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

`POST /v1/pusher/auth`

Pusher authorisation

> Body parameter

```json
{
  "socket_id": "string",
  "channel_name": "string"
}
```

<h3 id="get-authorized-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|[PusherAuthRequest](#schemapusherauthrequest)|true|none|

> Example responses

> 200 Response

```json
{
  "channel_data": "string",
  "auth": "string"
}
```

<h3 id="get-authorized-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Pusher Auth Response|[PusherAuthResponse](#schemapusherauthresponse)|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad request|[BadRequest](#schemabadrequest)|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Unautorized|[UnautorizedException](#schemaunautorizedexception)|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Not found|[NotFound](#schemanotfound)|
|503|[Service Unavailable](https://tools.ietf.org/html/rfc7231#section-6.6.4)|Service unavailable|[ServiceUnavailable](#schemaserviceunavailable)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
api_key
</aside>

# Schemas

<h2 id="tocSunautorizedexception">UnautorizedException</h2>

<a id="schemaunautorizedexception"></a>

```json
{
  "status": 0,
  "message": "string"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|status|number(double)|true|none|none|
|message|string|true|none|none|

<h2 id="tocSbadrequest">BadRequest</h2>

<a id="schemabadrequest"></a>

```json
{
  "status": 0,
  "message": "string"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|status|number(double)|true|none|none|
|message|string|true|none|none|

<h2 id="tocSnotfound">NotFound</h2>

<a id="schemanotfound"></a>

```json
{
  "status": 0,
  "message": "string"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|status|number(double)|true|none|none|
|message|string|true|none|none|

<h2 id="tocSserviceunavailable">ServiceUnavailable</h2>

<a id="schemaserviceunavailable"></a>

```json
{
  "status": 0,
  "message": "string"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|status|number(double)|true|none|none|
|message|string|true|none|none|

<h2 id="tocSentityuuid">EntityUUID</h2>

<a id="schemaentityuuid"></a>

```json
{
  "entityUUID": "string"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|entityUUID|string|true|none|none|

<h2 id="tocSorderuuid">OrderUUID</h2>

<a id="schemaorderuuid"></a>

```json
{
  "orderUUID": "string"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|orderUUID|string|true|none|none|

<h2 id="tocSorderstatus">OrderStatus</h2>

<a id="schemaorderstatus"></a>

```json
{
  "transitionAlias": "string",
  "orderStatus": "string"
}

```

*The Root Schema*

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|transitionAlias|string|true|none|none|
|orderStatus|string|true|none|none|

<h2 id="tocSgeneratereport">GenerateReport</h2>

<a id="schemageneratereport"></a>

```json
{
  "type": "string"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|type|string|true|none|none|

<h2 id="tocSorderpayment">OrderPayment</h2>

<a id="schemaorderpayment"></a>

```json
{
  "provider": "string",
  "currency": "string",
  "status": "string",
  "meta": "string"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|provider|string|true|none|none|
|currency|string|true|none|none|
|status|string|true|none|none|
|meta|string|false|none|none|

<h2 id="tocSpaymentstatus">PaymentStatus</h2>

<a id="schemapaymentstatus"></a>

```json
{
  "provider": "string",
  "currency": "string",
  "status": "string",
  "till": "string",
  "meta": "string"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|provider|string|true|none|none|
|currency|string|true|none|none|
|status|string|true|none|none|
|till|string|false|none|none|
|meta|string|false|none|none|

<h2 id="tocSordertakeawayflag">OrderTakeawayFlag</h2>

<a id="schemaordertakeawayflag"></a>

```json
{
  "status": true
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|status|boolean|true|none|none|

<h2 id="tocSordersendemail">OrderSendEmail</h2>

<a id="schemaordersendemail"></a>

```json
{
  "orderUUID": "string",
  "email": "string",
  "optIn": true
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|orderUUID|string|true|none|none|
|email|string|false|none|none|
|optIn|boolean|false|none|none|

<h2 id="tocSordershistorybody">OrdersHistoryBody</h2>

<a id="schemaordershistorybody"></a>

```json
{
  "meta": {
    "extStoreUUID": "string",
    "search": "string",
    "startDate": "string",
    "endDate": "string",
    "lastEvaluatedKey": "string"
  },
  "payload": [
    {
      "source": "string",
      "uuid": "string",
      "user": {
        "name": "string",
        "email": "string",
        "extUserUUID": "string"
      },
      "serialNumber": "string",
      "status": "string",
      "payment": {
        "totalAmount": 0,
        "discount": 0,
        "price": 0
      },
      "createdAt": "string",
      "updatedAt": "string",
      "orderNumber": "string"
    }
  ]
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|meta|object|true|none|none|
|» extStoreUUID|string|true|none|none|
|» search|string|false|none|none|
|» startDate|string|false|none|none|
|» endDate|string|false|none|none|
|» lastEvaluatedKey|string|false|none|none|
|payload|[object]|true|none|none|
|» source|string|true|none|none|
|» uuid|string|true|none|none|
|» user|object|true|none|none|
|»» name|string|true|none|none|
|»» email|string|false|none|none|
|»» extUserUUID|string|true|none|none|
|» serialNumber|string|true|none|none|
|» status|string|true|none|none|
|» payment|object|true|none|none|
|»» totalAmount|number|true|none|none|
|»» discount|number|false|none|none|
|»» price|number|true|none|none|
|» createdAt|string|true|none|none|
|» updatedAt|string|true|none|none|
|» orderNumber|string|true|none|none|

<h2 id="tocSuserordershistorybody">UserOrdersHistoryBody</h2>

<a id="schemauserordershistorybody"></a>

```json
{
  "meta": {
    "search": "string",
    "startDate": "string",
    "endDate": "string",
    "lastEvaluatedKey": "string"
  },
  "payload": [
    {
      "payment": {
        "totalAmount": 0
      },
      "source": "string",
      "uuid": "string",
      "storeUUID": "string",
      "serialNumber": "string",
      "status": "string",
      "collectionDate": "string",
      "createdAt": "string",
      "updatedAt": "string",
      "bundles": [
        {
          "itemTypes": [
            {
              "name": "string",
              "ticketGroup": "string",
              "minRestriction": 0,
              "uuid": "string",
              "items": [
                {
                  "name": "string",
                  "itemUUID": "string",
                  "uuid": "string",
                  "price": 0,
                  "customizations": [
                    {}
                  ]
                }
              ],
              "maxRestriction": 0
            }
          ],
          "straightToPickup": true,
          "price": 0,
          "name": "string",
          "description": "string",
          "isGrouped": true,
          "isPrintable": true,
          "type": "string",
          "uuid": "string"
        }
      ]
    }
  ]
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|meta|object|true|none|none|
|» search|string|false|none|none|
|» startDate|string|true|none|none|
|» endDate|string|true|none|none|
|» lastEvaluatedKey|string|false|none|none|
|payload|[object]|true|none|none|
|» payment|object|true|none|none|
|»» totalAmount|number|true|none|none|
|» source|string|true|none|none|
|» uuid|string|true|none|none|
|» storeUUID|string|true|none|none|
|» serialNumber|string|true|none|none|
|» status|string|true|none|none|
|» collectionDate|string|false|none|none|
|» createdAt|string|true|none|none|
|» updatedAt|string|true|none|none|
|» bundles|[object]|true|none|none|
|»» itemTypes|[object]|true|none|none|
|»»» name|string|true|none|none|
|»»» ticketGroup|string|true|none|none|
|»»» minRestriction|integer|true|none|none|
|»»» uuid|string|true|none|none|
|»»» items|[object]|true|none|none|
|»»»» name|string|true|none|none|
|»»»» itemUUID|string|true|none|none|
|»»»» uuid|string|true|none|none|
|»»»» price|integer|true|none|none|
|»»»» customizations|[object]|true|none|none|
|»»»»» current|integer|false|none|none|
|»»»»» text|string|true|none|none|
|»»»»» type|string|true|none|none|
|»»»»» uuid|string|true|none|none|
|»»»»» variations|[object]|false|none|none|
|»»»»»» unit|object|true|none|none|
|»»»»»» price|number|true|none|none|
|»»»»»» step|integer|true|none|none|
|»»»»»» type|string|true|none|none|
|»»»»»» uuid|string|true|none|none|
|»»»»»» value|string|true|none|none|
|»»»»»» printText|string|true|none|none|
|»»»»» meta|object|false|none|none|
|»»»»»» description|string|false|none|none|
|»»»»»» text|string|true|none|none|
|»»»»» maxRestriction|integer|true|none|none|
|»»»» straightToPickup|boolean|true|none|none|
|»»»» price|number|true|none|none|
|»»»» name|string|true|none|none|
|»»»» description|string|false|none|none|
|»»»» isGrouped|boolean|true|none|none|
|»»»» isPrintable|boolean|true|none|none|
|»»»» type|string|true|none|none|
|»»»» uuid|string|true|none|none|

<h2 id="tocSorder">Order</h2>

<a id="schemaorder"></a>

```json
{
  "required": [
    "payload"
  ],
  "type": "object",
  "properties": {
    "payload": {
      "required": [
        "uuid",
        "payment",
        "user",
        "bundles",
        "status"
      ],
      "type": "object",
      "properties": {
        "uuid": {
          "type": "string"
        },
        "status": {
          "type": "string"
        },
        "payment": {
          "required": [
            "price",
            "totalAmount"
          ],
          "type": "object",
          "properties": {
            "price": {
              "type": "number"
            },
            "vatAmount": {
              "type": "number"
            },
            "discount": {
              "type": "number"
            },
            "totalAmount": {
              "type": "number"
            },
            "till": {
              "type": "string"
            }
          }
        },
        "takeaway": {
          "type": "boolean"
        },
        "isAsap": {
          "type": "boolean"
        },
        "orderType": {
          "type": "number"
        },
        "sortOrder": {
          "type": "number"
        },
        "timeSlot": {
          "properties": {
            "uuid": {
              "type": "string"
            },
            "slot": {
              "type": "string"
            }
          },
          "required": [
            "uuid",
            "slot"
          ],
          "type": "object"
        },
        "table": {
          "type": "string"
        },
        "note": {
          "type": "string"
        },
        "user": {
          "required": [
            "name",
            "email",
            "extUserUUID"
          ],
          "type": "object",
          "properties": {
            "name": {
              "type": "string"
            },
            "email": {
              "type": "string"
            },
            "extUserUUID": {
              "type": "string"
            }
          }
        },
        "bundles": {
          "type": "array",
          "items": {
            "required": [
              "uuid",
              "vatAmount",
              "taxExempt",
              "vatRateEatIn",
              "vatRateTakeaway",
              "menuUUID",
              "name",
              "price",
              "finalPrice",
              "hasModifiers",
              "type",
              "straightToPickup",
              "isGrouped",
              "itemTypes"
            ],
            "type": "object",
            "properties": {
              "uuid": {
                "type": "string"
              },
              "vatAmount": {
                "type": "number"
              },
              "taxExempt": {
                "type": "number"
              },
              "vatRateEatIn": {
                "type": "number"
              },
              "vatRateTakeaway": {
                "type": "number"
              },
              "basketUUID": {
                "type": "string"
              },
              "menuUUID": {
                "type": "string"
              },
              "category": {
                "required": [
                  "uuid",
                  "name"
                ],
                "type": "object",
                "properties": {
                  "uuid": {
                    "type": "string"
                  },
                  "name": {
                    "type": "string"
                  }
                }
              },
              "name": {
                "type": "string"
              },
              "price": {
                "type": "number"
              },
              "finalPrice": {
                "type": "number"
              },
              "hasModifiers": {
                "type": "boolean"
              },
              "type": {
                "type": "string"
              },
              "straightToPickup": {
                "type": "boolean"
              },
              "isGrouped": {
                "type": "boolean"
              },
              "itemTypes": {
                "type": "array",
                "items": {
                  "required": [
                    "uuid",
                    "name",
                    "ticketGroup",
                    "maxRestriction",
                    "minRestriction",
                    "items"
                  ],
                  "type": "object",
                  "properties": {
                    "uuid": {},
                    "name": {},
                    "kitchenZone": {},
                    "ticketGroup": {},
                    "maxRestriction": {},
                    "minRestriction": {},
                    "items": {}
                  }
                }
              }
            }
          }
        }
      }
    }
  }
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|payload|object|true|none|none|
|» uuid|string|true|none|none|
|» status|string|true|none|none|
|» payment|object|true|none|none|
|»» price|number|true|none|none|
|»» vatAmount|number|false|none|none|
|»» discount|number|false|none|none|
|»» totalAmount|number|true|none|none|
|»» till|string|false|none|none|
|» takeaway|boolean|false|none|none|
|» isAsap|boolean|false|none|none|
|» orderType|number|false|none|none|
|» sortOrder|number|false|none|none|
|» timeSlot|object|false|none|none|
|»» uuid|string|true|none|none|
|»» slot|string|true|none|none|
|» table|string|false|none|none|
|» note|string|false|none|none|
|» user|object|true|none|none|
|»» name|string|true|none|none|
|»» email|string|true|none|none|
|»» extUserUUID|string|true|none|none|
|» bundles|[object]|true|none|none|
|»» uuid|string|true|none|none|
|»» vatAmount|number|true|none|none|
|»» taxExempt|number|true|none|none|
|»» vatRateEatIn|number|true|none|none|
|»» vatRateTakeaway|number|true|none|none|
|»» basketUUID|string|false|none|none|
|»» menuUUID|string|true|none|none|
|»» category|object|false|none|none|
|»»» uuid|string|true|none|none|
|»»» name|string|true|none|none|
|»» name|string|true|none|none|
|»» price|number|true|none|none|
|»» finalPrice|number|true|none|none|
|»» hasModifiers|boolean|true|none|none|
|»» type|string|true|none|none|
|»» straightToPickup|boolean|true|none|none|
|»» isGrouped|boolean|true|none|none|
|»» itemTypes|[object]|true|none|none|
|»»» uuid|string|true|none|none|
|»»» name|string|true|none|none|
|»»» kitchenZone|object|false|none|none|
|»»»» uuid|string|true|none|none|
|»»»» name|string|true|none|none|
|»»»» slug|string|true|none|none|
|»»»» sortOrderOnPrint|number|true|none|none|
|»»»» capacity|number|true|none|none|
|»»» ticketGroup|string|true|none|none|
|»»» maxRestriction|integer|true|none|none|
|»»» minRestriction|integer|true|none|none|
|»»» items|[object]|true|none|none|
|»»»» customizations|[object]|true|none|none|
|»»»»» type|string|true|none|none|
|»»»»» uuid|string|true|none|none|
|»»»»» text|string|true|none|none|
|»»»»» variations|[object]|true|none|none|
|»»»»»» uuid|string|true|none|none|
|»»»»»» unit|object|true|none|none|
|»»»»»»» slug|string|true|none|none|
|»»»»»»» name|string|true|none|none|
|»»»»»»» value|number|true|none|none|
|»»»»»» price|number|true|none|none|
|»»»»»» step|integer|true|none|none|
|»»»»»» type|string|true|none|none|
|»»»»»» value|string|true|none|none|

*allOf*

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|»»»»»»» *anonymous*|string|false|none|none|

*and*

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|»»»»»»» *anonymous*|number|false|none|none|

*and*

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|»»»»»»» *anonymous*|boolean|false|none|none|

*continued*

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|»»»»»» printText|string|false|none|none|
|»»»»» current|integer|false|none|none|
|»»»»» meta|object|true|none|none|
|»»»»»» text|string|true|none|none|
|»»»»»» default_value|string|true|none|none|
|»»»»» price|number|true|none|none|
|»»»»» finalPrice|number|true|none|none|
|»»»»» vatAmount|number|true|none|none|
|»»»»» taxExempt|number|true|none|none|
|»»»»» vatRateEatIn|number|true|none|none|
|»»»»» vatRateTakeaway|number|true|none|none|
|»»»»» name|string|true|none|none|
|»»»»» straightToPickup|boolean|true|none|none|
|»»»»» itemUUID|string|true|none|none|
|»»»»» uuid|string|true|none|none|

<h2 id="tocSordercreation">OrderCreation</h2>

<a id="schemaordercreation"></a>

```json
{
  "required": [
    "payment",
    "user",
    "bundles"
  ],
  "type": "object",
  "properties": {
    "payment": {
      "required": [
        "price",
        "totalAmount"
      ],
      "type": "object",
      "properties": {
        "price": {
          "type": "number"
        },
        "vatAmount": {
          "type": "number"
        },
        "discount": {
          "type": "number"
        },
        "subtotalAmount": {
          "type": "number"
        },
        "totalAmount": {
          "type": "number"
        }
      }
    },
    "takeaway": {
      "type": "boolean"
    },
    "isAsap": {
      "type": "boolean"
    },
    "timeSlot": {
      "properties": {
        "uuid": {
          "type": "string"
        },
        "slot": {
          "type": "string"
        }
      },
      "required": [
        "uuid",
        "slot"
      ],
      "type": "object"
    },
    "table": {
      "type": "string"
    },
    "note": {
      "type": "string"
    },
    "user": {
      "required": [
        "name",
        "email",
        "extUserUUID"
      ],
      "type": "object",
      "properties": {
        "name": {
          "type": "string"
        },
        "email": {
          "type": "string"
        },
        "extUserUUID": {
          "type": "string"
        }
      }
    },
    "bundles": {
      "type": "array",
      "items": {
        "required": [
          "uuid",
          "basketUUID",
          "vatAmount",
          "taxExempt",
          "vatRateEatIn",
          "vatRateTakeaway",
          "menuUUID",
          "category",
          "name",
          "price",
          "finalPrice",
          "subtotalAmount",
          "hasModifiers",
          "type",
          "straightToPickup",
          "isGrouped",
          "itemTypes"
        ],
        "type": "object",
        "properties": {
          "uuid": {
            "type": "string"
          },
          "vatAmount": {
            "type": "number"
          },
          "taxExempt": {
            "type": "number"
          },
          "vatRateEatIn": {
            "type": "number"
          },
          "vatRateTakeaway": {
            "type": "number"
          },
          "promotion": {
            "required": [
              "uuid",
              "name",
              "value",
              "type"
            ],
            "type": "object",
            "properties": {
              "uuid": {
                "type": "string"
              },
              "name": {
                "type": "string"
              },
              "value": {
                "type": "number"
              },
              "type": {
                "type": "string"
              }
            }
          },
          "basketUUID": {
            "type": "string"
          },
          "menuUUID": {
            "type": "string"
          },
          "category": {
            "required": [
              "uuid",
              "name"
            ],
            "type": "object",
            "properties": {
              "uuid": {
                "type": "string"
              },
              "name": {
                "type": "string"
              }
            }
          },
          "name": {
            "type": "string"
          },
          "price": {
            "type": "number"
          },
          "priceEatIn": {
            "type": "number"
          },
          "finalPrice": {
            "type": "number"
          },
          "discount": {
            "type": "number"
          },
          "subtotalAmount": {
            "type": "number"
          },
          "totalAmount": {
            "type": "number"
          },
          "hasModifiers": {
            "type": "boolean"
          },
          "hasEatInPrice": {
            "type": "boolean"
          },
          "type": {
            "type": "string"
          },
          "straightToPickup": {
            "type": "boolean"
          },
          "isGrouped": {
            "type": "boolean"
          },
          "itemTypes": {
            "type": "array",
            "items": {
              "required": [
                "uuid",
                "name",
                "ticketGroup",
                "maxRestriction",
                "minRestriction",
                "items"
              ],
              "type": "object",
              "properties": {
                "uuid": {
                  "type": "string"
                },
                "name": {
                  "type": "string"
                },
                "kitchenZone": {
                  "required": [
                    "uuid",
                    "name",
                    "slug",
                    "sortOrderOnPrint",
                    "capacity"
                  ],
                  "properties": {
                    "uuid": {},
                    "name": {},
                    "slug": {},
                    "sortOrderOnPrint": {},
                    "capacity": {}
                  },
                  "type": "object"
                },
                "ticketGroup": {
                  "type": "string"
                },
                "maxRestriction": {
                  "type": "integer"
                },
                "minRestriction": {
                  "type": "integer"
                },
                "items": {
                  "type": "array",
                  "items": {
                    "required": [],
                    "type": "object",
                    "properties": {}
                  }
                }
              }
            }
          }
        }
      }
    }
  }
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|payment|object|true|none|none|
|» price|number|true|none|none|
|» vatAmount|number|false|none|none|
|» discount|number|false|none|none|
|» subtotalAmount|number|false|none|none|
|» totalAmount|number|true|none|none|
|takeaway|boolean|false|none|none|
|isAsap|boolean|false|none|none|
|timeSlot|object|false|none|none|
|» uuid|string|true|none|none|
|» slot|string|true|none|none|
|table|string|false|none|none|
|note|string|false|none|none|
|user|object|true|none|none|
|» name|string|true|none|none|
|» email|string|true|none|none|
|» extUserUUID|string|true|none|none|
|bundles|[object]|true|none|none|
|» uuid|string|true|none|none|
|» vatAmount|number|true|none|none|
|» taxExempt|number|true|none|none|
|» vatRateEatIn|number|true|none|none|
|» vatRateTakeaway|number|true|none|none|
|» promotion|object|false|none|none|
|»» uuid|string|true|none|none|
|»» name|string|true|none|none|
|»» value|number|true|none|none|
|»» type|string|true|none|none|
|» basketUUID|string|true|none|none|
|» menuUUID|string|true|none|none|
|» category|object|true|none|none|
|»» uuid|string|true|none|none|
|»» name|string|true|none|none|
|» name|string|true|none|none|
|» price|number|true|none|none|
|» priceEatIn|number|false|none|none|
|» finalPrice|number|true|none|none|
|» discount|number|false|none|none|
|» subtotalAmount|number|true|none|none|
|» totalAmount|number|false|none|none|
|» hasModifiers|boolean|true|none|none|
|» hasEatInPrice|boolean|false|none|none|
|» type|string|true|none|none|
|» straightToPickup|boolean|true|none|none|
|» isGrouped|boolean|true|none|none|
|» itemTypes|[object]|true|none|none|
|»» uuid|string|true|none|none|
|»» name|string|true|none|none|
|»» kitchenZone|object|false|none|none|
|»»» uuid|string|true|none|none|
|»»» name|string|true|none|none|
|»»» slug|string|true|none|none|
|»»» sortOrderOnPrint|string|true|none|none|
|»»» capacity|string|true|none|none|
|»» ticketGroup|string|true|none|none|
|»» maxRestriction|integer|true|none|none|
|»» minRestriction|integer|true|none|none|
|»» items|[object]|true|none|none|
|»»» customizations|[object]|true|none|none|
|»»»» type|string|true|none|none|
|»»»» uuid|string|true|none|none|
|»»»» text|string|true|none|none|
|»»»» variations|[object]|true|none|none|
|»»»»» uuid|string|true|none|none|
|»»»»» unit|object|true|none|none|
|»»»»»» slug|string|true|none|none|
|»»»»»» name|string|true|none|none|
|»»»»»» value|string|true|none|none|
|»»»»» price|number|true|none|none|
|»»»»» step|integer|true|none|none|
|»»»»» type|string|true|none|none|
|»»»»» value|string|true|none|none|

*allOf*

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|»»»»»» *anonymous*|string|false|none|none|

*and*

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|»»»»»» *anonymous*|number|false|none|none|

*and*

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|»»»»»» *anonymous*|boolean|false|none|none|

*continued*

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|»»»»» printText|string|false|none|none|
|»»»» current|[](#schema)|true|none|none|
|»»»» meta|object|true|none|none|
|»»»»» text|string|true|none|none|
|»»»»» default_value|string|true|none|none|
|»»»» price|number|true|none|none|
|»»»» finalPrice|number|true|none|none|
|»»»» priceEatIn|number|false|none|none|
|»»»» hasEatInPrice|boolean|false|none|none|
|»»»» subtotalAmount|number|true|none|none|
|»»»» totalAmount|number|false|none|none|
|»»»» vatAmount|number|true|none|none|
|»»»» taxExempt|number|true|none|none|
|»»»» vatRateEatIn|number|true|none|none|
|»»»» vatRateTakeaway|number|true|none|none|
|»»»» name|string|true|none|none|
|»»»» straightToPickup|boolean|true|none|none|
|»»»» itemUUID|string|true|none|none|
|»»»» uuid|string|true|none|none|

<h2 id="tocSorderreport">OrderReport</h2>

<a id="schemaorderreport"></a>

```json
{
  "payload": {
    "uuid": "string",
    "createdAt": "string",
    "fromDate": "string",
    "refunds": 0,
    "discount": 0,
    "grossSales": 0,
    "totalTender": 0,
    "transactionsCount": 0,
    "vatableSales": 0,
    "nonVatableSales": 0,
    "paymentProviders": {
      "cash": 0,
      "stripe": 0,
      "izettle": 0
    },
    "tills": [
      {
        "refunds": 0,
        "discount": 0,
        "grossSales": 0,
        "totalTender": 0,
        "transactionsCount": 0,
        "vatableSales": 0,
        "nonVatableSales": 0,
        "paymentProviders": {
          "cash": 0,
          "stripe": 0,
          "izettle": 0
        }
      }
    ],
    "type": "string"
  }
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|payload|object|true|none|none|
|» uuid|string|true|none|none|
|» createdAt|string|true|none|none|
|» fromDate|string|true|none|none|
|» refunds|number|true|none|none|
|» discount|number|true|none|none|
|» grossSales|number|true|none|none|
|» totalTender|number|true|none|none|
|» transactionsCount|number|true|none|none|
|» vatableSales|number|true|none|none|
|» nonVatableSales|number|true|none|none|
|» paymentProviders|object|true|none|none|
|»» cash|number|true|none|none|
|»» stripe|number|true|none|none|
|»» izettle|number|true|none|none|
|» tills|[object]|true|none|none|
|»» refunds|number|true|none|none|
|»» discount|number|true|none|none|
|»» grossSales|number|true|none|none|
|»» totalTender|number|true|none|none|
|»» transactionsCount|number|true|none|none|
|»» vatableSales|number|true|none|none|
|»» nonVatableSales|number|true|none|none|
|»» paymentProviders|object|true|none|none|
|»»» cash|number|true|none|none|
|»»» stripe|number|true|none|none|
|»»» izettle|number|true|none|none|
|»» type|string|true|none|none|

<h2 id="tocSorderreports">OrderReports</h2>

<a id="schemaorderreports"></a>

```json
{
  "payload": {
    "items": [
      {
        "uuid": "string",
        "createdAt": "string",
        "fromDate": "string",
        "type": "string"
      }
    ],
    "meta": {
      "lastEvaluatedKey": "string",
      "startDate": "string",
      "endDate": "string"
    }
  }
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|payload|object|true|none|none|
|» items|[object]|true|none|none|
|»» uuid|string|true|none|none|
|»» createdAt|string|true|none|none|
|»» fromDate|string|true|none|none|
|»» type|string|true|none|none|
|» meta|object|true|none|none|
|»» lastEvaluatedKey|string|false|none|none|
|»» startDate|string|true|none|none|
|»» endDate|string|true|none|none|

<h2 id="tocSorderbundlespromo">OrderBundlesPromo</h2>

<a id="schemaorderbundlespromo"></a>

```json
{
  "bundles": [
    {
      "uuid": "string",
      "finalPrice": 0,
      "subtotalAmount": 0,
      "promotion": {
        "uuid": "string",
        "name": "string",
        "value": 0,
        "type": "string"
      },
      "itemTypes": [
        {
          "items": [
            {
              "itemUUID": "string",
              "finalPrice": 0,
              "subtotalAmount": 0
            }
          ]
        }
      ]
    }
  ]
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|bundles|[object]|true|none|none|
|» uuid|string|true|none|none|
|» finalPrice|number|true|none|none|
|» subtotalAmount|number|true|none|none|
|» promotion|object|false|none|none|
|»» uuid|string|true|none|none|
|»» name|string|true|none|none|
|»» value|number|true|none|none|
|»» type|string|true|none|none|
|» itemTypes|[object]|true|none|none|
|»» items|[object]|true|none|none|
|»»» itemUUID|string|true|none|none|
|»»» finalPrice|number|true|none|none|
|»»» subtotalAmount|number|true|none|none|

<h2 id="tocSorderremovebundle">OrderRemoveBundle</h2>

<a id="schemaorderremovebundle"></a>

```json
{
  "basketUUIDs": [
    "string"
  ],
  "payment": {
    "price": 0,
    "totalAmount": 0,
    "subtotalAmount": 0
  }
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|basketUUIDs|[string]|true|none|none|
|payment|object|true|none|none|
|» price|number|true|none|none|
|» totalAmount|number|true|none|none|
|» subtotalAmount|number|true|none|none|

<h2 id="tocSpusherauthrequest">PusherAuthRequest</h2>

<a id="schemapusherauthrequest"></a>

```json
{
  "socket_id": "string",
  "channel_name": "string"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|socket_id|string|true|none|none|
|channel_name|string|true|none|none|

<h2 id="tocSpusherauthresponse">PusherAuthResponse</h2>

<a id="schemapusherauthresponse"></a>

```json
{
  "channel_data": "string",
  "auth": "string"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|channel_data|string|true|none|none|
|auth|string|true|none|none|

