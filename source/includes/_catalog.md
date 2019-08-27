---
title: Catalog Service
language_tabs:
  - shell: curl
  - javascript: JavaScript
  - javascript--nodejs: Node.JS
  - python: Python
  - ruby: Ruby
toc_footers: []
includes: []
search: true
highlight_theme: darkula
headingLevel: 2

---

<h1 id="catalog-service">Catalog Service</h1>

> Scroll down for code samples, example requests and responses. Select a language for code samples from the tabs above or the mobile navigation menu.

The Catalog Service API Documentation

<h2 id="catalog-service-default">Default</h2>

### GET_healthcheck

<a id="opIdGET_healthcheck"></a>

> Code samples

```shell
# You can also use wget
curl -X GET /healthcheck

```

```javascript

$.ajax({
  url: '/healthcheck',
  method: 'get',

  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

```javascript--nodejs
const fetch = require('node-fetch');

fetch('/healthcheck',
{
  method: 'GET'

})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```python
import requests

r = requests.get('/healthcheck', params={

)

print r.json()

```

```ruby
require 'rest-client'
require 'json'

result = RestClient.get '/healthcheck',
  params: {
  }

p JSON.parse(result)

```

`GET /healthcheck`

<h4 id="get_healthcheck-responses">Responses</h4>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|none|None|

<aside class="success">
This operation does not require authentication
</aside>

<h2 id="catalog-service-bundles">bundles</h2>

### Validate Bundles

<a id="opIdValidate Bundles"></a>

> Code samples

```shell
# You can also use wget
curl -X POST /bundles/validate \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json' \
  -H 'store: string' \
  -H 'tenant: string'

```

```javascript
var headers = {
  'Content-Type':'application/json',
  'Accept':'application/json',
  'store':'string',
  'tenant':'string'

};

$.ajax({
  url: '/bundles/validate',
  method: 'post',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

```javascript--nodejs
const fetch = require('node-fetch');
const inputBody = '{
  "bundles": [
    {
      "itemTypes": [
        {
          "uuid": "string",
          "name": "string",
          "slug": "string",
          "isDefault": true,
          "ticketGroup": "string",
          "maxRestriction": 0,
          "minRestriction": 0,
          "items": [
            {
              "taxExempt": 0,
              "vatRateEatIn": 0,
              "vatRateTakeaway": 0,
              "price": 0,
              "priceEatIn": 0,
              "finalPrice": 0,
              "name": "string",
              "slug": "string",
              "straightToPickup": true,
              "itemUUID": "string",
              "uuid": "string",
              "customizations": [
                {
                  "type": "string",
                  "uuid": "string",
                  "text": "string",
                  "variations": [
                    {}
                  ],
                  "current": "string",
                  "meta": {
                    "text": "string",
                    "defaultValue": "string"
                  }
                }
              ]
            }
          ]
        }
      ],
      "taxExempt": 0,
      "vatRateEatIn": 0,
      "vatRateTakeaway": 0,
      "price": 0,
      "priceEatIn": 0,
      "finalPrice": 0,
      "name": "string",
      "basketUUID": "string",
      "hasItemsModifiers": true,
      "type": "string",
      "uuid": "string",
      "straightToPickup": true,
      "category": {
        "uuid": "string",
        "slug": "string",
        "name": "string"
      },
      "grouped": true
    }
  ],
  "takeaway": true
}';
const headers = {
  'Content-Type':'application/json',
  'Accept':'application/json',
  'store':'string',
  'tenant':'string'

};

fetch('/bundles/validate',
{
  method: 'POST',
  body: inputBody,
  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json',
  'store': 'string',
  'tenant': 'string'
}

r = requests.post('/bundles/validate', params={

}, headers = headers)

print r.json()

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Content-Type' => 'application/json',
  'Accept' => 'application/json',
  'store' => 'string',
  'tenant' => 'string'
}

result = RestClient.post '/bundles/validate',
  params: {
  }, headers: headers

p JSON.parse(result)

```

`POST /bundles/validate`

Deep integrations only! Validates a list of bundles. Checks if bundles are well formed (valid items, options, modifiers). Will also check pricing calculations are correct.

> Body parameter

```json
{
  "bundles": [
    {
      "itemTypes": [
        {
          "uuid": "string",
          "name": "string",
          "slug": "string",
          "isDefault": true,
          "ticketGroup": "string",
          "maxRestriction": 0,
          "minRestriction": 0,
          "items": [
            {
              "taxExempt": 0,
              "vatRateEatIn": 0,
              "vatRateTakeaway": 0,
              "price": 0,
              "priceEatIn": 0,
              "finalPrice": 0,
              "name": "string",
              "slug": "string",
              "straightToPickup": true,
              "itemUUID": "string",
              "uuid": "string",
              "customizations": [
                {
                  "type": "string",
                  "uuid": "string",
                  "text": "string",
                  "variations": [
                    {}
                  ],
                  "current": "string",
                  "meta": {
                    "text": "string",
                    "defaultValue": "string"
                  }
                }
              ]
            }
          ]
        }
      ],
      "taxExempt": 0,
      "vatRateEatIn": 0,
      "vatRateTakeaway": 0,
      "price": 0,
      "priceEatIn": 0,
      "finalPrice": 0,
      "name": "string",
      "basketUUID": "string",
      "hasItemsModifiers": true,
      "type": "string",
      "uuid": "string",
      "straightToPickup": true,
      "category": {
        "uuid": "string",
        "slug": "string",
        "name": "string"
      },
      "grouped": true
    }
  ],
  "takeaway": true
}
```

<h4 id="validate-bundles-parameters">Parameters</h4>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|store|header|string|true|Validate bundles by External Store UUID (876b34ad-45654-4ds7-cdd8-bfc47686d999)|
|tenant|header|string|true|Validate VAT by External Tenant UUID (832b34ad-2608-4cc7-bee8-bfc47686d801)|
|body|body|[BundlesModel](#schemabundlesmodel)|true|none|

> Example responses

> 200 Response

```json
{
  "status": true,
  "meta": null
}
```

> 400 Response

```json
{
  "statusCode": 0,
  "message": "string"
}
```

<h4 id="validate-bundles-responses">Responses</h4>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|none|[ValidationModel](#schemavalidationmodel)|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|none|[BadRequestError](#schemabadrequesterror)|
|403|[Forbidden](https://tools.ietf.org/html/rfc7231#section-6.5.3)|none|[ForbiddenError](#schemaforbiddenerror)|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|none|[InternalServerError](#schemainternalservererror)|

<aside class="success">
This operation does not require authentication
</aside>

### Get Bundle

<a id="opIdGet Bundle"></a>

> Code samples

```shell
# You can also use wget
curl -X GET /bundles/{bundleUUID} \
  -H 'Accept: application/json' \
  -H 'menu: string' \
  -H 'store: string' \
  -H 'tenant: string'

```

```javascript
var headers = {
  'Accept':'application/json',
  'menu':'string',
  'store':'string',
  'tenant':'string'

};

$.ajax({
  url: '/bundles/{bundleUUID}',
  method: 'get',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

```javascript--nodejs
const fetch = require('node-fetch');

const headers = {
  'Accept':'application/json',
  'menu':'string',
  'store':'string',
  'tenant':'string'

};

fetch('/bundles/{bundleUUID}',
{
  method: 'GET',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```python
import requests
headers = {
  'Accept': 'application/json',
  'menu': 'string',
  'store': 'string',
  'tenant': 'string'
}

r = requests.get('/bundles/{bundleUUID}', params={

}, headers = headers)

print r.json()

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json',
  'menu' => 'string',
  'store' => 'string',
  'tenant' => 'string'
}

result = RestClient.get '/bundles/{bundleUUID}',
  params: {
  }, headers: headers

p JSON.parse(result)

```

`GET /bundles/{bundleUUID}`

Get Bundle (items or meals) information by UUID. Bundle rules (item types), valid items and modifier, rule prices etc.

<h4 id="get-bundle-parameters">Parameters</h4>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|menu|header|string|true|Menu UUID, bind item stock price|
|store|header|string|true|External Store UUID (876b34ad-45654-4ds7-cdd8-bfc47686d999), bind stock|
|tenant|header|string|true|External Tenant UUID (832b34ad-2608-4cc7-bee8-bfc47686d801), bind item VAT|
|categoryUUID|query|string|false|Category UUID, bind Root Category to Bundle|
|bundleUUID|path|string|true|Bundle UUID|

> Example responses

> 200 Response

```json
{
  "payload": {
    "uuid": "sfcsdr533453445",
    "name": "Hot Chocolate",
    "description": null,
    "onlineDescription": "some online description",
    "category": {
      "name": "Main",
      "uuid": "asdased234234234"
    },
    "rootCategory": {
      "name": "Main",
      "uuid": "asdased234234234"
    },
    "hasModifiers": false,
    "isGrouped": false,
    "taxExempt": null,
    "vatRateEatIn": 12,
    "vatRateTakeaway": 9,
    "diets": [
      "sdcerf45f45f45",
      "sdcerf45f33f45"
    ],
    "allergens": [
      "sdcerf11f45f45",
      "sdcerf99f45f45"
    ],
    "items": [
      {
        "uuid": "0514be43-4c28-4aff-9e89-cdb4e7e4dab1",
        "sortOrder": 0,
        "name": "Hot Chocolate",
        "price": 6.95,
        "nutritionalMeta": {
          "calories": 136.5,
          "fats": 2.2,
          "fatSaturates": 0.7,
          "carbs": 0.1,
          "carbsSugar": 0,
          "fibre": 0.1,
          "protein": 29,
          "salt": 0.57,
          "tenAday": 0
        },
        "kitchenZone": {
          "uuid": "e43-4c28-4aff-9e89-cdb4",
          "name": "name 1",
          "slug": "some slug",
          "sortOrderOnPrint": 1,
          "capacity": 20
        },
        "description": "Est consequatur et consequatur vel dolorem reiciendis doloremque. Sint quas delectus illo architecto. Architecto quibusdam placeat.",
        "onlineDescription": "some online description",
        "itemType": {
          "uuid": "s0UrRl39krwrfexvz0tA33FQpjvHU4",
          "name": "Base Full English",
          "sortOrder": 0,
          "minRestriction": 1,
          "maxRestriction": 1
        },
        "customizations": [
          {
            "type": "radio",
            "uuid": "a112ad96-2a3d-4bee-8335-8e615a8fd1f5",
            "text": "size",
            "variations": [
              {
                "step": 0,
                "value": "12oz",
                "price": 2.3,
                "uuid": "4ba9dad1-ff24-421f-8546-443a71283d35",
                "type": "radio",
                "unit": null
              },
              {
                "step": 1,
                "value": "16oz",
                "price": 2.7,
                "uuid": "4483e0fa-7881-4cf0-b2ad-a5a727aba125",
                "type": "radio",
                "unit": null
              }
            ],
            "current": 0,
            "meta": {
              "text": "size",
              "defaultValue": "12oz"
            }
          },
          {
            "type": "radio",
            "uuid": "411308a3-6b38-11e8-8bcc-02f6c2788b90",
            "text": "milk type",
            "variations": [
              {
                "step": 0,
                "value": "Whole Milk",
                "price": 0,
                "uuid": "990bad22-9b76-4a41-b473-3cf90ff02128",
                "type": "radio",
                "unit": null
              },
              {
                "step": 1,
                "value": "Skimmed Milk",
                "price": 0,
                "uuid": "bfbd5f8b-eba5-4b6e-9a47-77d2614677ad",
                "type": "radio",
                "unit": null
              },
              {
                "step": 2,
                "value": "Soy Milk",
                "price": 0.5,
                "uuid": "c064445c-3b07-4a0a-afd8-ca2c8e73dbfd",
                "type": "radio",
                "unit": null
              },
              {
                "step": 3,
                "value": "Almond Milk",
                "price": 0.5,
                "uuid": "b48135e0-4294-45b4-8c2a-164affbc555d",
                "type": "radio",
                "unit": null
              },
              {
                "step": 4,
                "value": "Coconut Milk",
                "price": 1,
                "uuid": "ddcfcff6-6d72-49a7-a52c-8d7e4ae9097e",
                "type": "radio",
                "unit": null
              },
              {
                "step": 5,
                "value": "S Almond Milk",
                "price": 0.25,
                "uuid": "74063970-e3d1-4cdf-a1ba-16b8259ec7a3",
                "type": "radio",
                "unit": null
              },
              {
                "step": 6,
                "value": "S Coconut Milk",
                "price": 0.5,
                "uuid": "29dc1a1d-8658-4e7e-b549-e18435529c86",
                "type": "radio",
                "unit": null
              }
            ],
            "current": null,
            "meta": {
              "text": "milk type"
            }
          },
          {
            "type": "checkbox",
            "uuid": "74014e2d-6b49-11e8-8bcc-02f6c2788b90",
            "text": "Extra shot",
            "variations": [
              {
                "step": 0,
                "value": "Syrup Shot",
                "price": 0.8,
                "uuid": "11ed3d3c-d216-4d63-aea1-dd39c7866512",
                "type": "checkbox",
                "unit": null
              },
              {
                "step": 1,
                "value": "Expresso Shot",
                "price": 0.9,
                "uuid": "0e193d2e-43c5-45f2-a3f3-c7f3c5293dc5",
                "type": "checkbox",
                "unit": null
              }
            ],
            "current": [
              0
            ],
            "meta": {
              "text": "Extra shot"
            }
          }
        ]
      },
      {
        "uuid": "88d8140e-602a-4253-af9b-1394bbd45455",
        "sortOrder": 0,
        "name": "Avocado",
        "kitchenZone": null,
        "price": 5,
        "nutritionalMeta": null,
        "description": "Est consequatur et consequatur vel dolorem reiciendis doloremque. Sint quas delectus illo architecto. Architecto quibusdam placeat.",
        "onlineDescription": "some online description",
        "itemType": {
          "uuid": "uCqDma1SDrdepv0xN6nO",
          "name": "Extra Full english",
          "sortOrder": 1,
          "minRestriction": 1,
          "maxRestriction": 5
        },
        "customizations": [
          {
            "type": "radio",
            "uuid": "a112ad96-2a3d-4bee-8335-8e615a8fd1f5",
            "text": "size",
            "variations": [
              {
                "step": 0,
                "value": "12oz",
                "price": 2.3,
                "uuid": "4ba9dad1-ff24-421f-8546-443a71283d35",
                "type": "radio",
                "unit": null
              },
              {
                "step": 1,
                "value": "16oz",
                "price": 2.7,
                "uuid": "4483e0fa-7881-4cf0-b2ad-a5a727aba125",
                "type": "radio",
                "unit": null
              }
            ],
            "current": 0,
            "meta": {
              "text": "size",
              "defaultValue": "12oz"
            }
          },
          {
            "type": "radio",
            "uuid": "411308a3-6b38-11e8-8bcc-02f6c2788b90",
            "text": "milk type",
            "variations": [
              {
                "step": 0,
                "value": "Whole Milk",
                "price": 0,
                "uuid": "990bad22-9b76-4a41-b473-3cf90ff02128",
                "type": "radio",
                "unit": null
              },
              {
                "step": 1,
                "value": "Skimmed Milk",
                "price": 0,
                "uuid": "bfbd5f8b-eba5-4b6e-9a47-77d2614677ad",
                "type": "radio",
                "unit": null
              },
              {
                "step": 2,
                "value": "Soy Milk",
                "price": 0.5,
                "uuid": "c064445c-3b07-4a0a-afd8-ca2c8e73dbfd",
                "type": "radio",
                "unit": null
              },
              {
                "step": 3,
                "value": "Almond Milk",
                "price": 0.5,
                "uuid": "b48135e0-4294-45b4-8c2a-164affbc555d",
                "type": "radio",
                "unit": null
              },
              {
                "step": 4,
                "value": "Coconut Milk",
                "price": 1,
                "uuid": "ddcfcff6-6d72-49a7-a52c-8d7e4ae9097e",
                "type": "radio",
                "unit": null
              },
              {
                "step": 5,
                "value": "S Almond Milk",
                "price": 0.25,
                "uuid": "74063970-e3d1-4cdf-a1ba-16b8259ec7a3",
                "type": "radio",
                "unit": null
              },
              {
                "step": 6,
                "value": "S Coconut Milk",
                "price": 0.5,
                "uuid": "29dc1a1d-8658-4e7e-b549-e18435529c86",
                "type": "radio",
                "unit": null
              }
            ],
            "current": null,
            "meta": {
              "text": "milk type"
            }
          },
          {
            "type": "checkbox",
            "uuid": "74014e2d-6b49-11e8-8bcc-02f6c2788b90",
            "text": "Extra shot",
            "variations": [
              {
                "step": 0,
                "value": "Syrup Shot",
                "price": 0.8,
                "uuid": "11ed3d3c-d216-4d63-aea1-dd39c7866512",
                "type": "checkbox",
                "unit": null
              },
              {
                "step": 1,
                "value": "Expresso Shot",
                "price": 0.9,
                "uuid": "0e193d2e-43c5-45f2-a3f3-c7f3c5293dc5",
                "type": "checkbox",
                "unit": null
              }
            ],
            "current": [
              0
            ],
            "meta": {
              "text": "Extra shot"
            }
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
  "statusCode": 400,
  "message": "Please select store first!"
}
```

> 403 Response

```json
{
  "statusCode": 403,
  "message": "Forbidden resource"
}
```

> 500 Response

```json
{
  "statusCode": 500,
  "message": "Internal server error!"
}
```

<h4 id="get-bundle-responses">Responses</h4>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|none|[BundleModel](#schemabundlemodel)|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|none|[BadRequestError](#schemabadrequesterror)|
|403|[Forbidden](https://tools.ietf.org/html/rfc7231#section-6.5.3)|none|[ForbiddenError](#schemaforbiddenerror)|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|none|[InternalServerError](#schemainternalservererror)|

<aside class="success">
This operation does not require authentication
</aside>

### GET_bundles-bundleUUID-item-types

<a id="opIdGET_bundles-bundleUUID-item-types"></a>

> Code samples

```shell
# You can also use wget
curl -X GET /bundles/{bundleUUID}/item-types \
  -H 'Accept: application/json' \
  -H 'menu: string' \
  -H 'store: string' \
  -H 'tenant: string'

```

```javascript
var headers = {
  'Accept':'application/json',
  'menu':'string',
  'store':'string',
  'tenant':'string'

};

$.ajax({
  url: '/bundles/{bundleUUID}/item-types',
  method: 'get',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

```javascript--nodejs
const fetch = require('node-fetch');

const headers = {
  'Accept':'application/json',
  'menu':'string',
  'store':'string',
  'tenant':'string'

};

fetch('/bundles/{bundleUUID}/item-types',
{
  method: 'GET',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```python
import requests
headers = {
  'Accept': 'application/json',
  'menu': 'string',
  'store': 'string',
  'tenant': 'string'
}

r = requests.get('/bundles/{bundleUUID}/item-types', params={

}, headers = headers)

print r.json()

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json',
  'menu' => 'string',
  'store' => 'string',
  'tenant' => 'string'
}

result = RestClient.get '/bundles/{bundleUUID}/item-types',
  params: {
  }, headers: headers

p JSON.parse(result)

```

`GET /bundles/{bundleUUID}/item-types`

<h4 id="get_bundles-bundleuuid-item-types-parameters">Parameters</h4>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|menu|header|string|true|Menu UUID|
|store|header|string|true|External Store UUID (876b34ad-45654-4ds7-cdd8-bfc47686d999)|
|tenant|header|string|true|External Tenant UUID (832b34ad-2608-4cc7-bee8-bfc47686d801)|
|bundleUUID|path|string|true|Bundle UUID|

> Example responses

> 200 Response

```json
[
  {
    "payload": [
      {
        "uuid": "string",
        "name": "string",
        "sortOrder": 0,
        "minRestriction": 0,
        "maxRestriction": 0,
        "description": "string",
        "onlineDescription": "string",
        "ticketGroup": "string",
        "items": [
          {
            "uuid": "string",
            "taxExempt": 0,
            "vatRateEatIn": 0,
            "vatRateTakeaway": 0,
            "sortOrder": 0,
            "name": "string",
            "price": 0,
            "nutritionalMeta": {},
            "kitchenZone": {
              "uuid": "string",
              "name": "string",
              "slug": "string",
              "sortOrderOnPrint": 0,
              "capacity": 0
            },
            "itemType": {
              "uuid": "string",
              "name": "string",
              "sortOrder": 0,
              "minRestriction": 0,
              "maxRestriction": 0
            },
            "customizations": [
              {
                "type": "string",
                "uuid": "string",
                "text": "string",
                "variations": [
                  {
                    "step": 0,
                    "value": "string",
                    "price": 0,
                    "uuid": "string",
                    "type": "string"
                  }
                ],
                "current": "string"
              }
            ]
          }
        ]
      }
    ]
  }
]
```

<h4 id="get_bundles-bundleuuid-item-types-responses">Responses</h4>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|none|Inline|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|none|[BadRequestError](#schemabadrequesterror)|
|403|[Forbidden](https://tools.ietf.org/html/rfc7231#section-6.5.3)|none|[ForbiddenError](#schemaforbiddenerror)|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|none|[InternalServerError](#schemainternalservererror)|

<h4 id="get_bundles-bundleuuid-item-types-responseschema">Response Schema</h4>

Status Code **200**

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|*anonymous*|[[BundleItemTypesItems](#schemabundleitemtypesitems)]|false|none|none|
|» payload|[object]|true|none|none|
|»» uuid|string|true|none|none|
|»» name|string|true|none|none|
|»» sortOrder|integer|true|none|none|
|»» minRestriction|integer|false|none|none|
|»» maxRestriction|integer|false|none|none|
|»» description|string|false|none|none|
|»» onlineDescription|string|false|none|none|
|»» ticketGroup|string|false|none|none|
|»» items|[object]|true|none|none|
|»»» uuid|string|true|none|none|
|»»» taxExempt|number|true|none|none|
|»»» vatRateEatIn|number|true|none|none|
|»»» vatRateTakeaway|number|true|none|none|
|»»» sortOrder|integer|false|none|none|
|»»» name|string|true|none|none|
|»»» price|number|true|none|none|
|»»» nutritionalMeta|object|false|none|none|
|»»» kitchenZone|object|false|none|none|
|»»»» uuid|string|true|none|none|
|»»»» name|string|true|none|none|
|»»»» slug|string|true|none|none|
|»»»» sortOrderOnPrint|integer|true|none|none|
|»»»» capacity|integer|true|none|none|
|»»» itemType|object|true|none|none|
|»»»» uuid|string|true|none|none|
|»»»» name|string|true|none|none|
|»»»» sortOrder|integer|false|none|none|
|»»»» minRestriction|integer|false|none|none|
|»»»» maxRestriction|integer|false|none|none|
|»»» customizations|[object]|true|none|none|
|»»»» type|string|true|none|none|
|»»»» uuid|string|true|none|none|
|»»»» text|string|true|none|none|
|»»»» variations|[object]|true|none|none|
|»»»»» step|integer|true|none|none|
|»»»»» value|string|true|none|none|
|»»»»» price|number|true|none|none|
|»»»»» uuid|string|true|none|none|
|»»»»» type|string|true|none|none|
|»»»» current|string|false|none|none|

<aside class="success">
This operation does not require authentication
</aside>

<h2 id="catalog-service-diets">diets</h2>

### Get Diets

<a id="opIdGet Diets"></a>

> Code samples

```shell
# You can also use wget
curl -X GET /diets \
  -H 'Accept: application/json' \
  -H 'tenant: string'

```

```javascript
var headers = {
  'Accept':'application/json',
  'tenant':'string'

};

$.ajax({
  url: '/diets',
  method: 'get',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

```javascript--nodejs
const fetch = require('node-fetch');

const headers = {
  'Accept':'application/json',
  'tenant':'string'

};

fetch('/diets',
{
  method: 'GET',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```python
import requests
headers = {
  'Accept': 'application/json',
  'tenant': 'string'
}

r = requests.get('/diets', params={

}, headers = headers)

print r.json()

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json',
  'tenant' => 'string'
}

result = RestClient.get '/diets',
  params: {
  }, headers: headers

p JSON.parse(result)

```

`GET /diets`

Get a list of diets described in the system

<h4 id="get-diets-parameters">Parameters</h4>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|tenant|header|string|true|External Tenant UUID (832b34ad-2608-4cc7-bee8-bfc47686d801)|

> Example responses

> 200 Response

```json
{
  "payload": {
    "diets": [
      {
        "uuid": "string",
        "name": "string",
        "image": "string",
        "selectImage": "string",
        "description": "string"
      }
    ],
    "allergens": [
      {
        "uuid": "string",
        "image": "string",
        "selectImage": "string",
        "name": "string",
        "description": "string"
      }
    ]
  }
}
```

<h4 id="get-diets-responses">Responses</h4>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|none|[DietResponseModel](#schemadietresponsemodel)|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|none|[BadRequestError](#schemabadrequesterror)|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|none|[UnauthorizedError](#schemaunauthorizederror)|
|403|[Forbidden](https://tools.ietf.org/html/rfc7231#section-6.5.3)|none|[ForbiddenError](#schemaforbiddenerror)|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|none|[InternalServerError](#schemainternalservererror)|

<aside class="success">
This operation does not require authentication
</aside>

<h2 id="catalog-service-management">management</h2>

### Get Bundles

<a id="opIdGet Bundles"></a>

> Code samples

```shell
# You can also use wget
curl -X GET /management/bundles \
  -H 'Accept: application/json' \
  -H 'Authorization: API_KEY'

```

```javascript
var headers = {
  'Accept':'application/json',
  'Authorization':'API_KEY'

};

$.ajax({
  url: '/management/bundles',
  method: 'get',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

```javascript--nodejs
const fetch = require('node-fetch');

const headers = {
  'Accept':'application/json',
  'Authorization':'API_KEY'

};

fetch('/management/bundles',
{
  method: 'GET',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```python
import requests
headers = {
  'Accept': 'application/json',
  'Authorization': 'API_KEY'
}

r = requests.get('/management/bundles', params={

}, headers = headers)

print r.json()

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json',
  'Authorization' => 'API_KEY'
}

result = RestClient.get '/management/bundles',
  params: {
  }, headers: headers

p JSON.parse(result)

```

`GET /management/bundles`

Get a list of Bundles (meals or items) in the system. Bundle is an entity that can be sold on a menu. It can be either a simple Item (can of coke) or a complex Meal comprised of multiple Items sold together, like a build your own salad for example.

<h4 id="get-bundles-parameters">Parameters</h4>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|sortByName|query|string|false|none|
|tags|query|array[string]|false|none|
|search|query|undefined|false|none|
|limit|query|undefined|false|Default limit = 100 rows|
|page|query|undefined|false|Default page = 1|

#### Enumerated Values

|Parameter|Value|
|---|---|
|sortByName|ASC|
|sortByName|DESC|

> Example responses

> 200 Response

```json
[
  {
    "meta": {
      "page": 0,
      "limit": 0,
      "pageCount": 0,
      "totalCount": 0
    },
    "payload": [
      {
        "uuid": "string",
        "name": "string",
        "tags": [
          {
            "uuid": "string",
            "name": "string"
          }
        ],
        "type": "CUSTOMISED",
        "status": "string"
      }
    ]
  }
]
```

<h4 id="get-bundles-responses">Responses</h4>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Bundles|Inline|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|none|[BadRequestError](#schemabadrequesterror)|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|none|[UnauthorizedError](#schemaunauthorizederror)|
|403|[Forbidden](https://tools.ietf.org/html/rfc7231#section-6.5.3)|none|[ForbiddenError](#schemaforbiddenerror)|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|none|[InternalServerError](#schemainternalservererror)|

<h4 id="get-bundles-responseschema">Response Schema</h4>

Status Code **200**

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|*anonymous*|[[ManagementBundlesModel](#schemamanagementbundlesmodel)]|false|none|none|
|» meta|object|true|none|none|
|»» page|integer|true|none|none|
|»» limit|integer|true|none|none|
|»» pageCount|integer|true|none|none|
|»» totalCount|integer|true|none|none|
|» payload|[object]|true|none|none|
|»» uuid|string|true|none|none|
|»» name|string|true|none|none|
|»» tags|[object]|true|none|none|
|»»» uuid|string|true|none|none|
|»»» name|string|true|none|none|
|»» type|string|true|none|none|
|»» status|string|true|none|none|

#### Enumerated Values

|Property|Value|
|---|---|
|type|CUSTOMISED|
|type|VIRTUAL|
|type|BUILD_YOUR_OWN|
|type|FIXED_PRICE|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
bearer ( Scopes: ADMINISTRATOR MANAGER )
</aside>

### Create Bundle

<a id="opIdCreate Bundle"></a>

> Code samples

```shell
# You can also use wget
curl -X POST /management/bundles \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json' \
  -H 'Authorization: API_KEY'

```

```javascript
var headers = {
  'Content-Type':'application/json',
  'Accept':'application/json',
  'Authorization':'API_KEY'

};

$.ajax({
  url: '/management/bundles',
  method: 'post',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

```javascript--nodejs
const fetch = require('node-fetch');
const inputBody = '{
  "uuid": "string",
  "isFixedPrice": true,
  "status": true,
  "name": "string",
  "slug": "string",
  "description": "string",
  "taxExempt": "string",
  "straightToPickup": true,
  "isPrintable": true,
  "hasEatInPrice": true,
  "isGrouped": true,
  "upsellText": "string",
  "upsellItemTypeUUID": "string",
  "type": "CUSTOMISED",
  "onlineDescription": "string",
  "kitchenTicketGroup": "string",
  "price": 0,
  "priceFrom": 0,
  "priceEatInFrom": 0,
  "priceEatIn": 0,
  "tags": [
    {
      "name": "string",
      "uuid": "string"
    }
  ],
  "itemTypes": [
    {
      "uuid": "string",
      "name": "string",
      "sortOrder": 0,
      "minRestriction": 0,
      "maxRestriction": 0,
      "ticketGroup": "string",
      "isDefault": true,
      "isUpsellItemType": true,
      "items": [
        {
          "uuid": "string",
          "isPreselected": true,
          "isRequired": true,
          "sortOrder": 0,
          "price": 0
        }
      ]
    }
  ],
  "menus": [
    {
      "uuid": "string",
      "isActive": true,
      "isSoldOut": true,
      "price": 0
    }
  ]
}';
const headers = {
  'Content-Type':'application/json',
  'Accept':'application/json',
  'Authorization':'API_KEY'

};

fetch('/management/bundles',
{
  method: 'POST',
  body: inputBody,
  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json',
  'Authorization': 'API_KEY'
}

r = requests.post('/management/bundles', params={

}, headers = headers)

print r.json()

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Content-Type' => 'application/json',
  'Accept' => 'application/json',
  'Authorization' => 'API_KEY'
}

result = RestClient.post '/management/bundles',
  params: {
  }, headers: headers

p JSON.parse(result)

```

`POST /management/bundles`

Deep integrations only! Create new Bundles (meal or item).

> Body parameter

```json
{
  "uuid": "string",
  "isFixedPrice": true,
  "status": true,
  "name": "string",
  "slug": "string",
  "description": "string",
  "taxExempt": "string",
  "straightToPickup": true,
  "isPrintable": true,
  "hasEatInPrice": true,
  "isGrouped": true,
  "upsellText": "string",
  "upsellItemTypeUUID": "string",
  "type": "CUSTOMISED",
  "onlineDescription": "string",
  "kitchenTicketGroup": "string",
  "price": 0,
  "priceFrom": 0,
  "priceEatInFrom": 0,
  "priceEatIn": 0,
  "tags": [
    {
      "name": "string",
      "uuid": "string"
    }
  ],
  "itemTypes": [
    {
      "uuid": "string",
      "name": "string",
      "sortOrder": 0,
      "minRestriction": 0,
      "maxRestriction": 0,
      "ticketGroup": "string",
      "isDefault": true,
      "isUpsellItemType": true,
      "items": [
        {
          "uuid": "string",
          "isPreselected": true,
          "isRequired": true,
          "sortOrder": 0,
          "price": 0
        }
      ]
    }
  ],
  "menus": [
    {
      "uuid": "string",
      "isActive": true,
      "isSoldOut": true,
      "price": 0
    }
  ]
}
```

<h4 id="create-bundle-parameters">Parameters</h4>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|[ManagementBundleDto](#schemamanagementbundledto)|true|none|

> Example responses

> 201 Response

```json
{
  "payload": "d85cb735-71a8-472f-98c0-34380860845a"
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

> 403 Response

```json
{
  "statusCode": 403,
  "message": "Forbidden resource"
}
```

> 500 Response

```json
{
  "statusCode": 500,
  "message": "Internal server error!"
}
```

<h4 id="create-bundle-responses">Responses</h4>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|201|[Created](https://tools.ietf.org/html/rfc7231#section-6.3.2)|Bundle|[ManagementBundleUUID](#schemamanagementbundleuuid)|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|none|[BadRequestError](#schemabadrequesterror)|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|none|[UnauthorizedError](#schemaunauthorizederror)|
|403|[Forbidden](https://tools.ietf.org/html/rfc7231#section-6.5.3)|none|[ForbiddenError](#schemaforbiddenerror)|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|none|[InternalServerError](#schemainternalservererror)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
bearer ( Scopes: ADMINISTRATOR )
</aside>

### Update Bundle Menu Status

<a id="opIdUpdate Bundle Menu Status"></a>

> Code samples

```shell
# You can also use wget
curl -X PATCH /management/bundles/{bundleUUID}/menus-status \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json' \
  -H 'Authorization: API_KEY'

```

```javascript
var headers = {
  'Content-Type':'application/json',
  'Accept':'application/json',
  'Authorization':'API_KEY'

};

$.ajax({
  url: '/management/bundles/{bundleUUID}/menus-status',
  method: 'patch',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

```javascript--nodejs
const fetch = require('node-fetch');
const inputBody = '{
  "active": true
}';
const headers = {
  'Content-Type':'application/json',
  'Accept':'application/json',
  'Authorization':'API_KEY'

};

fetch('/management/bundles/{bundleUUID}/menus-status',
{
  method: 'PATCH',
  body: inputBody,
  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json',
  'Authorization': 'API_KEY'
}

r = requests.patch('/management/bundles/{bundleUUID}/menus-status', params={

}, headers = headers)

print r.json()

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Content-Type' => 'application/json',
  'Accept' => 'application/json',
  'Authorization' => 'API_KEY'
}

result = RestClient.patch '/management/bundles/{bundleUUID}/menus-status',
  params: {
  }, headers: headers

p JSON.parse(result)

```

`PATCH /management/bundles/{bundleUUID}/menus-status`

Deep integrations only! Update Bundle (meal or item) status in the menu

> Body parameter

```json
{
  "active": true
}
```

<h4 id="update-bundle-menu-status-parameters">Parameters</h4>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|[StatusUpdateDto](#schemastatusupdatedto)|true|none|
|bundleUUID|path|string|true|none|

> Example responses

> 400 Response

```json
{
  "statusCode": 0,
  "message": "string"
}
```

<h4 id="update-bundle-menu-status-responses">Responses</h4>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|none|None|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|none|[BadRequestError](#schemabadrequesterror)|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|none|[UnauthorizedError](#schemaunauthorizederror)|
|403|[Forbidden](https://tools.ietf.org/html/rfc7231#section-6.5.3)|none|[ForbiddenError](#schemaforbiddenerror)|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|none|[InternalServerError](#schemainternalservererror)|

<h4 id="update-bundle-menu-status-responseschema">Response Schema</h4>

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
bearer ( Scopes: ADMINISTRATOR MANAGER )
</aside>

### Get Bundle

<a id="opIdGet Bundle"></a>

> Code samples

```shell
# You can also use wget
curl -X GET /management/bundles/{uuid} \
  -H 'Accept: application/json' \
  -H 'Authorization: API_KEY'

```

```javascript
var headers = {
  'Accept':'application/json',
  'Authorization':'API_KEY'

};

$.ajax({
  url: '/management/bundles/{uuid}',
  method: 'get',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

```javascript--nodejs
const fetch = require('node-fetch');

const headers = {
  'Accept':'application/json',
  'Authorization':'API_KEY'

};

fetch('/management/bundles/{uuid}',
{
  method: 'GET',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```python
import requests
headers = {
  'Accept': 'application/json',
  'Authorization': 'API_KEY'
}

r = requests.get('/management/bundles/{uuid}', params={

}, headers = headers)

print r.json()

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json',
  'Authorization' => 'API_KEY'
}

result = RestClient.get '/management/bundles/{uuid}',
  params: {
  }, headers: headers

p JSON.parse(result)

```

`GET /management/bundles/{uuid}`

Get all Bundle (meal or item) information by UUID. Bundle rules (item types) with containing items, modifier information and pricing.

<h4 id="get-bundle-parameters">Parameters</h4>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|uuid|path|string|true|Bundle UUID|

> Example responses

> 200 Response

```json
{
  "payload": {
    "uuid": "gdfgpg9fdgdf8787gdfgdfdfsdifsdugd",
    "name": "Lattedfghdfh",
    "description": null,
    "taxExempt": null,
    "straightToPickup": false,
    "isPrintable": true,
    "price": 12,
    "priceFrom": 2,
    "priceEatInFrom": 2,
    "upsellText": "some upsel text",
    "upsellItemTypeUUID": null,
    "onlineDescription": "some onlineDescription description",
    "kitchenTicketGroup": "some kitchenTicketGroup description",
    "type": "FIXED_PRICE",
    "tags": [
      {
        "uuid": "gdfgpgfdgdfgdf54675756",
        "name": "Tag A"
      },
      {
        "uuid": "gdfgpg9fdgdf8787g756gjhgjgh",
        "name": "test a tag"
      },
      {
        "uuid": "gdfgpg9fdgrhyui7876",
        "name": "spread"
      }
    ],
    "itemTypes": [
      {
        "uuid": "d85cb735-71a8-472f-98c0-34380860845a",
        "name": "Base Coffee",
        "sortOrder": 0,
        "minRestriction": 1,
        "maxRestriction": 8,
        "ticketGroup": null,
        "isDefault": false,
        "isUpsellItemType": false,
        "items": [
          {
            "uuid": "treterte64564gfdg",
            "name": "Latte",
            "isPreselected": false,
            "isRequired": false,
            "sortOrder": 0,
            "price": 9.35,
            "basePrice": 11.3,
            "priceEatIn": 10,
            "hasEatInPrice": true,
            "baseItemModifiers": [
              {
                "uuid": "01dd24f9-fe5d-497d-8063-7d418db009d7",
                "meta": {
                  "text": "onoff",
                  "defaultValue": true
                },
                "modifier": {
                  "uuid": "t34435634634564grf",
                  "name": "Select On or off",
                  "meta": null,
                  "slug": "checkbox"
                }
              }
            ],
            "itemModifiers": [
              {
                "uuid": "01dd24f9-fe5d-497d-8063-7d418db009d7",
                "meta": {
                  "text": "onoff",
                  "defaultValue": true
                },
                "modifier": {
                  "uuid": "t34435634634564grf",
                  "name": "Select On or off",
                  "meta": null,
                  "slug": "checkbox"
                },
                "itemModifierOptions": [
                  {
                    "uuid": "3607fdsfdsfds",
                    "meta": {
                      "value": true
                    },
                    "measurementUnit": null,
                    "price": 0.08
                  }
                ]
              },
              {
                "uuid": "3df79e14-7184-4ee6-94d7-391681b412cf",
                "meta": {
                  "text": "quantity",
                  "defaultValue": 2
                },
                "modifier": {
                  "uuid": "tfrewtgre344356346rfger34564grf",
                  "name": "Select Quantity",
                  "meta": null,
                  "slug": "range"
                }
              }
            ]
          }
        ]
      },
      {
        "uuid": "efb6a40c-e756-4154-be3f-c22b5221d201",
        "name": "main",
        "sortOrder": 0,
        "minRestriction": 0,
        "maxRestriction": 0,
        "ticketGroup": null,
        "isDefault": true,
        "isUpsellItemType": false,
        "items": [
          {
            "uuid": "0fb6a40c-e756-4154-be3f-c22b5221d201",
            "name": "Multigrain bread",
            "isPreselected": false,
            "isRequired": false,
            "sortOrder": 1,
            "price": 12.4,
            "basePrice": 10,
            "priceEatIn": 0,
            "hasEatInPrice": false,
            "baseItemModifiers": [
              {
                "uuid": "01dd24f9-fe5d-497d-8063-7d418db009d7",
                "meta": {
                  "text": "onoff",
                  "defaultValue": true
                },
                "modifier": {
                  "uuid": "t34435634634564grf",
                  "name": "Select On or off",
                  "meta": null,
                  "slug": "checkbox"
                }
              }
            ],
            "itemModifiers": [
              {
                "uuid": "203a3618-2193-4792-b845-27018fa2807c",
                "meta": {
                  "text": "1",
                  "defaultValue": {
                    "value": null
                  }
                },
                "modifier": {
                  "uuid": "345-gdfgdf-54y-gfdg-fhg-gfhfhg-hgfhf",
                  "name": "Select Multiple",
                  "meta": null,
                  "slug": "checkbox-group"
                }
              }
            ]
          }
        ]
      }
    ],
    "menus": [
      {
        "uuid": "sdfasd",
        "name": "Main",
        "isActive": true,
        "isSoldOut": false,
        "price": "12"
      }
    ]
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

> 403 Response

```json
{
  "statusCode": 403,
  "message": "Forbidden resource"
}
```

> 500 Response

```json
{
  "statusCode": 500,
  "message": "Internal server error!"
}
```

<h4 id="get-bundle-responses">Responses</h4>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Bundle by uuid|[ManagementBundleModel](#schemamanagementbundlemodel)|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|none|[BadRequestError](#schemabadrequesterror)|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|none|[UnauthorizedError](#schemaunauthorizederror)|
|403|[Forbidden](https://tools.ietf.org/html/rfc7231#section-6.5.3)|none|[ForbiddenError](#schemaforbiddenerror)|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|none|[InternalServerError](#schemainternalservererror)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
bearer ( Scopes: ADMINISTRATOR MANAGER )
</aside>

### Update Bundle

<a id="opIdUpdate Bundle"></a>

> Code samples

```shell
# You can also use wget
curl -X PUT /management/bundles/{uuid} \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json' \
  -H 'Authorization: API_KEY'

```

```javascript
var headers = {
  'Content-Type':'application/json',
  'Accept':'application/json',
  'Authorization':'API_KEY'

};

$.ajax({
  url: '/management/bundles/{uuid}',
  method: 'put',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

```javascript--nodejs
const fetch = require('node-fetch');
const inputBody = '{
  "uuid": "string",
  "isFixedPrice": true,
  "status": true,
  "name": "string",
  "slug": "string",
  "description": "string",
  "taxExempt": "string",
  "straightToPickup": true,
  "isPrintable": true,
  "hasEatInPrice": true,
  "isGrouped": true,
  "upsellText": "string",
  "upsellItemTypeUUID": "string",
  "type": "CUSTOMISED",
  "onlineDescription": "string",
  "kitchenTicketGroup": "string",
  "price": 0,
  "priceFrom": 0,
  "priceEatInFrom": 0,
  "priceEatIn": 0,
  "tags": [
    {
      "name": "string",
      "uuid": "string"
    }
  ],
  "itemTypes": [
    {
      "uuid": "string",
      "name": "string",
      "sortOrder": 0,
      "minRestriction": 0,
      "maxRestriction": 0,
      "ticketGroup": "string",
      "isDefault": true,
      "isUpsellItemType": true,
      "items": [
        {
          "uuid": "string",
          "isPreselected": true,
          "isRequired": true,
          "sortOrder": 0,
          "price": 0
        }
      ]
    }
  ],
  "menus": [
    {
      "uuid": "string",
      "isActive": true,
      "isSoldOut": true,
      "price": 0
    }
  ]
}';
const headers = {
  'Content-Type':'application/json',
  'Accept':'application/json',
  'Authorization':'API_KEY'

};

fetch('/management/bundles/{uuid}',
{
  method: 'PUT',
  body: inputBody,
  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json',
  'Authorization': 'API_KEY'
}

r = requests.put('/management/bundles/{uuid}', params={

}, headers = headers)

print r.json()

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Content-Type' => 'application/json',
  'Accept' => 'application/json',
  'Authorization' => 'API_KEY'
}

result = RestClient.put '/management/bundles/{uuid}',
  params: {
  }, headers: headers

p JSON.parse(result)

```

`PUT /management/bundles/{uuid}`

Deep integrations only! Partial Bundle (meal or item) update.

> Body parameter

```json
{
  "uuid": "string",
  "isFixedPrice": true,
  "status": true,
  "name": "string",
  "slug": "string",
  "description": "string",
  "taxExempt": "string",
  "straightToPickup": true,
  "isPrintable": true,
  "hasEatInPrice": true,
  "isGrouped": true,
  "upsellText": "string",
  "upsellItemTypeUUID": "string",
  "type": "CUSTOMISED",
  "onlineDescription": "string",
  "kitchenTicketGroup": "string",
  "price": 0,
  "priceFrom": 0,
  "priceEatInFrom": 0,
  "priceEatIn": 0,
  "tags": [
    {
      "name": "string",
      "uuid": "string"
    }
  ],
  "itemTypes": [
    {
      "uuid": "string",
      "name": "string",
      "sortOrder": 0,
      "minRestriction": 0,
      "maxRestriction": 0,
      "ticketGroup": "string",
      "isDefault": true,
      "isUpsellItemType": true,
      "items": [
        {
          "uuid": "string",
          "isPreselected": true,
          "isRequired": true,
          "sortOrder": 0,
          "price": 0
        }
      ]
    }
  ],
  "menus": [
    {
      "uuid": "string",
      "isActive": true,
      "isSoldOut": true,
      "price": 0
    }
  ]
}
```

<h4 id="update-bundle-parameters">Parameters</h4>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|[ManagementBundleDto](#schemamanagementbundledto)|true|none|
|uuid|path|string|true|Bundle UUID|

> Example responses

> 400 Response

```json
{
  "statusCode": 0,
  "message": "string"
}
```

<h4 id="update-bundle-responses">Responses</h4>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|none|[BadRequestError](#schemabadrequesterror)|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|none|[UnauthorizedError](#schemaunauthorizederror)|
|403|[Forbidden](https://tools.ietf.org/html/rfc7231#section-6.5.3)|none|[ForbiddenError](#schemaforbiddenerror)|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|none|[InternalServerError](#schemainternalservererror)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
bearer ( Scopes: ADMINISTRATOR )
</aside>

### Get Items

<a id="opIdGet Items"></a>

> Code samples

```shell
# You can also use wget
curl -X GET /management/items \
  -H 'Accept: application/json' \
  -H 'Authorization: API_KEY'

```

```javascript
var headers = {
  'Accept':'application/json',
  'Authorization':'API_KEY'

};

$.ajax({
  url: '/management/items',
  method: 'get',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

```javascript--nodejs
const fetch = require('node-fetch');

const headers = {
  'Accept':'application/json',
  'Authorization':'API_KEY'

};

fetch('/management/items',
{
  method: 'GET',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```python
import requests
headers = {
  'Accept': 'application/json',
  'Authorization': 'API_KEY'
}

r = requests.get('/management/items', params={

}, headers = headers)

print r.json()

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json',
  'Authorization' => 'API_KEY'
}

result = RestClient.get '/management/items',
  params: {
  }, headers: headers

p JSON.parse(result)

```

`GET /management/items`

Get a list of Items in the system. Item is the base entity for describing sold food. It can be a resold packaged item like a can of coke or a comprising element for a Meal or Build your own (like avocado mash, or chicken thighs for example)

<h4 id="get-items-parameters">Parameters</h4>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|provideModifiersInfo|query|string|false|none|
|sortByName|query|string|false|none|
|tags|query|array[string]|false|none|
|search|query|undefined|false|none|
|limit|query|undefined|false|Default limit = 100 rows|
|page|query|undefined|false|Default page = 1|

#### Enumerated Values

|Parameter|Value|
|---|---|
|provideModifiersInfo|0|
|provideModifiersInfo|1|
|sortByName|ASC|
|sortByName|DESC|

> Example responses

> 200 Response

```json
{
  "required": [
    "meta",
    "payload"
  ],
  "type": "object",
  "properties": {
    "meta": {
      "required": [
        "page",
        "limit",
        "pageCount",
        "totalCount"
      ],
      "type": "object",
      "properties": {
        "page": {
          "type": "integer"
        },
        "limit": {
          "type": "integer"
        },
        "pageCount": {
          "type": "integer"
        },
        "totalCount": {
          "type": "integer"
        }
      }
    },
    "payload": {
      "type": "array",
      "items": {
        "required": [
          "uuid",
          "name",
          "tags",
          "status",
          "price"
        ],
        "type": "object",
        "properties": {
          "uuid": {
            "type": "string"
          },
          "name": {
            "type": "string"
          },
          "tags": {
            "type": "array",
            "items": {
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
            }
          },
          "status": {
            "type": "string"
          },
          "price": {
            "type": "number"
          },
          "itemModifiers": {
            "type": "array",
            "items": {
              "required": [
                "uuid",
                "modifier",
                "itemModifierOptions"
              ],
              "type": "object",
              "properties": {
                "uuid": {
                  "type": "string"
                },
                "meta": {
                  "type": "object"
                },
                "modifier": {
                  "required": [
                    "uuid",
                    "name"
                  ],
                  "type": "object",
                  "properties": {
                    "uuid": {},
                    "name": {},
                    "meta": {},
                    "slug": {}
                  }
                },
                "itemModifierOptions": {
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

<h4 id="get-items-responses">Responses</h4>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|List of items|[ItemsModel](#schemaitemsmodel)|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|none|[BadRequestError](#schemabadrequesterror)|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|none|[UnauthorizedError](#schemaunauthorizederror)|
|403|[Forbidden](https://tools.ietf.org/html/rfc7231#section-6.5.3)|none|[ForbiddenError](#schemaforbiddenerror)|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|none|[InternalServerError](#schemainternalservererror)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
bearer ( Scopes: ADMINISTRATOR MANAGER )
</aside>

### Create Item

<a id="opIdCreate Item"></a>

> Code samples

```shell
# You can also use wget
curl -X POST /management/items \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json' \
  -H 'Authorization: API_KEY'

```

```javascript
var headers = {
  'Content-Type':'application/json',
  'Accept':'application/json',
  'Authorization':'API_KEY'

};

$.ajax({
  url: '/management/items',
  method: 'post',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

```javascript--nodejs
const fetch = require('node-fetch');
const inputBody = '{
  "name": "string",
  "media": "string",
  "description": "string",
  "onlineDescription": "string",
  "taxRate": 0,
  "taxExempt": 0,
  "kitchenTicketName": "string",
  "kitchenZoneUUID": "string",
  "isPrintable": true,
  "price": 0,
  "straightToPickup": true,
  "slug": "string",
  "tags": [],
  "menus": [
    {
      "name": "string",
      "slug": "string",
      "description": "string",
      "sortOrder": 0,
      "interval": 0
    }
  ],
  "allergens": [
    "string"
  ],
  "diets": [
    "string"
  ],
  "itemModifiers": []
}';
const headers = {
  'Content-Type':'application/json',
  'Accept':'application/json',
  'Authorization':'API_KEY'

};

fetch('/management/items',
{
  method: 'POST',
  body: inputBody,
  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json',
  'Authorization': 'API_KEY'
}

r = requests.post('/management/items', params={

}, headers = headers)

print r.json()

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Content-Type' => 'application/json',
  'Accept' => 'application/json',
  'Authorization' => 'API_KEY'
}

result = RestClient.post '/management/items',
  params: {
  }, headers: headers

p JSON.parse(result)

```

`POST /management/items`

Deep integrations only! Create new Item.

> Body parameter

```json
{
  "name": "string",
  "media": "string",
  "description": "string",
  "onlineDescription": "string",
  "taxRate": 0,
  "taxExempt": 0,
  "kitchenTicketName": "string",
  "kitchenZoneUUID": "string",
  "isPrintable": true,
  "price": 0,
  "straightToPickup": true,
  "slug": "string",
  "tags": [],
  "menus": [
    {
      "name": "string",
      "slug": "string",
      "description": "string",
      "sortOrder": 0,
      "interval": 0
    }
  ],
  "allergens": [
    "string"
  ],
  "diets": [
    "string"
  ],
  "itemModifiers": []
}
```

<h4 id="create-item-parameters">Parameters</h4>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|[ItemManagementDto](#schemaitemmanagementdto)|true|none|

> Example responses

> 200 Response

```json
"string"
```

<h4 id="create-item-responses">Responses</h4>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Item|string|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|none|[BadRequestError](#schemabadrequesterror)|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|none|[UnauthorizedError](#schemaunauthorizederror)|
|403|[Forbidden](https://tools.ietf.org/html/rfc7231#section-6.5.3)|none|[ForbiddenError](#schemaforbiddenerror)|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|none|[InternalServerError](#schemainternalservererror)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
bearer ( Scopes: ADMINISTRATOR MANAGER )
</aside>

### Get Item

<a id="opIdGet Item"></a>

> Code samples

```shell
# You can also use wget
curl -X GET /management/items/{itemUUID} \
  -H 'Accept: application/json' \
  -H 'Authorization: API_KEY'

```

```javascript
var headers = {
  'Accept':'application/json',
  'Authorization':'API_KEY'

};

$.ajax({
  url: '/management/items/{itemUUID}',
  method: 'get',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

```javascript--nodejs
const fetch = require('node-fetch');

const headers = {
  'Accept':'application/json',
  'Authorization':'API_KEY'

};

fetch('/management/items/{itemUUID}',
{
  method: 'GET',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```python
import requests
headers = {
  'Accept': 'application/json',
  'Authorization': 'API_KEY'
}

r = requests.get('/management/items/{itemUUID}', params={

}, headers = headers)

print r.json()

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json',
  'Authorization' => 'API_KEY'
}

result = RestClient.get '/management/items/{itemUUID}',
  params: {
  }, headers: headers

p JSON.parse(result)

```

`GET /management/items/{itemUUID}`

Get all Item information by UUID. Modifier, nutrition information and pricing.

<h4 id="get-item-parameters">Parameters</h4>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|itemUUID|path|string|true|Item UUID|

> Example responses

> 200 Response

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
        "name",
        "kitchenTicketName",
        "taxExempt",
        "kitchenZoneUUID",
        "isPrintable",
        "tags",
        "price",
        "straightToPickup",
        "menus",
        "itemModifiers",
        "allergens",
        "diets"
      ],
      "type": "object",
      "properties": {
        "uuid": {
          "type": "string"
        },
        "name": {
          "type": "string"
        },
        "kitchenTicketName": {
          "type": "string"
        },
        "description": {
          "type": "string"
        },
        "taxRate": {
          "type": "number"
        },
        "taxExempt": {
          "type": "number"
        },
        "kitchenZoneUUID": {
          "type": "string"
        },
        "nutritionalMeta": {
          "type": "object"
        },
        "isPrintable": {
          "type": "boolean"
        },
        "hasEatInPrice": {
          "type": "boolean"
        },
        "slug": {
          "type": "string"
        },
        "tags": {
          "type": "array",
          "items": {
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
          }
        },
        "price": {
          "type": "number"
        },
        "priceEatIn": {
          "type": "number"
        },
        "straightToPickup": {
          "type": "boolean"
        },
        "allergens": {
          "type": "array",
          "items": {
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
              },
              "description": {
                "type": "string"
              },
              "image": {
                "type": "string"
              },
              "selectImage": {
                "type": "string"
              }
            }
          }
        },
        "diets": {
          "type": "array",
          "items": {
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
              },
              "description": {
                "type": "string"
              },
              "image": {
                "type": "string"
              },
              "selectImage": {
                "type": "string"
              }
            }
          }
        },
        "menus": {
          "type": "array",
          "items": {
            "required": [
              "menuUUID",
              "price",
              "isActive",
              "isSoldOut"
            ],
            "type": "object",
            "properties": {
              "menuUUID": {
                "type": "string"
              },
              "menu": {
                "required": [
                  "name",
                  "sortOrder",
                  "uuid"
                ],
                "type": "object",
                "properties": {
                  "name": {
                    "type": "string"
                  },
                  "sortOrder": {
                    "type": "number"
                  },
                  "uuid": {
                    "type": "string"
                  }
                }
              },
              "price": {
                "type": "string"
              },
              "isActive": {
                "type": "boolean"
              },
              "isSoldOut": {
                "type": "boolean"
              }
            }
          }
        },
        "itemModifiers": {
          "type": "array",
          "items": {
            "required": [
              "uuid",
              "modifier",
              "itemModifierOptions"
            ],
            "type": "object",
            "properties": {
              "uuid": {
                "type": "string"
              },
              "meta": {
                "type": "object"
              },
              "modifier": {
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
                  },
                  "meta": {
                    "type": "object"
                  },
                  "slug": {
                    "type": "string"
                  }
                }
              },
              "itemModifierOptions": {
                "type": "array",
                "items": {
                  "required": [
                    "uuid",
                    "price"
                  ],
                  "type": "object",
                  "properties": {
                    "uuid": {},
                    "meta": {},
                    "measurementUnit": {},
                    "price": {}
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

<h4 id="get-item-responses">Responses</h4>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Item by uuid|[ItemByUUIDModel](#schemaitembyuuidmodel)|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|none|[BadRequestError](#schemabadrequesterror)|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|none|[UnauthorizedError](#schemaunauthorizederror)|
|403|[Forbidden](https://tools.ietf.org/html/rfc7231#section-6.5.3)|none|[ForbiddenError](#schemaforbiddenerror)|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|none|[InternalServerError](#schemainternalservererror)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
bearer ( Scopes: ADMINISTRATOR MANAGER )
</aside>

### Update Item Menu Status

<a id="opIdUpdate Item Menu Status"></a>

> Code samples

```shell
# You can also use wget
curl -X PATCH /management/items/{itemUUID}/menus-status \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json' \
  -H 'Authorization: API_KEY'

```

```javascript
var headers = {
  'Content-Type':'application/json',
  'Accept':'application/json',
  'Authorization':'API_KEY'

};

$.ajax({
  url: '/management/items/{itemUUID}/menus-status',
  method: 'patch',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

```javascript--nodejs
const fetch = require('node-fetch');
const inputBody = '{
  "active": true
}';
const headers = {
  'Content-Type':'application/json',
  'Accept':'application/json',
  'Authorization':'API_KEY'

};

fetch('/management/items/{itemUUID}/menus-status',
{
  method: 'PATCH',
  body: inputBody,
  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json',
  'Authorization': 'API_KEY'
}

r = requests.patch('/management/items/{itemUUID}/menus-status', params={

}, headers = headers)

print r.json()

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Content-Type' => 'application/json',
  'Accept' => 'application/json',
  'Authorization' => 'API_KEY'
}

result = RestClient.patch '/management/items/{itemUUID}/menus-status',
  params: {
  }, headers: headers

p JSON.parse(result)

```

`PATCH /management/items/{itemUUID}/menus-status`

Deep integrations only! Update Item status in the menu

> Body parameter

```json
{
  "active": true
}
```

<h4 id="update-item-menu-status-parameters">Parameters</h4>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|[StatusUpdateDto](#schemastatusupdatedto)|true|none|
|itemUUID|path|string|true|Item UUID|

> Example responses

> 400 Response

```json
{
  "statusCode": 0,
  "message": "string"
}
```

<h4 id="update-item-menu-status-responses">Responses</h4>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|none|None|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|none|[BadRequestError](#schemabadrequesterror)|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|none|[UnauthorizedError](#schemaunauthorizederror)|
|403|[Forbidden](https://tools.ietf.org/html/rfc7231#section-6.5.3)|none|[ForbiddenError](#schemaforbiddenerror)|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|none|[InternalServerError](#schemainternalservererror)|

<h4 id="update-item-menu-status-responseschema">Response Schema</h4>

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
bearer ( Scopes: ADMINISTRATOR MANAGER )
</aside>

### Update Item

<a id="opIdUpdate Item"></a>

> Code samples

```shell
# You can also use wget
curl -X PUT /management/items/{uuid} \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json' \
  -H 'Authorization: API_KEY'

```

```javascript
var headers = {
  'Content-Type':'application/json',
  'Accept':'application/json',
  'Authorization':'API_KEY'

};

$.ajax({
  url: '/management/items/{uuid}',
  method: 'put',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

```javascript--nodejs
const fetch = require('node-fetch');
const inputBody = '{
  "name": "string",
  "media": "string",
  "description": "string",
  "onlineDescription": "string",
  "taxRate": 0,
  "taxExempt": 0,
  "kitchenTicketName": "string",
  "kitchenZoneUUID": "string",
  "isPrintable": true,
  "price": 0,
  "straightToPickup": true,
  "slug": "string",
  "tags": [],
  "menus": [
    {
      "name": "string",
      "slug": "string",
      "description": "string",
      "sortOrder": 0,
      "interval": 0
    }
  ],
  "allergens": [
    "string"
  ],
  "diets": [
    "string"
  ],
  "itemModifiers": []
}';
const headers = {
  'Content-Type':'application/json',
  'Accept':'application/json',
  'Authorization':'API_KEY'

};

fetch('/management/items/{uuid}',
{
  method: 'PUT',
  body: inputBody,
  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json',
  'Authorization': 'API_KEY'
}

r = requests.put('/management/items/{uuid}', params={

}, headers = headers)

print r.json()

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Content-Type' => 'application/json',
  'Accept' => 'application/json',
  'Authorization' => 'API_KEY'
}

result = RestClient.put '/management/items/{uuid}',
  params: {
  }, headers: headers

p JSON.parse(result)

```

`PUT /management/items/{uuid}`

Deep integrations only! Partial Item update.

> Body parameter

```json
{
  "name": "string",
  "media": "string",
  "description": "string",
  "onlineDescription": "string",
  "taxRate": 0,
  "taxExempt": 0,
  "kitchenTicketName": "string",
  "kitchenZoneUUID": "string",
  "isPrintable": true,
  "price": 0,
  "straightToPickup": true,
  "slug": "string",
  "tags": [],
  "menus": [
    {
      "name": "string",
      "slug": "string",
      "description": "string",
      "sortOrder": 0,
      "interval": 0
    }
  ],
  "allergens": [
    "string"
  ],
  "diets": [
    "string"
  ],
  "itemModifiers": []
}
```

<h4 id="update-item-parameters">Parameters</h4>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|[ItemManagementDto](#schemaitemmanagementdto)|true|none|
|uuid|path|string|true|Bundle UUID|

> Example responses

> 400 Response

```json
{
  "statusCode": 0,
  "message": "string"
}
```

<h4 id="update-item-responses">Responses</h4>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|none|[BadRequestError](#schemabadrequesterror)|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|none|[UnauthorizedError](#schemaunauthorizederror)|
|403|[Forbidden](https://tools.ietf.org/html/rfc7231#section-6.5.3)|none|[ForbiddenError](#schemaforbiddenerror)|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|none|[InternalServerError](#schemainternalservererror)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
bearer ( Scopes: ADMINISTRATOR MANAGER )
</aside>

### Get Kitchen Zones

<a id="opIdGet Kitchen Zones"></a>

> Code samples

```shell
# You can also use wget
curl -X GET /management/kitchen-zones \
  -H 'Accept: application/json' \
  -H 'Authorization: API_KEY'

```

```javascript
var headers = {
  'Accept':'application/json',
  'Authorization':'API_KEY'

};

$.ajax({
  url: '/management/kitchen-zones',
  method: 'get',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

```javascript--nodejs
const fetch = require('node-fetch');

const headers = {
  'Accept':'application/json',
  'Authorization':'API_KEY'

};

fetch('/management/kitchen-zones',
{
  method: 'GET',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```python
import requests
headers = {
  'Accept': 'application/json',
  'Authorization': 'API_KEY'
}

r = requests.get('/management/kitchen-zones', params={

}, headers = headers)

print r.json()

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json',
  'Authorization' => 'API_KEY'
}

result = RestClient.get '/management/kitchen-zones',
  params: {
  }, headers: headers

p JSON.parse(result)

```

`GET /management/kitchen-zones`

Get a list of kitchen zones described in the system. These represent sepparate areas in the kitchen. Build tickets and KDS screens will be sepparated into Kitchen Zones.

> Example responses

> 200 Response

```json
[
  {
    "payload": [
      {
        "uuid": "string",
        "name": "string",
        "slug": "string",
        "sortOrderOnPrint": 0,
        "capacity": 0
      }
    ]
  }
]
```

<h4 id="get-kitchen-zones-responses">Responses</h4>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|KitchenZones|Inline|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|none|[BadRequestError](#schemabadrequesterror)|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|none|[UnauthorizedError](#schemaunauthorizederror)|
|403|[Forbidden](https://tools.ietf.org/html/rfc7231#section-6.5.3)|none|[ForbiddenError](#schemaforbiddenerror)|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|none|[InternalServerError](#schemainternalservererror)|

<h4 id="get-kitchen-zones-responseschema">Response Schema</h4>

Status Code **200**

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|*anonymous*|[[KitchenZone](#schemakitchenzone)]|false|none|none|
|» payload|[object]|true|none|none|
|»» uuid|string|true|none|none|
|»» name|string|true|none|none|
|»» slug|string|true|none|none|
|»» sortOrderOnPrint|integer|true|none|none|
|»» capacity|integer|true|none|none|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
bearer ( Scopes: ADMINISTRATOR MANAGER )
</aside>

### Get Measurment Units

<a id="opIdGet Measurment Units"></a>

> Code samples

```shell
# You can also use wget
curl -X GET /management/measurement-units \
  -H 'Accept: application/json' \
  -H 'Authorization: API_KEY'

```

```javascript
var headers = {
  'Accept':'application/json',
  'Authorization':'API_KEY'

};

$.ajax({
  url: '/management/measurement-units',
  method: 'get',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

```javascript--nodejs
const fetch = require('node-fetch');

const headers = {
  'Accept':'application/json',
  'Authorization':'API_KEY'

};

fetch('/management/measurement-units',
{
  method: 'GET',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```python
import requests
headers = {
  'Accept': 'application/json',
  'Authorization': 'API_KEY'
}

r = requests.get('/management/measurement-units', params={

}, headers = headers)

print r.json()

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json',
  'Authorization' => 'API_KEY'
}

result = RestClient.get '/management/measurement-units',
  params: {
  }, headers: headers

p JSON.parse(result)

```

`GET /management/measurement-units`

Get a list of measurment units understood by the system.

> Example responses

> 200 Response

```json
[
  {
    "payload": [
      {
        "uuid": "string",
        "slug": "string",
        "name": "string",
        "value": 0
      }
    ]
  }
]
```

<h4 id="get-measurment-units-responses">Responses</h4>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|MeasurementUnits|Inline|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|none|[BadRequestError](#schemabadrequesterror)|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|none|[UnauthorizedError](#schemaunauthorizederror)|
|403|[Forbidden](https://tools.ietf.org/html/rfc7231#section-6.5.3)|none|[ForbiddenError](#schemaforbiddenerror)|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|none|[InternalServerError](#schemainternalservererror)|

<h4 id="get-measurment-units-responseschema">Response Schema</h4>

Status Code **200**

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|*anonymous*|[[MeasurementUnits](#schemameasurementunits)]|false|none|none|
|» payload|[object]|true|none|none|
|»» uuid|string|true|none|none|
|»» slug|string|false|none|none|
|»» name|string|true|none|none|
|»» value|integer|true|none|none|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
bearer ( Scopes: ADMINISTRATOR MANAGER )
</aside>

### Get Menus

<a id="opIdGet Menus"></a>

> Code samples

```shell
# You can also use wget
curl -X GET /management/menus \
  -H 'Accept: application/json' \
  -H 'Authorization: API_KEY'

```

```javascript
var headers = {
  'Accept':'application/json',
  'Authorization':'API_KEY'

};

$.ajax({
  url: '/management/menus',
  method: 'get',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

```javascript--nodejs
const fetch = require('node-fetch');

const headers = {
  'Accept':'application/json',
  'Authorization':'API_KEY'

};

fetch('/management/menus',
{
  method: 'GET',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```python
import requests
headers = {
  'Accept': 'application/json',
  'Authorization': 'API_KEY'
}

r = requests.get('/management/menus', params={

}, headers = headers)

print r.json()

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json',
  'Authorization' => 'API_KEY'
}

result = RestClient.get '/management/menus',
  params: {
  }, headers: headers

p JSON.parse(result)

```

`GET /management/menus`

Get a list of menus. A menu is a grouping of Bundles (meals or items) that can be configured to be sold together. It contains pricing information alongside the list of Bundles. One menu can be extended on multiple stores and can be presented in different layouts. Examples of menus can be breakfast menus, lunch menus, Xmas special menus.

<h4 id="get-menus-parameters">Parameters</h4>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|search|query|string|false|none|

> Example responses

> 200 Response

```json
[
  {
    "payload": {
      "name": "string",
      "slug": "string",
      "description": "string",
      "sortOrder": 0,
      "interval": 0
    }
  }
]
```

<h4 id="get-menus-responses">Responses</h4>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Menus|Inline|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|none|[BadRequestError](#schemabadrequesterror)|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|none|[UnauthorizedError](#schemaunauthorizederror)|
|403|[Forbidden](https://tools.ietf.org/html/rfc7231#section-6.5.3)|none|[ForbiddenError](#schemaforbiddenerror)|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|none|[InternalServerError](#schemainternalservererror)|

<h4 id="get-menus-responseschema">Response Schema</h4>

Status Code **200**

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|*anonymous*|[[Menu](#schemamenu)]|false|none|none|
|» payload|object|true|none|none|
|»» name|string|true|none|none|
|»» slug|string|true|none|none|
|»» description|string|false|none|none|
|»» sortOrder|integer|true|none|none|
|»» interval|integer|false|none|none|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
bearer ( Scopes: ADMINISTRATOR MANAGER )
</aside>

### Create Menu

<a id="opIdCreate Menu"></a>

> Code samples

```shell
# You can also use wget
curl -X POST /management/menus \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json' \
  -H 'Authorization: API_KEY'

```

```javascript
var headers = {
  'Content-Type':'application/json',
  'Accept':'application/json',
  'Authorization':'API_KEY'

};

$.ajax({
  url: '/management/menus',
  method: 'post',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

```javascript--nodejs
const fetch = require('node-fetch');
const inputBody = '{
  "name": "string",
  "slug": "string",
  "description": "string",
  "sortOrder": 0,
  "interval": 0
}';
const headers = {
  'Content-Type':'application/json',
  'Accept':'application/json',
  'Authorization':'API_KEY'

};

fetch('/management/menus',
{
  method: 'POST',
  body: inputBody,
  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json',
  'Authorization': 'API_KEY'
}

r = requests.post('/management/menus', params={

}, headers = headers)

print r.json()

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Content-Type' => 'application/json',
  'Accept' => 'application/json',
  'Authorization' => 'API_KEY'
}

result = RestClient.post '/management/menus',
  params: {
  }, headers: headers

p JSON.parse(result)

```

`POST /management/menus`

Deep integrations only! Create a new Menu.

> Body parameter

```json
{
  "name": "string",
  "slug": "string",
  "description": "string",
  "sortOrder": 0,
  "interval": 0
}
```

<h4 id="create-menu-parameters">Parameters</h4>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|[MenuDto](#schemamenudto)|true|none|

> Example responses

> 200 Response

```json
{
  "payload": {
    "name": "string",
    "slug": "string",
    "description": "string",
    "sortOrder": 0,
    "interval": 0
  }
}
```

<h4 id="create-menu-responses">Responses</h4>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Menu|[Menu](#schemamenu)|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|none|[BadRequestError](#schemabadrequesterror)|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|none|[UnauthorizedError](#schemaunauthorizederror)|
|403|[Forbidden](https://tools.ietf.org/html/rfc7231#section-6.5.3)|none|[ForbiddenError](#schemaforbiddenerror)|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|none|[InternalServerError](#schemainternalservererror)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
bearer ( Scopes: ADMINISTRATOR MANAGER )
</aside>

### Get Menu

<a id="opIdGet Menu"></a>

> Code samples

```shell
# You can also use wget
curl -X GET /management/menus/{menuUUID} \
  -H 'Accept: application/json' \
  -H 'Authorization: API_KEY'

```

```javascript
var headers = {
  'Accept':'application/json',
  'Authorization':'API_KEY'

};

$.ajax({
  url: '/management/menus/{menuUUID}',
  method: 'get',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

```javascript--nodejs
const fetch = require('node-fetch');

const headers = {
  'Accept':'application/json',
  'Authorization':'API_KEY'

};

fetch('/management/menus/{menuUUID}',
{
  method: 'GET',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```python
import requests
headers = {
  'Accept': 'application/json',
  'Authorization': 'API_KEY'
}

r = requests.get('/management/menus/{menuUUID}', params={

}, headers = headers)

print r.json()

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json',
  'Authorization' => 'API_KEY'
}

result = RestClient.get '/management/menus/{menuUUID}',
  params: {
  }, headers: headers

p JSON.parse(result)

```

`GET /management/menus/{menuUUID}`

Get information about a specific Menu.

<h4 id="get-menu-parameters">Parameters</h4>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|menuUUID|path|string|true|none|

> Example responses

> 200 Response

```json
{
  "payload": {
    "name": "string",
    "slug": "string",
    "description": "string",
    "sortOrder": 0,
    "interval": 0
  }
}
```

<h4 id="get-menu-responses">Responses</h4>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|none|[Menu](#schemamenu)|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|none|[BadRequestError](#schemabadrequesterror)|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|none|[UnauthorizedError](#schemaunauthorizederror)|
|403|[Forbidden](https://tools.ietf.org/html/rfc7231#section-6.5.3)|none|[ForbiddenError](#schemaforbiddenerror)|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|none|[InternalServerError](#schemainternalservererror)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
bearer ( Scopes: ADMINISTRATOR MANAGER )
</aside>

### Update Menu

<a id="opIdUpdate Menu"></a>

> Code samples

```shell
# You can also use wget
curl -X PUT /management/menus/{menuUUID} \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json' \
  -H 'Authorization: API_KEY'

```

```javascript
var headers = {
  'Content-Type':'application/json',
  'Accept':'application/json',
  'Authorization':'API_KEY'

};

$.ajax({
  url: '/management/menus/{menuUUID}',
  method: 'put',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

```javascript--nodejs
const fetch = require('node-fetch');
const inputBody = '{
  "name": "string",
  "slug": "string",
  "description": "string",
  "sortOrder": 0,
  "interval": 0
}';
const headers = {
  'Content-Type':'application/json',
  'Accept':'application/json',
  'Authorization':'API_KEY'

};

fetch('/management/menus/{menuUUID}',
{
  method: 'PUT',
  body: inputBody,
  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json',
  'Authorization': 'API_KEY'
}

r = requests.put('/management/menus/{menuUUID}', params={

}, headers = headers)

print r.json()

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Content-Type' => 'application/json',
  'Accept' => 'application/json',
  'Authorization' => 'API_KEY'
}

result = RestClient.put '/management/menus/{menuUUID}',
  params: {
  }, headers: headers

p JSON.parse(result)

```

`PUT /management/menus/{menuUUID}`

Deep integrations only! Update Menu information.

> Body parameter

```json
{
  "name": "string",
  "slug": "string",
  "description": "string",
  "sortOrder": 0,
  "interval": 0
}
```

<h4 id="update-menu-parameters">Parameters</h4>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|[MenuDto](#schemamenudto)|true|none|
|menuUUID|path|string|true|none|

> Example responses

> 200 Response

```json
{
  "name": "string",
  "slug": "string",
  "description": "string",
  "sortOrder": 0,
  "interval": 0
}
```

<h4 id="update-menu-responses">Responses</h4>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Menu|[MenuDto](#schemamenudto)|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|none|[BadRequestError](#schemabadrequesterror)|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|none|[UnauthorizedError](#schemaunauthorizederror)|
|403|[Forbidden](https://tools.ietf.org/html/rfc7231#section-6.5.3)|none|[ForbiddenError](#schemaforbiddenerror)|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|none|[InternalServerError](#schemainternalservererror)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
bearer
</aside>

### Get Modifiers

<a id="opIdGet Modifiers"></a>

> Code samples

```shell
# You can also use wget
curl -X GET /management/modifiers \
  -H 'Accept: application/json' \
  -H 'Authorization: API_KEY'

```

```javascript
var headers = {
  'Accept':'application/json',
  'Authorization':'API_KEY'

};

$.ajax({
  url: '/management/modifiers',
  method: 'get',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

```javascript--nodejs
const fetch = require('node-fetch');

const headers = {
  'Accept':'application/json',
  'Authorization':'API_KEY'

};

fetch('/management/modifiers',
{
  method: 'GET',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```python
import requests
headers = {
  'Accept': 'application/json',
  'Authorization': 'API_KEY'
}

r = requests.get('/management/modifiers', params={

}, headers = headers)

print r.json()

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json',
  'Authorization' => 'API_KEY'
}

result = RestClient.get '/management/modifiers',
  params: {
  }, headers: headers

p JSON.parse(result)

```

`GET /management/modifiers`

Get a list of modifiers in the system.

> Example responses

> 200 Response

```json
[
  {
    "payload": [
      {
        "uuid": "string",
        "name": "string",
        "meta": {},
        "slug": "string"
      }
    ]
  }
]
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

> 403 Response

```json
{
  "statusCode": 403,
  "message": "Forbidden resource"
}
```

> 500 Response

```json
{
  "statusCode": 500,
  "message": "Internal server error!"
}
```

<h4 id="get-modifiers-responses">Responses</h4>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Modifiers|Inline|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|none|[UnauthorizedError](#schemaunauthorizederror)|
|403|[Forbidden](https://tools.ietf.org/html/rfc7231#section-6.5.3)|none|[ForbiddenError](#schemaforbiddenerror)|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|none|[InternalServerError](#schemainternalservererror)|

<h4 id="get-modifiers-responseschema">Response Schema</h4>

Status Code **200**

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|*anonymous*|[[Modifier](#schemamodifier)]|false|none|none|
|» payload|[object]|true|none|none|
|»» uuid|string|true|none|none|
|»» name|string|true|none|none|
|»» meta|object|false|none|none|
|»» slug|string|true|none|none|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
bearer ( Scopes: ADMINISTRATOR MANAGER )
</aside>

### Get Allergens

<a id="opIdGet Allergens"></a>

> Code samples

```shell
# You can also use wget
curl -X GET /management/allergens \
  -H 'Accept: application/json' \
  -H 'tenant: string' \
  -H 'Authorization: API_KEY'

```

```javascript
var headers = {
  'Accept':'application/json',
  'tenant':'string',
  'Authorization':'API_KEY'

};

$.ajax({
  url: '/management/allergens',
  method: 'get',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

```javascript--nodejs
const fetch = require('node-fetch');

const headers = {
  'Accept':'application/json',
  'tenant':'string',
  'Authorization':'API_KEY'

};

fetch('/management/allergens',
{
  method: 'GET',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```python
import requests
headers = {
  'Accept': 'application/json',
  'tenant': 'string',
  'Authorization': 'API_KEY'
}

r = requests.get('/management/allergens', params={

}, headers = headers)

print r.json()

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json',
  'tenant' => 'string',
  'Authorization' => 'API_KEY'
}

result = RestClient.get '/management/allergens',
  params: {
  }, headers: headers

p JSON.parse(result)

```

`GET /management/allergens`

Get a list of allergens described in the system.

<h4 id="get-allergens-parameters">Parameters</h4>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|tenant|header|string|true|External Tenant UUID (832b34ad-2608-4cc7-bee8-bfc47686d801)|
|search|query|undefined|false|Search allergen by name|

> Example responses

> 200 Response

```json
[
  {
    "payload": [
      {
        "uuid": "string",
        "name": "string",
        "description": "string",
        "image": "string",
        "selectImage": "string"
      }
    ]
  }
]
```

> 400 Response

```json
{
  "statusCode": 400,
  "message": "Please select store first!"
}
```

> 403 Response

```json
{
  "statusCode": 403,
  "message": "Forbidden resource"
}
```

> 404 Response

```json
{
  "statusCode": 404,
  "message": "Cannot GET ..."
}
```

> 500 Response

```json
{
  "statusCode": 500,
  "message": "Internal server error!"
}
```

<h4 id="get-allergens-responses">Responses</h4>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|ManagementAllergens|Inline|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|none|[BadRequestError](#schemabadrequesterror)|
|403|[Forbidden](https://tools.ietf.org/html/rfc7231#section-6.5.3)|none|[ForbiddenError](#schemaforbiddenerror)|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|none|[NotFoundError](#schemanotfounderror)|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|none|[InternalServerError](#schemainternalservererror)|

<h4 id="get-allergens-responseschema">Response Schema</h4>

Status Code **200**

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|*anonymous*|[[ManagementAllergens](#schemamanagementallergens)]|false|none|none|
|» payload|[object]|true|none|none|
|»» uuid|string|true|none|none|
|»» name|string|true|none|none|
|»» description|string|true|none|none|
|»» image|string|true|none|none|
|»» selectImage|string|true|none|none|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
bearer ( Scopes: ADMINISTRATOR MANAGER )
</aside>

### Get Diets

<a id="opIdGet Diets"></a>

> Code samples

```shell
# You can also use wget
curl -X GET /management/diets \
  -H 'Accept: application/json' \
  -H 'tenant: string' \
  -H 'Authorization: API_KEY'

```

```javascript
var headers = {
  'Accept':'application/json',
  'tenant':'string',
  'Authorization':'API_KEY'

};

$.ajax({
  url: '/management/diets',
  method: 'get',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

```javascript--nodejs
const fetch = require('node-fetch');

const headers = {
  'Accept':'application/json',
  'tenant':'string',
  'Authorization':'API_KEY'

};

fetch('/management/diets',
{
  method: 'GET',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```python
import requests
headers = {
  'Accept': 'application/json',
  'tenant': 'string',
  'Authorization': 'API_KEY'
}

r = requests.get('/management/diets', params={

}, headers = headers)

print r.json()

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json',
  'tenant' => 'string',
  'Authorization' => 'API_KEY'
}

result = RestClient.get '/management/diets',
  params: {
  }, headers: headers

p JSON.parse(result)

```

`GET /management/diets`

Get a list of diets described in the system.

<h4 id="get-diets-parameters">Parameters</h4>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|tenant|header|string|true|External Tenant UUID (832b34ad-2608-4cc7-bee8-bfc47686d801)|
|search|query|undefined|false|Search allergen by name|

> Example responses

> 200 Response

```json
[
  {
    "payload": [
      {
        "uuid": "string",
        "name": "string",
        "description": "string",
        "image": "string",
        "selectImage": "string"
      }
    ]
  }
]
```

> 400 Response

```json
{
  "statusCode": 400,
  "message": "Please select store first!"
}
```

> 403 Response

```json
{
  "statusCode": 403,
  "message": "Forbidden resource"
}
```

> 404 Response

```json
{
  "statusCode": 404,
  "message": "Cannot GET ..."
}
```

> 500 Response

```json
{
  "statusCode": 500,
  "message": "Internal server error!"
}
```

<h4 id="get-diets-responses">Responses</h4>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|ManagementDiets|Inline|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|none|[BadRequestError](#schemabadrequesterror)|
|403|[Forbidden](https://tools.ietf.org/html/rfc7231#section-6.5.3)|none|[ForbiddenError](#schemaforbiddenerror)|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|none|[NotFoundError](#schemanotfounderror)|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|none|[InternalServerError](#schemainternalservererror)|

<h4 id="get-diets-responseschema">Response Schema</h4>

Status Code **200**

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|*anonymous*|[[ManagementDiets](#schemamanagementdiets)]|false|none|none|
|» payload|[object]|true|none|none|
|»» uuid|string|true|none|none|
|»» name|string|true|none|none|
|»» description|string|true|none|none|
|»» image|string|true|none|none|
|»» selectImage|string|true|none|none|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
bearer ( Scopes: ADMINISTRATOR MANAGER )
</aside>

### Get Tags

<a id="opIdGet Tags"></a>

> Code samples

```shell
# You can also use wget
curl -X GET /management/tags \
  -H 'Accept: application/json' \
  -H 'Authorization: API_KEY'

```

```javascript
var headers = {
  'Accept':'application/json',
  'Authorization':'API_KEY'

};

$.ajax({
  url: '/management/tags',
  method: 'get',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

```javascript--nodejs
const fetch = require('node-fetch');

const headers = {
  'Accept':'application/json',
  'Authorization':'API_KEY'

};

fetch('/management/tags',
{
  method: 'GET',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```python
import requests
headers = {
  'Accept': 'application/json',
  'Authorization': 'API_KEY'
}

r = requests.get('/management/tags', params={

}, headers = headers)

print r.json()

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json',
  'Authorization' => 'API_KEY'
}

result = RestClient.get '/management/tags',
  params: {
  }, headers: headers

p JSON.parse(result)

```

`GET /management/tags`

Get a list of tags in the system. Tags are used for grouping and searching in the system. Bundles and Items can be tagged.

<h4 id="get-tags-parameters">Parameters</h4>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|search|query|undefined|false|Search tags by name|

> Example responses

> 200 Response

```json
[
  {
    "payload": [
      {
        "uuid": "string",
        "name": "string"
      }
    ]
  }
]
```

<h4 id="get-tags-responses">Responses</h4>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Tags|Inline|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|none|[BadRequestError](#schemabadrequesterror)|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|none|[UnauthorizedError](#schemaunauthorizederror)|
|403|[Forbidden](https://tools.ietf.org/html/rfc7231#section-6.5.3)|none|[ForbiddenError](#schemaforbiddenerror)|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|none|[InternalServerError](#schemainternalservererror)|

<h4 id="get-tags-responseschema">Response Schema</h4>

Status Code **200**

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|*anonymous*|[[Tag](#schematag)]|false|none|none|
|» payload|[object]|true|none|none|
|»» uuid|string|true|none|none|
|»» name|string|true|none|none|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
bearer ( Scopes: ADMINISTRATOR MANAGER )
</aside>

### Get Unites

<a id="opIdGet Unites"></a>

> Code samples

```shell
# You can also use wget
curl -X GET /management/units \
  -H 'Accept: application/json' \
  -H 'Authorization: API_KEY'

```

```javascript
var headers = {
  'Accept':'application/json',
  'Authorization':'API_KEY'

};

$.ajax({
  url: '/management/units',
  method: 'get',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

```javascript--nodejs
const fetch = require('node-fetch');

const headers = {
  'Accept':'application/json',
  'Authorization':'API_KEY'

};

fetch('/management/units',
{
  method: 'GET',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```python
import requests
headers = {
  'Accept': 'application/json',
  'Authorization': 'API_KEY'
}

r = requests.get('/management/units', params={

}, headers = headers)

print r.json()

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json',
  'Authorization' => 'API_KEY'
}

result = RestClient.get '/management/units',
  params: {
  }, headers: headers

p JSON.parse(result)

```

`GET /management/units`

Get a list of units in the system. Items can be sold in random user definied units. For example pinches, scoops, etc. Underlying these there will be a quantity defined in a mesurmeant unit.

> Example responses

> 200 Response

```json
[
  {
    "payload": [
      {
        "slug": "string",
        "name": "string"
      }
    ]
  }
]
```

<h4 id="get-unites-responses">Responses</h4>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Units|Inline|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|none|[BadRequestError](#schemabadrequesterror)|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|none|[UnauthorizedError](#schemaunauthorizederror)|
|403|[Forbidden](https://tools.ietf.org/html/rfc7231#section-6.5.3)|none|[ForbiddenError](#schemaforbiddenerror)|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|none|[InternalServerError](#schemainternalservererror)|

<h4 id="get-unites-responseschema">Response Schema</h4>

Status Code **200**

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|*anonymous*|[[Unit](#schemaunit)]|false|none|none|
|» payload|[object]|true|none|none|
|»» slug|string|true|none|none|
|»» name|string|true|none|none|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
bearer ( Scopes: ADMINISTRATOR MANAGER )
</aside>

### Get Menu Layouts

<a id="opIdGet Menu Layouts"></a>

> Code samples

```shell
# You can also use wget
curl -X GET /management/layout/{type}/menus \
  -H 'Accept: application/json' \
  -H 'store: string' \
  -H 'Authorization: API_KEY'

```

```javascript
var headers = {
  'Accept':'application/json',
  'store':'string',
  'Authorization':'API_KEY'

};

$.ajax({
  url: '/management/layout/{type}/menus',
  method: 'get',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

```javascript--nodejs
const fetch = require('node-fetch');

const headers = {
  'Accept':'application/json',
  'store':'string',
  'Authorization':'API_KEY'

};

fetch('/management/layout/{type}/menus',
{
  method: 'GET',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```python
import requests
headers = {
  'Accept': 'application/json',
  'store': 'string',
  'Authorization': 'API_KEY'
}

r = requests.get('/management/layout/{type}/menus', params={

}, headers = headers)

print r.json()

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json',
  'store' => 'string',
  'Authorization' => 'API_KEY'
}

result = RestClient.get '/management/layout/{type}/menus',
  params: {
  }, headers: headers

p JSON.parse(result)

```

`GET /management/layout/{type}/menus`

Deep integrations only! Get a list of menu layouts. A menu can have multiple layouts. A layout is a hierarchy of categories grouping the Bundles on the menu. This can be different for POS/Kiosk/Online etc. The Layout routes are ment for creating and updating complex layouts for pos/kiosk/online.

<h4 id="get-menu-layouts-parameters">Parameters</h4>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|store|header|string|true|External Store UUID (876b34ad-45654-4ds7-cdd8-bfc47686d999)|
|type|path|string|true|Menu Layout type (kiosk, pos)|

> Example responses

> 200 Response

```json
[
  {
    "payload": [
      {
        "uuid": "string",
        "name": "string",
        "isActive": true,
        "isVisible": true
      }
    ]
  }
]
```

<h4 id="get-menu-layouts-responses">Responses</h4>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Menus|Inline|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|none|[BadRequestError](#schemabadrequesterror)|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|none|[UnauthorizedError](#schemaunauthorizederror)|
|403|[Forbidden](https://tools.ietf.org/html/rfc7231#section-6.5.3)|none|[ForbiddenError](#schemaforbiddenerror)|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|none|[InternalServerError](#schemainternalservererror)|

<h4 id="get-menu-layouts-responseschema">Response Schema</h4>

Status Code **200**

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|*anonymous*|[[LayoutMenuModel](#schemalayoutmenumodel)]|false|none|none|
|» payload|[object]|true|none|none|
|»» uuid|string|true|none|none|
|»» name|string|true|none|none|
|»» isActive|boolean|true|none|none|
|»» isVisible|boolean|true|none|none|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
bearer ( Scopes: ADMINISTRATOR MANAGER )
</aside>

### Add Menu Layout Type

<a id="opIdAdd Menu Layout Type"></a>

> Code samples

```shell
# You can also use wget
curl -X PUT /management/layout/{type}/menus \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json' \
  -H 'store: string' \
  -H 'Authorization: API_KEY'

```

```javascript
var headers = {
  'Content-Type':'application/json',
  'Accept':'application/json',
  'store':'string',
  'Authorization':'API_KEY'

};

$.ajax({
  url: '/management/layout/{type}/menus',
  method: 'put',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

```javascript--nodejs
const fetch = require('node-fetch');
const inputBody = 'false';
const headers = {
  'Content-Type':'application/json',
  'Accept':'application/json',
  'store':'string',
  'Authorization':'API_KEY'

};

fetch('/management/layout/{type}/menus',
{
  method: 'PUT',
  body: inputBody,
  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json',
  'store': 'string',
  'Authorization': 'API_KEY'
}

r = requests.put('/management/layout/{type}/menus', params={

}, headers = headers)

print r.json()

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Content-Type' => 'application/json',
  'Accept' => 'application/json',
  'store' => 'string',
  'Authorization' => 'API_KEY'
}

result = RestClient.put '/management/layout/{type}/menus',
  params: {
  }, headers: headers

p JSON.parse(result)

```

`PUT /management/layout/{type}/menus`

Deep integrations only! Add a menu layout type to a menu. A layout type can be POS/Kiosk/Online and specifies what the layout was meant for.

> Body parameter

```json
false
```

<h4 id="add-menu-layout-type-parameters">Parameters</h4>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|store|header|string|true|External Store UUID (876b34ad-45654-4ds7-cdd8-bfc47686d999)|
|type|path|string|true|Menu Layout type (kiosk, pos)|

> Example responses

> 400 Response

```json
{
  "statusCode": 0,
  "message": "string"
}
```

<h4 id="add-menu-layout-type-responses">Responses</h4>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|204|[No Content](https://tools.ietf.org/html/rfc7231#section-6.3.5)|No content|None|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|none|[BadRequestError](#schemabadrequesterror)|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|none|[UnauthorizedError](#schemaunauthorizederror)|
|403|[Forbidden](https://tools.ietf.org/html/rfc7231#section-6.5.3)|none|[ForbiddenError](#schemaforbiddenerror)|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|none|[InternalServerError](#schemainternalservererror)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
bearer ( Scopes: ADMINISTRATOR )
</aside>

### Get Categories

<a id="opIdGet Categories"></a>

> Code samples

```shell
# You can also use wget
curl -X GET /management/layout/{type}/menus/{menuUUID}/categories \
  -H 'Accept: application/json' \
  -H 'store: string' \
  -H 'Authorization: API_KEY'

```

```javascript
var headers = {
  'Accept':'application/json',
  'store':'string',
  'Authorization':'API_KEY'

};

$.ajax({
  url: '/management/layout/{type}/menus/{menuUUID}/categories',
  method: 'get',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

```javascript--nodejs
const fetch = require('node-fetch');

const headers = {
  'Accept':'application/json',
  'store':'string',
  'Authorization':'API_KEY'

};

fetch('/management/layout/{type}/menus/{menuUUID}/categories',
{
  method: 'GET',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```python
import requests
headers = {
  'Accept': 'application/json',
  'store': 'string',
  'Authorization': 'API_KEY'
}

r = requests.get('/management/layout/{type}/menus/{menuUUID}/categories', params={

}, headers = headers)

print r.json()

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json',
  'store' => 'string',
  'Authorization' => 'API_KEY'
}

result = RestClient.get '/management/layout/{type}/menus/{menuUUID}/categories',
  params: {
  }, headers: headers

p JSON.parse(result)

```

`GET /management/layout/{type}/menus/{menuUUID}/categories`

Deep integrations only! Get a list of categories on the specified menu layout.

<h4 id="get-categories-parameters">Parameters</h4>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|store|header|string|true|Get layout menu categories by Store UUID|
|menuUUID|path|string|true|Menu UUID|
|type|path|string|true|Menu Layout type (kiosk, pos)|

> Example responses

> 200 Response

```json
{
  "payload": [
    {
      "uuid": "string",
      "name": "string",
      "type": "string",
      "sortOrder": 0
    }
  ]
}
```

<h4 id="get-categories-responses">Responses</h4>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Layout Menu Categories|[LayoutMenuCategories](#schemalayoutmenucategories)|
|201|[Created](https://tools.ietf.org/html/rfc7231#section-6.3.2)|On POS menu layout the Root category is created on get request|[LayoutMenuCategories](#schemalayoutmenucategories)|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|none|[BadRequestError](#schemabadrequesterror)|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|none|[UnauthorizedError](#schemaunauthorizederror)|
|403|[Forbidden](https://tools.ietf.org/html/rfc7231#section-6.5.3)|none|[ForbiddenError](#schemaforbiddenerror)|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|none|[InternalServerError](#schemainternalservererror)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
bearer ( Scopes: ADMINISTRATOR )
</aside>

### Add Category to Layout

<a id="opIdAdd Category to Layout"></a>

> Code samples

```shell
# You can also use wget
curl -X PUT /management/layout/{type}/menus/{menuUUID}/categories \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json' \
  -H 'store: string' \
  -H 'tenant: string' \
  -H 'Authorization: API_KEY'

```

```javascript
var headers = {
  'Content-Type':'application/json',
  'Accept':'application/json',
  'store':'string',
  'tenant':'string',
  'Authorization':'API_KEY'

};

$.ajax({
  url: '/management/layout/{type}/menus/{menuUUID}/categories',
  method: 'put',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

```javascript--nodejs
const fetch = require('node-fetch');
const inputBody = 'false';
const headers = {
  'Content-Type':'application/json',
  'Accept':'application/json',
  'store':'string',
  'tenant':'string',
  'Authorization':'API_KEY'

};

fetch('/management/layout/{type}/menus/{menuUUID}/categories',
{
  method: 'PUT',
  body: inputBody,
  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json',
  'store': 'string',
  'tenant': 'string',
  'Authorization': 'API_KEY'
}

r = requests.put('/management/layout/{type}/menus/{menuUUID}/categories', params={

}, headers = headers)

print r.json()

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Content-Type' => 'application/json',
  'Accept' => 'application/json',
  'store' => 'string',
  'tenant' => 'string',
  'Authorization' => 'API_KEY'
}

result = RestClient.put '/management/layout/{type}/menus/{menuUUID}/categories',
  params: {
  }, headers: headers

p JSON.parse(result)

```

`PUT /management/layout/{type}/menus/{menuUUID}/categories`

Deep integrations only!

> Body parameter

```json
false
```

<h4 id="add-category-to-layout-parameters">Parameters</h4>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|store|header|string|true|Store UUID|
|tenant|header|string|true|Tenant UUID|
|menuUUID|path|string|true|Menu UUID|
|type|path|string|true|Menu Layout type (kiosk, pos)|

> Example responses

> 200 Response

```json
{
  "payload": [
    {
      "uuid": "string",
      "name": "string",
      "type": "string",
      "sortOrder": 0
    }
  ]
}
```

<h4 id="add-category-to-layout-responses">Responses</h4>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|none|[LayoutMenuCategories](#schemalayoutmenucategories)|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|none|[BadRequestError](#schemabadrequesterror)|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|none|[UnauthorizedError](#schemaunauthorizederror)|
|403|[Forbidden](https://tools.ietf.org/html/rfc7231#section-6.5.3)|none|[ForbiddenError](#schemaforbiddenerror)|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|none|[InternalServerError](#schemainternalservererror)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
bearer ( Scopes: ADMINISTRATOR )
</aside>

### Get Category

<a id="opIdGet Category"></a>

> Code samples

```shell
# You can also use wget
curl -X GET /management/layout/{type}/menus/{menuUUID}/categories/{categoryUUID} \
  -H 'Accept: application/json' \
  -H 'store: string' \
  -H 'Authorization: API_KEY'

```

```javascript
var headers = {
  'Accept':'application/json',
  'store':'string',
  'Authorization':'API_KEY'

};

$.ajax({
  url: '/management/layout/{type}/menus/{menuUUID}/categories/{categoryUUID}',
  method: 'get',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

```javascript--nodejs
const fetch = require('node-fetch');

const headers = {
  'Accept':'application/json',
  'store':'string',
  'Authorization':'API_KEY'

};

fetch('/management/layout/{type}/menus/{menuUUID}/categories/{categoryUUID}',
{
  method: 'GET',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```python
import requests
headers = {
  'Accept': 'application/json',
  'store': 'string',
  'Authorization': 'API_KEY'
}

r = requests.get('/management/layout/{type}/menus/{menuUUID}/categories/{categoryUUID}', params={

}, headers = headers)

print r.json()

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json',
  'store' => 'string',
  'Authorization' => 'API_KEY'
}

result = RestClient.get '/management/layout/{type}/menus/{menuUUID}/categories/{categoryUUID}',
  params: {
  }, headers: headers

p JSON.parse(result)

```

`GET /management/layout/{type}/menus/{menuUUID}/categories/{categoryUUID}`

Deep integrations only! Get category Bundles and sub-categories.

<h4 id="get-category-parameters">Parameters</h4>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|store|header|string|true|Store UUID|
|categoryUUID|path|string|true|Category UUID|
|menuUUID|path|string|true|Menu UUID|
|type|path|string|true|Menu Layout type (kiosk, pos)|

> Example responses

> 200 Response

```json
{
  "payload": {
    "bundles": [
      {
        "uuid": "string",
        "itemUUID": "string",
        "name": "string",
        "tags": [
          {
            "name": "string"
          }
        ],
        "isActive": true,
        "isSoldOut": true,
        "sortOrder": 0
      }
    ],
    "categories": [
      {
        "name": "string",
        "uuid": "string",
        "sortOrder": 0,
        "bundles": [
          {
            "uuid": "string",
            "itemUUID": "string",
            "name": "string",
            "tags": [
              {
                "name": "string"
              }
            ],
            "isActive": true,
            "isSoldOut": true,
            "sortOrder": 0
          }
        ]
      }
    ]
  }
}
```

<h4 id="get-category-responses">Responses</h4>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Get a Root Category (Categories and Products)|[RootCategoryProducts](#schemarootcategoryproducts)|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|none|[BadRequestError](#schemabadrequesterror)|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|none|[UnauthorizedError](#schemaunauthorizederror)|
|403|[Forbidden](https://tools.ietf.org/html/rfc7231#section-6.5.3)|none|[ForbiddenError](#schemaforbiddenerror)|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|none|[InternalServerError](#schemainternalservererror)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
bearer ( Scopes: ADMINISTRATOR )
</aside>

### Create Category

<a id="opIdCreate Category"></a>

> Code samples

```shell
# You can also use wget
curl -X POST /management/layout/{type}/menus/{menuUUID}/categories/{categoryUUID} \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json' \
  -H 'store: string' \
  -H 'Authorization: API_KEY'

```

```javascript
var headers = {
  'Content-Type':'application/json',
  'Accept':'application/json',
  'store':'string',
  'Authorization':'API_KEY'

};

$.ajax({
  url: '/management/layout/{type}/menus/{menuUUID}/categories/{categoryUUID}',
  method: 'post',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

```javascript--nodejs
const fetch = require('node-fetch');
const inputBody = '{
  "name": "string",
  "sortOrder": 0
}';
const headers = {
  'Content-Type':'application/json',
  'Accept':'application/json',
  'store':'string',
  'Authorization':'API_KEY'

};

fetch('/management/layout/{type}/menus/{menuUUID}/categories/{categoryUUID}',
{
  method: 'POST',
  body: inputBody,
  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json',
  'store': 'string',
  'Authorization': 'API_KEY'
}

r = requests.post('/management/layout/{type}/menus/{menuUUID}/categories/{categoryUUID}', params={

}, headers = headers)

print r.json()

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Content-Type' => 'application/json',
  'Accept' => 'application/json',
  'store' => 'string',
  'Authorization' => 'API_KEY'
}

result = RestClient.post '/management/layout/{type}/menus/{menuUUID}/categories/{categoryUUID}',
  params: {
  }, headers: headers

p JSON.parse(result)

```

`POST /management/layout/{type}/menus/{menuUUID}/categories/{categoryUUID}`

Deep integrations only! Get a new category with a parent.

> Body parameter

```json
{
  "name": "string",
  "sortOrder": 0
}
```

<h4 id="create-category-parameters">Parameters</h4>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|store|header|string|true|External Store UUID (876b34ad-45654-4ds7-cdd8-bfc47686d999)|
|body|body|[CategoryDto](#schemacategorydto)|true|none|
|categoryUUID|path|string|true|Category UUID|
|menuUUID|path|string|true|Menu UUID|
|type|path|string|true|Menu Layout type (kiosk, pos)|

> Example responses

> 200 Response

```json
{
  "payload": {
    "name": "string",
    "uuid": "string",
    "sortOrder": 0
  }
}
```

<h4 id="create-category-responses">Responses</h4>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Category|[Category](#schemacategory)|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|none|[BadRequestError](#schemabadrequesterror)|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|none|[UnauthorizedError](#schemaunauthorizederror)|
|403|[Forbidden](https://tools.ietf.org/html/rfc7231#section-6.5.3)|none|[ForbiddenError](#schemaforbiddenerror)|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|none|[InternalServerError](#schemainternalservererror)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
bearer ( Scopes: ADMINISTRATOR )
</aside>

### Update Category

<a id="opIdUpdate Category"></a>

> Code samples

```shell
# You can also use wget
curl -X PUT /management/layout/{type}/menus/{menuUUID}/categories/{categoryUUID} \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json' \
  -H 'store: string' \
  -H 'Authorization: API_KEY'

```

```javascript
var headers = {
  'Content-Type':'application/json',
  'Accept':'application/json',
  'store':'string',
  'Authorization':'API_KEY'

};

$.ajax({
  url: '/management/layout/{type}/menus/{menuUUID}/categories/{categoryUUID}',
  method: 'put',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

```javascript--nodejs
const fetch = require('node-fetch');
const inputBody = '{
  "name": "string",
  "sortOrder": 0
}';
const headers = {
  'Content-Type':'application/json',
  'Accept':'application/json',
  'store':'string',
  'Authorization':'API_KEY'

};

fetch('/management/layout/{type}/menus/{menuUUID}/categories/{categoryUUID}',
{
  method: 'PUT',
  body: inputBody,
  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json',
  'store': 'string',
  'Authorization': 'API_KEY'
}

r = requests.put('/management/layout/{type}/menus/{menuUUID}/categories/{categoryUUID}', params={

}, headers = headers)

print r.json()

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Content-Type' => 'application/json',
  'Accept' => 'application/json',
  'store' => 'string',
  'Authorization' => 'API_KEY'
}

result = RestClient.put '/management/layout/{type}/menus/{menuUUID}/categories/{categoryUUID}',
  params: {
  }, headers: headers

p JSON.parse(result)

```

`PUT /management/layout/{type}/menus/{menuUUID}/categories/{categoryUUID}`

Deep integrations only!

> Body parameter

```json
{
  "name": "string",
  "sortOrder": 0
}
```

<h4 id="update-category-parameters">Parameters</h4>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|store|header|string|true|Store UUID|
|body|body|[CategoryDto](#schemacategorydto)|true|none|
|categoryUUID|path|string|true|Category UUID|
|menuUUID|path|string|true|Menu UUID|
|type|path|string|true|Menu Layout type (kiosk, pos)|

> Example responses

> 200 Response

```json
{
  "payload": {
    "name": "string",
    "uuid": "string",
    "sortOrder": 0
  }
}
```

<h4 id="update-category-responses">Responses</h4>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Category|[Category](#schemacategory)|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|none|[BadRequestError](#schemabadrequesterror)|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|none|[UnauthorizedError](#schemaunauthorizederror)|
|403|[Forbidden](https://tools.ietf.org/html/rfc7231#section-6.5.3)|none|[ForbiddenError](#schemaforbiddenerror)|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|none|[InternalServerError](#schemainternalservererror)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
bearer ( Scopes: ADMINISTRATOR )
</aside>

### Delete Category

<a id="opIdDelete Category"></a>

> Code samples

```shell
# You can also use wget
curl -X DELETE /management/layout/{type}/menus/{menuUUID}/categories/{categoryUUID} \
  -H 'Accept: application/json' \
  -H 'store: string' \
  -H 'Authorization: API_KEY'

```

```javascript
var headers = {
  'Accept':'application/json',
  'store':'string',
  'Authorization':'API_KEY'

};

$.ajax({
  url: '/management/layout/{type}/menus/{menuUUID}/categories/{categoryUUID}',
  method: 'delete',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

```javascript--nodejs
const fetch = require('node-fetch');

const headers = {
  'Accept':'application/json',
  'store':'string',
  'Authorization':'API_KEY'

};

fetch('/management/layout/{type}/menus/{menuUUID}/categories/{categoryUUID}',
{
  method: 'DELETE',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```python
import requests
headers = {
  'Accept': 'application/json',
  'store': 'string',
  'Authorization': 'API_KEY'
}

r = requests.delete('/management/layout/{type}/menus/{menuUUID}/categories/{categoryUUID}', params={

}, headers = headers)

print r.json()

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json',
  'store' => 'string',
  'Authorization' => 'API_KEY'
}

result = RestClient.delete '/management/layout/{type}/menus/{menuUUID}/categories/{categoryUUID}',
  params: {
  }, headers: headers

p JSON.parse(result)

```

`DELETE /management/layout/{type}/menus/{menuUUID}/categories/{categoryUUID}`

Deep integrations only!

<h4 id="delete-category-parameters">Parameters</h4>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|store|header|string|true|External Store UUID (876b34ad-45654-4ds7-cdd8-bfc47686d999)|
|categoryUUID|path|string|true|Category UUID|
|menuUUID|path|string|true|Menu UUID|
|type|path|string|true|Menu Layout type (kiosk, pos)|

> Example responses

> 400 Response

```json
{
  "statusCode": 0,
  "message": "string"
}
```

<h4 id="delete-category-responses">Responses</h4>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|204|[No Content](https://tools.ietf.org/html/rfc7231#section-6.3.5)|No content|None|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|none|[BadRequestError](#schemabadrequesterror)|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|none|[UnauthorizedError](#schemaunauthorizederror)|
|403|[Forbidden](https://tools.ietf.org/html/rfc7231#section-6.5.3)|none|[ForbiddenError](#schemaforbiddenerror)|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|none|[InternalServerError](#schemainternalservererror)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
bearer ( Scopes: ADMINISTRATOR )
</aside>

### Delete Category Bundles

<a id="opIdDelete Category Bundles"></a>

> Code samples

```shell
# You can also use wget
curl -X GET /management/layout/{type}/menus/{menuUUID}/categories/{categoryUUID}/products \
  -H 'Accept: application/json' \
  -H 'store: string' \
  -H 'Authorization: API_KEY'

```

```javascript
var headers = {
  'Accept':'application/json',
  'store':'string',
  'Authorization':'API_KEY'

};

$.ajax({
  url: '/management/layout/{type}/menus/{menuUUID}/categories/{categoryUUID}/products',
  method: 'get',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

```javascript--nodejs
const fetch = require('node-fetch');

const headers = {
  'Accept':'application/json',
  'store':'string',
  'Authorization':'API_KEY'

};

fetch('/management/layout/{type}/menus/{menuUUID}/categories/{categoryUUID}/products',
{
  method: 'GET',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```python
import requests
headers = {
  'Accept': 'application/json',
  'store': 'string',
  'Authorization': 'API_KEY'
}

r = requests.get('/management/layout/{type}/menus/{menuUUID}/categories/{categoryUUID}/products', params={

}, headers = headers)

print r.json()

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json',
  'store' => 'string',
  'Authorization' => 'API_KEY'
}

result = RestClient.get '/management/layout/{type}/menus/{menuUUID}/categories/{categoryUUID}/products',
  params: {
  }, headers: headers

p JSON.parse(result)

```

`GET /management/layout/{type}/menus/{menuUUID}/categories/{categoryUUID}/products`

Deep integrations only! Get a list of Bundles (meals or items) in category

<h4 id="delete-category-bundles-parameters">Parameters</h4>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|store|header|string|true|External Store UUID (876b34ad-45654-4ds7-cdd8-bfc47686d999)|
|limit|query|number|false|Limit of items per page|
|page|query|number|false|Page number|
|tags|query|array[string]|false|Tags uuids|
|search|query|string|false|Search a product by name|
|sort|query|array[string]|false|Sort: ?sort[name] = desc&sort[type] = asc|
|categoryUUID|path|string|true|Category UUID|
|menuUUID|path|string|true|Menu UUID|
|type|path|string|true|Menu Layout type (kiosk, pos)|

> Example responses

> 200 Response

```json
{
  "meta": {
    "page": 0,
    "limit": 0,
    "pageCount": 0,
    "totalCount": 0
  },
  "payload": [
    {
      "uuid": "string",
      "name": "string",
      "tags": [
        {
          "name": "string"
        }
      ],
      "isActive": true,
      "isSoldout": true,
      "type": "string"
    }
  ]
}
```

<h4 id="delete-category-bundles-responses">Responses</h4>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|none|[CategoryProducts](#schemacategoryproducts)|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|none|[BadRequestError](#schemabadrequesterror)|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|none|[UnauthorizedError](#schemaunauthorizederror)|
|403|[Forbidden](https://tools.ietf.org/html/rfc7231#section-6.5.3)|none|[ForbiddenError](#schemaforbiddenerror)|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|none|[InternalServerError](#schemainternalservererror)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
bearer ( Scopes: ADMINISTRATOR )
</aside>

### Add Product in Category

<a id="opIdAdd Product in Category"></a>

> Code samples

```shell
# You can also use wget
curl -X POST /management/layout/{type}/menus/{menuUUID}/categories/{categoryUUID}/products \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json' \
  -H 'store: string' \
  -H 'Authorization: API_KEY'

```

```javascript
var headers = {
  'Content-Type':'application/json',
  'Accept':'application/json',
  'store':'string',
  'Authorization':'API_KEY'

};

$.ajax({
  url: '/management/layout/{type}/menus/{menuUUID}/categories/{categoryUUID}/products',
  method: 'post',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

```javascript--nodejs
const fetch = require('node-fetch');
const inputBody = '{
  "products": [
    {
      "uuid": "string",
      "type": "string"
    }
  ]
}';
const headers = {
  'Content-Type':'application/json',
  'Accept':'application/json',
  'store':'string',
  'Authorization':'API_KEY'

};

fetch('/management/layout/{type}/menus/{menuUUID}/categories/{categoryUUID}/products',
{
  method: 'POST',
  body: inputBody,
  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json',
  'store': 'string',
  'Authorization': 'API_KEY'
}

r = requests.post('/management/layout/{type}/menus/{menuUUID}/categories/{categoryUUID}/products', params={

}, headers = headers)

print r.json()

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Content-Type' => 'application/json',
  'Accept' => 'application/json',
  'store' => 'string',
  'Authorization' => 'API_KEY'
}

result = RestClient.post '/management/layout/{type}/menus/{menuUUID}/categories/{categoryUUID}/products',
  params: {
  }, headers: headers

p JSON.parse(result)

```

`POST /management/layout/{type}/menus/{menuUUID}/categories/{categoryUUID}/products`

Deep integrations only!

> Body parameter

```json
{
  "products": [
    {
      "uuid": "string",
      "type": "string"
    }
  ]
}
```

<h4 id="add-product-in-category-parameters">Parameters</h4>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|store|header|string|true|External Store UUID (876b34ad-45654-4ds7-cdd8-bfc47686d999)|
|body|body|[CategoryProductsDto](#schemacategoryproductsdto)|true|none|
|categoryUUID|path|string|true|Category UUID|
|menuUUID|path|string|true|Menu UUID|
|type|path|string|true|Menu Layout type (kiosk, pos)|

> Example responses

> 400 Response

```json
{
  "statusCode": 0,
  "message": "string"
}
```

<h4 id="add-product-in-category-responses">Responses</h4>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|204|[No Content](https://tools.ietf.org/html/rfc7231#section-6.3.5)|No Content|None|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|none|[BadRequestError](#schemabadrequesterror)|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|none|[UnauthorizedError](#schemaunauthorizederror)|
|403|[Forbidden](https://tools.ietf.org/html/rfc7231#section-6.5.3)|none|[ForbiddenError](#schemaforbiddenerror)|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|none|[InternalServerError](#schemainternalservererror)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
bearer ( Scopes: ADMINISTRATOR )
</aside>

### Reorder Bundles in Category

<a id="opIdReorder Bundles in Category"></a>

> Code samples

```shell
# You can also use wget
curl -X PATCH /management/layout/{type}/menus/{menuUUID}/categories/{categoryUUID}/products/reordering \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json' \
  -H 'store: string' \
  -H 'Authorization: API_KEY'

```

```javascript
var headers = {
  'Content-Type':'application/json',
  'Accept':'application/json',
  'store':'string',
  'Authorization':'API_KEY'

};

$.ajax({
  url: '/management/layout/{type}/menus/{menuUUID}/categories/{categoryUUID}/products/reordering',
  method: 'patch',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

```javascript--nodejs
const fetch = require('node-fetch');
const inputBody = '{
  "products": [
    {
      "uuid": "string",
      "sortOrder": 0
    }
  ]
}';
const headers = {
  'Content-Type':'application/json',
  'Accept':'application/json',
  'store':'string',
  'Authorization':'API_KEY'

};

fetch('/management/layout/{type}/menus/{menuUUID}/categories/{categoryUUID}/products/reordering',
{
  method: 'PATCH',
  body: inputBody,
  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json',
  'store': 'string',
  'Authorization': 'API_KEY'
}

r = requests.patch('/management/layout/{type}/menus/{menuUUID}/categories/{categoryUUID}/products/reordering', params={

}, headers = headers)

print r.json()

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Content-Type' => 'application/json',
  'Accept' => 'application/json',
  'store' => 'string',
  'Authorization' => 'API_KEY'
}

result = RestClient.patch '/management/layout/{type}/menus/{menuUUID}/categories/{categoryUUID}/products/reordering',
  params: {
  }, headers: headers

p JSON.parse(result)

```

`PATCH /management/layout/{type}/menus/{menuUUID}/categories/{categoryUUID}/products/reordering`

Deep integrations only!

> Body parameter

```json
{
  "products": [
    {
      "uuid": "string",
      "sortOrder": 0
    }
  ]
}
```

<h4 id="reorder-bundles-in-category-parameters">Parameters</h4>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|store|header|string|true|External Store UUID (876b34ad-45654-4ds7-cdd8-bfc47686d999)|
|body|body|[ReorderCategoryBundlesDto](#schemareordercategorybundlesdto)|true|none|
|categoryUUID|path|string|true|Category UUID|
|menuUUID|path|string|true|Menu UUID|
|type|path|string|true|Menu Layout type (kiosk, pos)|

> Example responses

> 400 Response

```json
{
  "statusCode": 0,
  "message": "string"
}
```

<h4 id="reorder-bundles-in-category-responses">Responses</h4>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|204|[No Content](https://tools.ietf.org/html/rfc7231#section-6.3.5)|No Content|None|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|none|[BadRequestError](#schemabadrequesterror)|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|none|[UnauthorizedError](#schemaunauthorizederror)|
|403|[Forbidden](https://tools.ietf.org/html/rfc7231#section-6.5.3)|none|[ForbiddenError](#schemaforbiddenerror)|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|none|[InternalServerError](#schemainternalservererror)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
bearer ( Scopes: ADMINISTRATOR )
</aside>

### Remove Bundles from Category

<a id="opIdRemove Bundles from Category"></a>

> Code samples

```shell
# You can also use wget
curl -X DELETE /management/layout/{type}/menus/{menuUUID}/categories/{categoryUUID}/products/{bundleUUID} \
  -H 'Accept: application/json' \
  -H 'store: string' \
  -H 'Authorization: API_KEY'

```

```javascript
var headers = {
  'Accept':'application/json',
  'store':'string',
  'Authorization':'API_KEY'

};

$.ajax({
  url: '/management/layout/{type}/menus/{menuUUID}/categories/{categoryUUID}/products/{bundleUUID}',
  method: 'delete',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

```javascript--nodejs
const fetch = require('node-fetch');

const headers = {
  'Accept':'application/json',
  'store':'string',
  'Authorization':'API_KEY'

};

fetch('/management/layout/{type}/menus/{menuUUID}/categories/{categoryUUID}/products/{bundleUUID}',
{
  method: 'DELETE',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```python
import requests
headers = {
  'Accept': 'application/json',
  'store': 'string',
  'Authorization': 'API_KEY'
}

r = requests.delete('/management/layout/{type}/menus/{menuUUID}/categories/{categoryUUID}/products/{bundleUUID}', params={

}, headers = headers)

print r.json()

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json',
  'store' => 'string',
  'Authorization' => 'API_KEY'
}

result = RestClient.delete '/management/layout/{type}/menus/{menuUUID}/categories/{categoryUUID}/products/{bundleUUID}',
  params: {
  }, headers: headers

p JSON.parse(result)

```

`DELETE /management/layout/{type}/menus/{menuUUID}/categories/{categoryUUID}/products/{bundleUUID}`

Deep integrations only!

<h4 id="remove-bundles-from-category-parameters">Parameters</h4>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|store|header|string|true|External Store UUID (876b34ad-45654-4ds7-cdd8-bfc47686d999)|
|bundleUUID|path|string|true|Bundle UUID|
|categoryUUID|path|string|true|Category UUID|
|menuUUID|path|string|true|Menu UUID|
|type|path|string|true|Menu Layout type (kiosk, pos)|

> Example responses

> 400 Response

```json
{
  "statusCode": 0,
  "message": "string"
}
```

<h4 id="remove-bundles-from-category-responses">Responses</h4>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|204|[No Content](https://tools.ietf.org/html/rfc7231#section-6.3.5)|No content|None|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|none|[BadRequestError](#schemabadrequesterror)|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|none|[UnauthorizedError](#schemaunauthorizederror)|
|403|[Forbidden](https://tools.ietf.org/html/rfc7231#section-6.5.3)|none|[ForbiddenError](#schemaforbiddenerror)|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|none|[InternalServerError](#schemainternalservererror)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
bearer ( Scopes: ADMINISTRATOR )
</aside>

### Reorder Categories

<a id="opIdReorder Categories"></a>

> Code samples

```shell
# You can also use wget
curl -X PATCH /management/layout/{type}/menus/{menuUUID}/categories/{categoryUUID}/reordering \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json' \
  -H 'store: string' \
  -H 'Authorization: API_KEY'

```

```javascript
var headers = {
  'Content-Type':'application/json',
  'Accept':'application/json',
  'store':'string',
  'Authorization':'API_KEY'

};

$.ajax({
  url: '/management/layout/{type}/menus/{menuUUID}/categories/{categoryUUID}/reordering',
  method: 'patch',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

```javascript--nodejs
const fetch = require('node-fetch');
const inputBody = '{
  "categories": [
    {
      "uuid": "string",
      "sortOrder": 0
    }
  ]
}';
const headers = {
  'Content-Type':'application/json',
  'Accept':'application/json',
  'store':'string',
  'Authorization':'API_KEY'

};

fetch('/management/layout/{type}/menus/{menuUUID}/categories/{categoryUUID}/reordering',
{
  method: 'PATCH',
  body: inputBody,
  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json',
  'store': 'string',
  'Authorization': 'API_KEY'
}

r = requests.patch('/management/layout/{type}/menus/{menuUUID}/categories/{categoryUUID}/reordering', params={

}, headers = headers)

print r.json()

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Content-Type' => 'application/json',
  'Accept' => 'application/json',
  'store' => 'string',
  'Authorization' => 'API_KEY'
}

result = RestClient.patch '/management/layout/{type}/menus/{menuUUID}/categories/{categoryUUID}/reordering',
  params: {
  }, headers: headers

p JSON.parse(result)

```

`PATCH /management/layout/{type}/menus/{menuUUID}/categories/{categoryUUID}/reordering`

Deep integrations only!

> Body parameter

```json
{
  "categories": [
    {
      "uuid": "string",
      "sortOrder": 0
    }
  ]
}
```

<h4 id="reorder-categories-parameters">Parameters</h4>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|store|header|string|true|External Store UUID (876b34ad-45654-4ds7-cdd8-bfc47686d999)|
|body|body|[ReorderCategoriesDto](#schemareordercategoriesdto)|true|none|
|categoryUUID|path|string|true|Category UUID|
|menuUUID|path|string|true|Menu UUID|
|type|path|string|true|Menu Layout type (kiosk, pos)|

> Example responses

> 400 Response

```json
{
  "statusCode": 0,
  "message": "string"
}
```

<h4 id="reorder-categories-responses">Responses</h4>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|204|[No Content](https://tools.ietf.org/html/rfc7231#section-6.3.5)|No content|None|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|none|[BadRequestError](#schemabadrequesterror)|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|none|[UnauthorizedError](#schemaunauthorizederror)|
|403|[Forbidden](https://tools.ietf.org/html/rfc7231#section-6.5.3)|none|[ForbiddenError](#schemaforbiddenerror)|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|none|[InternalServerError](#schemainternalservererror)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
bearer ( Scopes: ADMINISTRATOR )
</aside>

### Move Category into another cateogry

<a id="opIdMove Category into another cateogry"></a>

> Code samples

```shell
# You can also use wget
curl -X PUT /management/layout/{type}/menus/{menuUUID}/categories/{fromCategoryUUID}/move/{toCategoryUUID} \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json' \
  -H 'store: string' \
  -H 'Authorization: API_KEY'

```

```javascript
var headers = {
  'Content-Type':'application/json',
  'Accept':'application/json',
  'store':'string',
  'Authorization':'API_KEY'

};

$.ajax({
  url: '/management/layout/{type}/menus/{menuUUID}/categories/{fromCategoryUUID}/move/{toCategoryUUID}',
  method: 'put',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

```javascript--nodejs
const fetch = require('node-fetch');
const inputBody = '{
  "uuid": "string",
  "name": "string",
  "sortOrder": 0
}';
const headers = {
  'Content-Type':'application/json',
  'Accept':'application/json',
  'store':'string',
  'Authorization':'API_KEY'

};

fetch('/management/layout/{type}/menus/{menuUUID}/categories/{fromCategoryUUID}/move/{toCategoryUUID}',
{
  method: 'PUT',
  body: inputBody,
  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json',
  'store': 'string',
  'Authorization': 'API_KEY'
}

r = requests.put('/management/layout/{type}/menus/{menuUUID}/categories/{fromCategoryUUID}/move/{toCategoryUUID}', params={

}, headers = headers)

print r.json()

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Content-Type' => 'application/json',
  'Accept' => 'application/json',
  'store' => 'string',
  'Authorization' => 'API_KEY'
}

result = RestClient.put '/management/layout/{type}/menus/{menuUUID}/categories/{fromCategoryUUID}/move/{toCategoryUUID}',
  params: {
  }, headers: headers

p JSON.parse(result)

```

`PUT /management/layout/{type}/menus/{menuUUID}/categories/{fromCategoryUUID}/move/{toCategoryUUID}`

Deep integrations only!

> Body parameter

```json
{
  "uuid": "string",
  "name": "string",
  "sortOrder": 0
}
```

<h4 id="move-category-into-another-cateogry-parameters">Parameters</h4>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|store|header|string|true|External Store UUID (876b34ad-45654-4ds7-cdd8-bfc47686d999)|
|body|body|[MoveCategoryDto](#schemamovecategorydto)|true|none|
|toCategoryUUID|path|string|true|To Category UUID|
|fromCategoryUUID|path|string|true|From Category UUID|
|menuUUID|path|string|true|Menu UUID|
|type|path|string|true|Menu Layout type (kiosk, pos)|

> Example responses

> 400 Response

```json
{
  "statusCode": 0,
  "message": "string"
}
```

<h4 id="move-category-into-another-cateogry-responses">Responses</h4>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|204|[No Content](https://tools.ietf.org/html/rfc7231#section-6.3.5)|No content|None|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|none|[BadRequestError](#schemabadrequesterror)|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|none|[UnauthorizedError](#schemaunauthorizederror)|
|403|[Forbidden](https://tools.ietf.org/html/rfc7231#section-6.5.3)|none|[ForbiddenError](#schemaforbiddenerror)|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|none|[InternalServerError](#schemainternalservererror)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
bearer ( Scopes: ADMINISTRATOR )
</aside>

### Move Bundle into another cateogry

<a id="opIdMove Bundle into another cateogry"></a>

> Code samples

```shell
# You can also use wget
curl -X PUT /management/layout/{type}/menus/{menuUUID}/categories/{fromCategoryUUID}/products/move/{toCategoryUUID} \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json' \
  -H 'store: string' \
  -H 'Authorization: API_KEY'

```

```javascript
var headers = {
  'Content-Type':'application/json',
  'Accept':'application/json',
  'store':'string',
  'Authorization':'API_KEY'

};

$.ajax({
  url: '/management/layout/{type}/menus/{menuUUID}/categories/{fromCategoryUUID}/products/move/{toCategoryUUID}',
  method: 'put',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

```javascript--nodejs
const fetch = require('node-fetch');
const inputBody = '{
  "products": [
    {
      "uuid": "string",
      "type": "string"
    }
  ]
}';
const headers = {
  'Content-Type':'application/json',
  'Accept':'application/json',
  'store':'string',
  'Authorization':'API_KEY'

};

fetch('/management/layout/{type}/menus/{menuUUID}/categories/{fromCategoryUUID}/products/move/{toCategoryUUID}',
{
  method: 'PUT',
  body: inputBody,
  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json',
  'store': 'string',
  'Authorization': 'API_KEY'
}

r = requests.put('/management/layout/{type}/menus/{menuUUID}/categories/{fromCategoryUUID}/products/move/{toCategoryUUID}', params={

}, headers = headers)

print r.json()

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Content-Type' => 'application/json',
  'Accept' => 'application/json',
  'store' => 'string',
  'Authorization' => 'API_KEY'
}

result = RestClient.put '/management/layout/{type}/menus/{menuUUID}/categories/{fromCategoryUUID}/products/move/{toCategoryUUID}',
  params: {
  }, headers: headers

p JSON.parse(result)

```

`PUT /management/layout/{type}/menus/{menuUUID}/categories/{fromCategoryUUID}/products/move/{toCategoryUUID}`

Deep integrations only!

> Body parameter

```json
{
  "products": [
    {
      "uuid": "string",
      "type": "string"
    }
  ]
}
```

<h4 id="move-bundle-into-another-cateogry-parameters">Parameters</h4>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|store|header|string|true|Store UUID|
|body|body|[MoveBundleDto](#schemamovebundledto)|true|none|
|toCategoryUUID|path|string|true|To Category UUID|
|fromCategoryUUID|path|string|true|From Category UUID|
|menuUUID|path|string|true|Menu UUID|
|type|path|string|true|Menu Layout type (kiosk, pos)|

> Example responses

> 400 Response

```json
{
  "statusCode": 0,
  "message": "string"
}
```

<h4 id="move-bundle-into-another-cateogry-responses">Responses</h4>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|204|[No Content](https://tools.ietf.org/html/rfc7231#section-6.3.5)|No content|None|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|none|[BadRequestError](#schemabadrequesterror)|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|none|[UnauthorizedError](#schemaunauthorizederror)|
|403|[Forbidden](https://tools.ietf.org/html/rfc7231#section-6.5.3)|none|[ForbiddenError](#schemaforbiddenerror)|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|none|[InternalServerError](#schemainternalservererror)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
bearer ( Scopes: ADMINISTRATOR )
</aside>

<h2 id="catalog-service-menu">menu</h2>

### Get Menu

<a id="opIdGet Menu"></a>

> Code samples

```shell
# You can also use wget
curl -X GET /menu \
  -H 'Accept: application/json' \
  -H 'store: string' \
  -H 'tenant: string' \
  -H 'x-requested-from: string'

```

```javascript
var headers = {
  'Accept':'application/json',
  'store':'string',
  'tenant':'string',
  'x-requested-from':'string'

};

$.ajax({
  url: '/menu',
  method: 'get',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

```javascript--nodejs
const fetch = require('node-fetch');

const headers = {
  'Accept':'application/json',
  'store':'string',
  'tenant':'string',
  'x-requested-from':'string'

};

fetch('/menu',
{
  method: 'GET',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```python
import requests
headers = {
  'Accept': 'application/json',
  'store': 'string',
  'tenant': 'string',
  'x-requested-from': 'string'
}

r = requests.get('/menu', params={

}, headers = headers)

print r.json()

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json',
  'store' => 'string',
  'tenant' => 'string',
  'x-requested-from' => 'string'
}

result = RestClient.get '/menu',
  params: {
  }, headers: headers

p JSON.parse(result)

```

`GET /menu`

Get a hierarchy of Categories for the given menu. Bundles (meals or items) in each Category are also retrieved.

<h4 id="get-menu-parameters">Parameters</h4>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|store|header|string|true|External Store UUID (876b34ad-45654-4ds7-cdd8-bfc47686d999)|
|tenant|header|string|true|External Tenant UUID (832b34ad-2608-4cc7-bee8-bfc47686d801)|
|x-requested-from|header|string|true|Request come from (kiosk, pos, online)|

> Example responses

> 200 Response

```json
{
  "payload": [
    {
      "name": "string",
      "uuid": "string",
      "sortOrder": 0,
      "currentDayWorkHours": {
        "weekday": 0,
        "from": "string",
        "to": "string"
      },
      "categories": [
        {
          "name": "string",
          "uuid": "string",
          "sortOrder": 0,
          "type": "string"
        }
      ]
    }
  ]
}
```

> 400 Response

```json
{
  "statusCode": 400,
  "message": "Please select store first!"
}
```

> 403 Response

```json
{
  "statusCode": 403,
  "message": "Forbidden resource"
}
```

> 500 Response

```json
{
  "statusCode": 500,
  "message": "Internal server error!"
}
```

<h4 id="get-menu-responses">Responses</h4>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|none|[MenuModel](#schemamenumodel)|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|none|[BadRequestError](#schemabadrequesterror)|
|403|[Forbidden](https://tools.ietf.org/html/rfc7231#section-6.5.3)|none|[ForbiddenError](#schemaforbiddenerror)|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|none|[InternalServerError](#schemainternalservererror)|

<aside class="success">
This operation does not require authentication
</aside>

<h2 id="catalog-service-categories">categories</h2>

### Get Category Bundles

<a id="opIdGet Category Bundles"></a>

> Code samples

```shell
# You can also use wget
curl -X GET /categories/{categoryUUID}/bundles \
  -H 'Accept: application/json' \
  -H 'menu: string' \
  -H 'store: string' \
  -H 'tenant: string' \
  -H 'x-requested-from: string'

```

```javascript
var headers = {
  'Accept':'application/json',
  'menu':'string',
  'store':'string',
  'tenant':'string',
  'x-requested-from':'string'

};

$.ajax({
  url: '/categories/{categoryUUID}/bundles',
  method: 'get',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

```javascript--nodejs
const fetch = require('node-fetch');

const headers = {
  'Accept':'application/json',
  'menu':'string',
  'store':'string',
  'tenant':'string',
  'x-requested-from':'string'

};

fetch('/categories/{categoryUUID}/bundles',
{
  method: 'GET',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```python
import requests
headers = {
  'Accept': 'application/json',
  'menu': 'string',
  'store': 'string',
  'tenant': 'string',
  'x-requested-from': 'string'
}

r = requests.get('/categories/{categoryUUID}/bundles', params={

}, headers = headers)

print r.json()

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json',
  'menu' => 'string',
  'store' => 'string',
  'tenant' => 'string',
  'x-requested-from' => 'string'
}

result = RestClient.get '/categories/{categoryUUID}/bundles',
  params: {
  }, headers: headers

p JSON.parse(result)

```

`GET /categories/{categoryUUID}/bundles`

Retrieve all bundles (meals and items) in a given menu category

<h4 id="get-category-bundles-parameters">Parameters</h4>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|menu|header|string|true|Menu UUID|
|store|header|string|true|External Store UUID (876b34ad-45654-4ds7-cdd8-bfc47686d999)|
|tenant|header|string|true|External Tenant UUID (832b34ad-2608-4cc7-bee8-bfc47686d801)|
|x-requested-from|header|string|true|Request come from (kiosk, pos, online)|
|categoryUUID|path|string|true|Category UUID|

> Example responses

> 200 Response

```json
{
  "payload": {
    "bundles": [
      {
        "name": "MEXICAN POACHED",
        "description": "mexiacn poached description",
        "onlineDescription": "mexiacn poached description",
        "uuid": "sdwe34434dew34d3445r",
        "taxExempt": null,
        "vatRateEatIn": 1,
        "vatRateTakeaway": 1,
        "price": 3.4,
        "priceFrom": 2,
        "priceEatInFrom": 2,
        "sortOrder": 5,
        "upsellText": "upsellText",
        "upsellItemTypeUUID": null,
        "rootCategory": {
          "name": "Main",
          "uuid": "564564hgfhfghfghf"
        },
        "category": {
          "name": "Main",
          "uuid": "564564hgfhfghfghf"
        },
        "hasModifiers": false,
        "isGrouped": false,
        "diets": [],
        "allergens": [],
        "itemTypes": [
          "uCqDma1SDrde6u67u67pv0xNjyu"
        ],
        "items": [
          {
            "uuid": "fsdfsdhu-602a-4253-af9b-fdgdf5",
            "sortOrder": 0,
            "name": "Egg",
            "taxExempt": null,
            "vatRateEatIn": 2,
            "kitchenZone": null,
            "vatRateTakeaway": 2,
            "price": 45,
            "nutritionalMeta": {
              "calories": 136.5,
              "fats": 2.2,
              "fatSaturates": 0.7,
              "carbs": 0.1,
              "carbsSugar": 0,
              "fibre": 0.1,
              "protein": 29,
              "salt": 0.57,
              "tenAday": 0
            },
            "description": "Est consequatur et consequatur vel dolorem reiciendis doloremque. Sint quas delectus illo architecto. Architecto quibusdam placeat.",
            "onlineDescription": "some online description",
            "diets": [],
            "allergens": [],
            "itemType": {
              "uuid": "uCqDma1SDrde6u67u67pv0xNjyu",
              "name": "Extra",
              "sortOrder": 1,
              "minRestriction": 1,
              "maxRestriction": 5
            },
            "customizations": []
          }
        ]
      }
    ],
    "categories": [
      {
        "uuid": "asdasd345fdsfsd",
        "name": "Meal Category 1",
        "sortOrder": 1,
        "upsellText": "upsellText",
        "upsellItemTypeUUID": null,
        "bundles": [
          {
            "uuid": "sfcsdr533453445",
            "name": "BYO meal",
            "description": null,
            "onlineDescription": "some online description",
            "taxExempt": null,
            "vatRateEatIn": 2,
            "vatRateTakeaway": 2,
            "rootCategory": {
              "name": "Main",
              "uuid": "asdased234234234"
            },
            "hasModifiers": true,
            "isGrouped": false,
            "price": 10,
            "priceFrom": 5,
            "priceEatInFrom": 2,
            "diets": [
              "sdcerf45f45f45",
              "sdcerf45f33f45"
            ],
            "allergens": [
              "sdcerf11f45f45",
              "sdcerf99f45f45"
            ],
            "itemTypes": [
              "s0UrRl39krwrfexvz0tA33FQpjvHU4",
              "uCqDma1SDrdepv0xN6nO"
            ],
            "items": [
              {
                "uuid": "0514be43-4c28-4aff-9e89-cdb4e7e4dab1",
                "sortOrder": 0,
                "name": "Hot Chocolate",
                "taxExempt": null,
                "kitchenZone": {
                  "uuid": "e43-4c28-4aff-9e89-cdb4",
                  "name": "name 1",
                  "slug": "some slug",
                  "sortOrderOnPrint": 1,
                  "capacity": 3
                },
                "vatRateEatIn": 2,
                "vatRateTakeaway": 2,
                "price": 6.95,
                "nutritionalMeta": {
                  "calories": 136.5,
                  "fats": 2.2,
                  "fatSaturates": 0.7,
                  "carbs": 0.1,
                  "carbsSugar": 0,
                  "fibre": 0.1,
                  "protein": 29,
                  "salt": 0.57,
                  "tenAday": 0
                },
                "description": "Est consequatur et consequatur vel dolorem reiciendis doloremque. Sint quas delectus illo architecto. Architecto quibusdam placeat.",
                "onlineDescription": "some online description",
                "itemType": {
                  "uuid": "s0UrRl39krwrfexvz0tA33FQpjvHU4",
                  "name": "Base Full English",
                  "sortOrder": 0,
                  "minRestriction": 1,
                  "maxRestriction": 1
                },
                "diets": [
                  "sdcerf45f45f45",
                  "sdcerf45f33f45"
                ],
                "allergens": [
                  "sdcerf11f45f45",
                  "sdcerf99f45f45"
                ],
                "customizations": [
                  {
                    "type": "radio",
                    "uuid": "a112ad96-2a3d-4bee-8335-8e615a8fd1f5",
                    "text": "size",
                    "variations": [
                      {
                        "step": 0,
                        "value": "12oz",
                        "price": 0,
                        "uuid": "4ba9dad1-ff24-421f-8546-443a71283d35",
                        "type": "radio",
                        "unit": null
                      },
                      {
                        "step": 1,
                        "value": "16oz",
                        "price": 2.7,
                        "uuid": "4483e0fa-7881-4cf0-b2ad-a5a727aba125",
                        "type": "radio",
                        "unit": null
                      }
                    ],
                    "current": 0
                  },
                  {
                    "type": "radio",
                    "uuid": "411308a3-6b38-11e8-8bcc-02f6c2788b90",
                    "text": "milk type",
                    "variations": [
                      {
                        "step": 0,
                        "value": "Whole Milk",
                        "price": 0,
                        "uuid": "990bad22-9b76-4a41-b473-3cf90ff02128",
                        "type": "radio",
                        "unit": null
                      },
                      {
                        "step": 1,
                        "value": "Skimmed Milk",
                        "price": 0,
                        "uuid": "bfbd5f8b-eba5-4b6e-9a47-77d2614677ad",
                        "type": "radio",
                        "unit": null
                      },
                      {
                        "step": 2,
                        "value": "Soy Milk",
                        "price": 0.5,
                        "uuid": "c064445c-3b07-4a0a-afd8-ca2c8e73dbfd",
                        "type": "radio",
                        "unit": null
                      },
                      {
                        "step": 3,
                        "value": "Almond Milk",
                        "price": 0.5,
                        "uuid": "b48135e0-4294-45b4-8c2a-164affbc555d",
                        "type": "radio",
                        "unit": null
                      },
                      {
                        "step": 4,
                        "value": "Coconut Milk",
                        "price": 1,
                        "uuid": "ddcfcff6-6d72-49a7-a52c-8d7e4ae9097e",
                        "type": "radio",
                        "unit": null
                      },
                      {
                        "step": 5,
                        "value": "S Almond Milk",
                        "price": 0.25,
                        "uuid": "74063970-e3d1-4cdf-a1ba-16b8259ec7a3",
                        "type": "radio",
                        "unit": null
                      },
                      {
                        "step": 6,
                        "value": "S Coconut Milk",
                        "price": 0.5,
                        "uuid": "29dc1a1d-8658-4e7e-b549-e18435529c86",
                        "type": "radio",
                        "unit": null
                      }
                    ],
                    "current": null
                  },
                  {
                    "type": "checkbox",
                    "uuid": "74014e2d-6b49-11e8-8bcc-02f6c2788b90",
                    "text": "Extra shot",
                    "variations": [
                      {
                        "step": 0,
                        "value": "Syrup Shot",
                        "price": 0.8,
                        "uuid": "11ed3d3c-d216-4d63-aea1-dd39c7866512",
                        "type": "checkbox",
                        "unit": null
                      },
                      {
                        "step": 1,
                        "value": "Expresso Shot",
                        "price": 0.9,
                        "uuid": "0e193d2e-43c5-45f2-a3f3-c7f3c5293dc5",
                        "type": "checkbox",
                        "unit": null
                      }
                    ],
                    "current": [
                      0
                    ]
                  }
                ]
              },
              {
                "uuid": "88d8140e-602a-4253-af9b-1394bbd45455",
                "sortOrder": 0,
                "name": "Avocado",
                "taxExempt": null,
                "kitchenZone": null,
                "vatRateEatIn": 2,
                "vatRateTakeaway": 2,
                "price": 5,
                "nutritionalMeta": null,
                "description": "Est consequatur et consequatur vel dolorem reiciendis doloremque. Sint quas delectus illo architecto. Architecto quibusdam placeat.",
                "onlineDescription": "some online description",
                "diets": [],
                "allergens": [],
                "itemType": {
                  "uuid": "uCqDma1SDrdepv0xN6nO",
                  "name": "Extra Full english",
                  "sortOrder": 1,
                  "minRestriction": 1,
                  "maxRestriction": 5
                },
                "customizations": [
                  {
                    "type": "radio",
                    "uuid": "a112ad96-2a3d-4bee-8335-8e615a8fd1f5",
                    "text": "size",
                    "variations": [
                      {
                        "step": 0,
                        "value": "12oz",
                        "price": 0,
                        "uuid": "4ba9dad1-ff24-421f-8546-443a71283d35",
                        "type": "radio",
                        "unit": null
                      },
                      {
                        "step": 1,
                        "value": "16oz",
                        "price": 2.7,
                        "uuid": "4483e0fa-7881-4cf0-b2ad-a5a727aba125",
                        "type": "radio",
                        "unit": null
                      }
                    ],
                    "current": 0,
                    "meta": {
                      "text": "size",
                      "defaultValue": "12oz"
                    }
                  },
                  {
                    "type": "radio",
                    "uuid": "411308a3-6b38-11e8-8bcc-02f6c2788b90",
                    "text": "milk type",
                    "variations": [
                      {
                        "step": 0,
                        "value": "Whole Milk",
                        "price": 0,
                        "uuid": "990bad22-9b76-4a41-b473-3cf90ff02128",
                        "type": "radio",
                        "unit": null
                      },
                      {
                        "step": 1,
                        "value": "Skimmed Milk",
                        "price": 0,
                        "uuid": "bfbd5f8b-eba5-4b6e-9a47-77d2614677ad",
                        "type": "radio",
                        "unit": null
                      },
                      {
                        "step": 2,
                        "value": "Soy Milk",
                        "price": 0.5,
                        "uuid": "c064445c-3b07-4a0a-afd8-ca2c8e73dbfd",
                        "type": "radio",
                        "unit": null
                      },
                      {
                        "step": 3,
                        "value": "Almond Milk",
                        "price": 0.5,
                        "uuid": "b48135e0-4294-45b4-8c2a-164affbc555d",
                        "type": "radio",
                        "unit": null
                      },
                      {
                        "step": 4,
                        "value": "Coconut Milk",
                        "price": 1,
                        "uuid": "ddcfcff6-6d72-49a7-a52c-8d7e4ae9097e",
                        "type": "radio",
                        "unit": null
                      },
                      {
                        "step": 5,
                        "value": "S Almond Milk",
                        "price": 0.25,
                        "uuid": "74063970-e3d1-4cdf-a1ba-16b8259ec7a3",
                        "type": "radio",
                        "unit": null
                      },
                      {
                        "step": 6,
                        "value": "S Coconut Milk",
                        "price": 0.5,
                        "uuid": "29dc1a1d-8658-4e7e-b549-e18435529c86",
                        "type": "radio",
                        "unit": null
                      }
                    ],
                    "current": null,
                    "meta": {
                      "text": "milk type"
                    }
                  },
                  {
                    "type": "checkbox",
                    "uuid": "74014e2d-6b49-11e8-8bcc-02f6c2788b90",
                    "text": "Extra shot",
                    "variations": [
                      {
                        "step": 0,
                        "value": "Syrup Shot",
                        "price": 0.8,
                        "uuid": "11ed3d3c-d216-4d63-aea1-dd39c7866512",
                        "type": "checkbox",
                        "unit": null
                      },
                      {
                        "step": 1,
                        "value": "Expresso Shot",
                        "price": 0.9,
                        "uuid": "0e193d2e-43c5-45f2-a3f3-c7f3c5293dc5",
                        "type": "checkbox",
                        "unit": null
                      }
                    ],
                    "current": [
                      0
                    ],
                    "meta": {
                      "text": "Extra shot"
                    }
                  }
                ]
              }
            ]
          }
        ]
      },
      {
        "uuid": "asdasd45345345",
        "name": "Meal Category 2",
        "sortOrder": 2,
        "upsellText": "upsellText",
        "upsellItemTypeUUID": null,
        "bundles": [
          {
            "name": "HAM AND EGG POT",
            "description": "Grass-fed beef ragout with chickpeas",
            "onlineDescription": "some online description",
            "uuid": "sfcsdr533453cj5",
            "taxExempt": null,
            "vatRateEatIn": 2,
            "vatRateTakeaway": 2,
            "price": 2.13,
            "priceFrom": 2,
            "priceEatInFrom": 2,
            "sortOrder": 3,
            "rootCategory": {
              "name": "Main",
              "uuid": "564564hgfhfghfghf"
            },
            "category": {
              "uuid": "asdasd345fdsfsd",
              "name": "Meal Category 2"
            },
            "hasModifiers": false,
            "isGrouped": false,
            "diets": [],
            "allergens": [],
            "itemTypes": [
              "uCqDma1SDrde6u67u67pv0xNjyu"
            ],
            "items": [
              {
                "uuid": "fsdfsdhu-602a-4253-af9b-fdgdf5",
                "sortOrder": 0,
                "name": "Egg",
                "taxExempt": null,
                "vatRateEatIn": 2,
                "kitchenZone": null,
                "vatRateTakeaway": 2,
                "price": 45,
                "nutritionalMeta": {
                  "calories": 136.5,
                  "fats": 2.2,
                  "fatSaturates": 0.7,
                  "carbs": 0.1,
                  "carbsSugar": 0,
                  "fibre": 0.1,
                  "protein": 29,
                  "salt": 0.57,
                  "tenAday": 0
                },
                "description": "Est consequatur et consequatur vel dolorem reiciendis doloremque. Sint quas delectus illo architecto. Architecto quibusdam placeat.",
                "onlineDescription": "some online description",
                "diets": [],
                "allergens": [],
                "itemType": {
                  "uuid": "uCqDma1SDrde6u67u67pv0xNjyu",
                  "name": "Extra",
                  "sortOrder": 1,
                  "minRestriction": 1,
                  "maxRestriction": 5
                },
                "customizations": []
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
  "statusCode": 400,
  "message": "Please select store first!"
}
```

> 403 Response

```json
{
  "statusCode": 403,
  "message": "Forbidden resource"
}
```

> 404 Response

```json
{
  "statusCode": 404,
  "message": "Cannot GET ..."
}
```

> 500 Response

```json
{
  "statusCode": 500,
  "message": "Internal server error!"
}
```

<h4 id="get-category-bundles-responses">Responses</h4>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|none|[CategoryBundlesModel](#schemacategorybundlesmodel)|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|none|[BadRequestError](#schemabadrequesterror)|
|403|[Forbidden](https://tools.ietf.org/html/rfc7231#section-6.5.3)|none|[ForbiddenError](#schemaforbiddenerror)|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|none|[NotFoundError](#schemanotfounderror)|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|none|[InternalServerError](#schemainternalservererror)|

<aside class="success">
This operation does not require authentication
</aside>

### Get Category Breadcrumb

<a id="opIdGet Category Breadcrumb"></a>

> Code samples

```shell
# You can also use wget
curl -X GET /categories/{categoryUUID}/breadcrumb \
  -H 'Accept: application/json'

```

```javascript
var headers = {
  'Accept':'application/json'

};

$.ajax({
  url: '/categories/{categoryUUID}/breadcrumb',
  method: 'get',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

```javascript--nodejs
const fetch = require('node-fetch');

const headers = {
  'Accept':'application/json'

};

fetch('/categories/{categoryUUID}/breadcrumb',
{
  method: 'GET',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.get('/categories/{categoryUUID}/breadcrumb', params={

}, headers = headers)

print r.json()

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json'
}

result = RestClient.get '/categories/{categoryUUID}/breadcrumb',
  params: {
  }, headers: headers

p JSON.parse(result)

```

`GET /categories/{categoryUUID}/breadcrumb`

Deep integrations only! Retrievs breacrumbs information for navigation tree.

<h4 id="get-category-breadcrumb-parameters">Parameters</h4>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|categoryUUID|path|string|true|Category UUID|

> Example responses

> 200 Response

```json
[
  {
    "payload": {
      "name": "string",
      "uuid": "string",
      "sortOrder": 0
    }
  }
]
```

<h4 id="get-category-breadcrumb-responses">Responses</h4>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|none|Inline|

<h4 id="get-category-breadcrumb-responseschema">Response Schema</h4>

Status Code **200**

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|*anonymous*|[[Category](#schemacategory)]|false|none|none|
|» payload|object|true|none|none|
|»» name|string|true|none|none|
|»» uuid|string|true|none|none|
|»» sortOrder|integer|true|none|none|

<aside class="success">
This operation does not require authentication
</aside>

## Schemas

<h3 id="tocScategorybundlesmodel">CategoryBundlesModel</h3>

<a id="schemacategorybundlesmodel"></a>

```json
{
  "payload": {
    "bundles": [
      {
        "uuid": "string",
        "taxExempt": 0,
        "vatRateEatIn": 0,
        "vatRateTakeaway": 0,
        "name": "string",
        "description": "string",
        "onlineDescription": "string",
        "diets": [
          "string"
        ],
        "allergens": [
          "string"
        ],
        "rootCategory": {
          "name": "string",
          "uuid": "string"
        },
        "hasModifiers": true,
        "isGrouped": true,
        "price": 0,
        "priceFrom": 0,
        "priceEatInFrom": 0,
        "itemTypes": [
          "string"
        ],
        "upsellText": "string",
        "upsellItemTypeUUID": "string",
        "items": [
          {
            "uuid": "string",
            "taxExempt": 0,
            "vatRateEatIn": 0,
            "vatRateTakeaway": 0,
            "sortOrder": 0,
            "name": "string",
            "price": 0,
            "description": "string",
            "onlineDescription": "string",
            "kitchenZone": {
              "uuid": "string",
              "name": "string",
              "slug": "string",
              "sortOrderOnPrint": 0,
              "capacity": 0
            },
            "itemType": {
              "uuid": "string",
              "name": "string",
              "sortOrder": 0,
              "minRestriction": 0,
              "maxRestriction": 0
            },
            "customizations": [
              {
                "type": "string",
                "uuid": "string",
                "text": "string",
                "variations": [
                  {
                    "step": 0,
                    "value": "string",
                    "price": 0,
                    "uuid": "string",
                    "type": "string",
                    "unit": {}
                  }
                ],
                "current": "string"
              }
            ]
          }
        ]
      }
    ],
    "categories": [
      {
        "uuid": "string",
        "name": "string",
        "sortOrder": 0,
        "bundles": [
          {
            "uuid": "string",
            "taxExempt": 0,
            "vatRateEatIn": 0,
            "vatRateTakeaway": 0,
            "name": "string",
            "description": "string",
            "onlineDescription": "string",
            "diets": [
              "string"
            ],
            "allergens": [
              "string"
            ],
            "rootCategory": {
              "name": "string",
              "uuid": "string"
            },
            "hasModifiers": true,
            "isGrouped": true,
            "price": 0,
            "priceFrom": 0,
            "priceEatInFrom": 0,
            "itemTypes": [
              "string"
            ],
            "items": [
              {
                "uuid": "string",
                "taxExempt": 0,
                "vatRateEatIn": 0,
                "vatRateTakeaway": 0,
                "sortOrder": 0,
                "name": "string",
                "price": 0,
                "description": "string",
                "onlineDescription": "string",
                "kitchenZone": {
                  "uuid": "string",
                  "name": "string",
                  "slug": "string",
                  "sortOrderOnPrint": 0,
                  "capacity": 0
                },
                "itemType": {
                  "uuid": "string",
                  "name": "string",
                  "sortOrder": 0,
                  "minRestriction": 0,
                  "maxRestriction": 0
                },
                "customizations": [
                  {
                    "type": "string",
                    "uuid": "string",
                    "text": "string",
                    "variations": [],
                    "current": "string"
                  }
                ]
              }
            ]
          }
        ]
      }
    ]
  }
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|payload|object|true|none|none|
|» bundles|[object]|true|none|none|
|»» uuid|string|true|none|none|
|»» taxExempt|number|true|none|none|
|»» vatRateEatIn|number|true|none|none|
|»» vatRateTakeaway|number|true|none|none|
|»» name|string|true|none|none|
|»» description|string|true|none|none|
|»» onlineDescription|string|false|none|none|
|»» diets|[string]|true|none|none|
|»» allergens|[string]|true|none|none|
|»» rootCategory|object|true|none|none|
|»»» name|string|true|none|none|
|»»» uuid|string|true|none|none|
|»» hasModifiers|boolean|true|none|none|
|»» isGrouped|boolean|true|none|none|
|»» price|number|true|none|none|
|»» priceFrom|number|true|none|none|
|»» priceEatInFrom|number|false|none|none|
|»» itemTypes|[string]|true|none|none|
|»» upsellText|string|false|none|none|
|»» upsellItemTypeUUID|string|false|none|none|
|»» items|[object]|true|none|none|
|»»» uuid|string|true|none|none|
|»»» taxExempt|number|true|none|none|
|»»» vatRateEatIn|number|true|none|none|
|»»» vatRateTakeaway|number|true|none|none|
|»»» sortOrder|integer|true|none|none|
|»»» name|string|true|none|none|
|»»» price|number|true|none|none|
|»»» description|string|true|none|none|
|»»» onlineDescription|string|false|none|none|
|»»» kitchenZone|object|false|none|none|
|»»»» uuid|string|true|none|none|
|»»»» name|string|true|none|none|
|»»»» slug|string|true|none|none|
|»»»» sortOrderOnPrint|integer|true|none|none|
|»»»» capacity|integer|true|none|none|
|»»» itemType|object|true|none|none|
|»»»» uuid|string|true|none|none|
|»»»» name|string|true|none|none|
|»»»» sortOrder|integer|true|none|none|
|»»»» minRestriction|integer|true|none|none|
|»»»» maxRestriction|integer|true|none|none|
|»»» customizations|[object]|true|none|none|
|»»»» type|string|true|none|none|
|»»»» uuid|string|true|none|none|
|»»»» text|string|true|none|none|
|»»»» variations|[object]|true|none|none|
|»»»»» step|integer|true|none|none|
|»»»»» value|string|true|none|none|
|»»»»» price|number|true|none|none|
|»»»»» uuid|string|true|none|none|
|»»»»» type|string|true|none|none|
|»»»»» unit|object|false|none|none|
|»»»»»» slug|string|true|none|none|
|»»»»»» name|string|true|none|none|
|»»»»»» value|number|true|none|none|
|»»»»» current|string|true|none|none|
|»»»» categories|[object]|true|none|none|
|»»»»» uuid|string|true|none|none|
|»»»»» name|string|true|none|none|
|»»»»» sortOrder|integer|true|none|none|
|»»»»» bundles|[object]|true|none|none|
|»»»»»» uuid|string|true|none|none|
|»»»»»» taxExempt|number|true|none|none|
|»»»»»» vatRateEatIn|number|true|none|none|
|»»»»»» vatRateTakeaway|number|true|none|none|
|»»»»»» name|string|true|none|none|
|»»»»»» description|string|true|none|none|
|»»»»»» onlineDescription|string|false|none|none|
|»»»»»» diets|[string]|true|none|none|
|»»»»»» allergens|[string]|true|none|none|
|»»»»»» rootCategory|object|true|none|none|
|»»»»»»» name|string|true|none|none|
|»»»»»»» uuid|string|true|none|none|
|»»»»»» hasModifiers|boolean|true|none|none|
|»»»»»» isGrouped|boolean|true|none|none|
|»»»»»» price|number|true|none|none|
|»»»»»» priceFrom|number|true|none|none|
|»»»»»» priceEatInFrom|number|false|none|none|
|»»»»»» itemTypes|[string]|true|none|none|
|»»»»»» items|[object]|true|none|none|
|»»»»»»» uuid|string|true|none|none|
|»»»»»»» taxExempt|number|true|none|none|
|»»»»»»» vatRateEatIn|number|true|none|none|
|»»»»»»» vatRateTakeaway|number|true|none|none|
|»»»»»»» sortOrder|integer|true|none|none|
|»»»»»»» name|string|true|none|none|
|»»»»»»» price|number|true|none|none|
|»»»»»»» description|string|true|none|none|
|»»»»»»» onlineDescription|string|false|none|none|
|»»»»»»» kitchenZone|object|false|none|none|
|»»»»»»»» uuid|string|true|none|none|
|»»»»»»»» name|string|true|none|none|
|»»»»»»»» slug|string|true|none|none|
|»»»»»»»» sortOrderOnPrint|integer|true|none|none|
|»»»»»»»» capacity|integer|true|none|none|
|»»»»»»» itemType|object|true|none|none|
|»»»»»»»» uuid|string|true|none|none|
|»»»»»»»» name|string|true|none|none|
|»»»»»»»» sortOrder|integer|true|none|none|
|»»»»»»»» minRestriction|integer|true|none|none|
|»»»»»»»» maxRestriction|integer|true|none|none|
|»»»»»»» customizations|[object]|true|none|none|
|»»»»»»»» type|string|true|none|none|
|»»»»»»»» uuid|string|true|none|none|
|»»»»»»»» text|string|true|none|none|
|»»»»»»»» variations|[object]|true|none|none|
|»»»»»»»»» step|integer|true|none|none|
|»»»»»»»»» value|string|true|none|none|
|»»»»»»»»» price|number|true|none|none|
|»»»»»»»»» uuid|string|true|none|none|
|»»»»»»»»» type|string|true|none|none|
|»»»»»»»»» unit|object|false|none|none|
|»»»»»»»»»» slug|string|true|none|none|
|»»»»»»»»»» name|string|true|none|none|
|»»»»»»»»»» value|number|true|none|none|
|»»»»»»»»» current|string|true|none|none|

<h3 id="tocSmanagementbundlesmodel">ManagementBundlesModel</h3>

<a id="schemamanagementbundlesmodel"></a>

```json
{
  "meta": {
    "page": 0,
    "limit": 0,
    "pageCount": 0,
    "totalCount": 0
  },
  "payload": [
    {
      "uuid": "string",
      "name": "string",
      "tags": [
        {
          "uuid": "string",
          "name": "string"
        }
      ],
      "type": "CUSTOMISED",
      "status": "string"
    }
  ]
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|meta|object|true|none|none|
|» page|integer|true|none|none|
|» limit|integer|true|none|none|
|» pageCount|integer|true|none|none|
|» totalCount|integer|true|none|none|
|payload|[object]|true|none|none|
|» uuid|string|true|none|none|
|» name|string|true|none|none|
|» tags|[object]|true|none|none|
|»» uuid|string|true|none|none|
|»» name|string|true|none|none|
|» type|string|true|none|none|
|» status|string|true|none|none|

#### Enumerated Values

|Property|Value|
|---|---|
|type|CUSTOMISED|
|type|VIRTUAL|
|type|BUILD_YOUR_OWN|
|type|FIXED_PRICE|

<h3 id="tocSbadrequesterror">BadRequestError</h3>

<a id="schemabadrequesterror"></a>

```json
{
  "statusCode": 0,
  "message": "string"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|statusCode|number|true|none|none|
|message|string|true|none|none|

<h3 id="tocSnotfounderror">NotFoundError</h3>

<a id="schemanotfounderror"></a>

```json
{
  "statusCode": 0,
  "message": "string"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|statusCode|number|true|none|none|
|message|string|true|none|none|

<h3 id="tocSforbiddenerror">ForbiddenError</h3>

<a id="schemaforbiddenerror"></a>

```json
{
  "statusCode": 0,
  "message": "string"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|statusCode|number|true|none|none|
|message|string|true|none|none|

<h3 id="tocSunauthorizederror">UnauthorizedError</h3>

<a id="schemaunauthorizederror"></a>

```json
{
  "statusCode": 0,
  "message": "string"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|statusCode|number|true|none|none|
|message|string|true|none|none|

<h3 id="tocSinternalservererror">InternalServerError</h3>

<a id="schemainternalservererror"></a>

```json
{
  "statusCode": 0,
  "message": "string"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|statusCode|number|true|none|none|
|message|string|true|none|none|

<h3 id="tocSvalidationmodel">ValidationModel</h3>

<a id="schemavalidationmodel"></a>

```json
{
  "payload": {
    "status": true,
    "meta": "string"
  }
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|payload|object|true|none|none|
|» status|boolean|true|none|none|
|» meta|string|true|none|none|

<h3 id="tocSbundlesmodel">BundlesModel</h3>

<a id="schemabundlesmodel"></a>

```json
{
  "bundles": [
    {
      "itemTypes": [
        {
          "uuid": "string",
          "name": "string",
          "slug": "string",
          "isDefault": true,
          "ticketGroup": "string",
          "maxRestriction": 0,
          "minRestriction": 0,
          "items": [
            {
              "taxExempt": 0,
              "vatRateEatIn": 0,
              "vatRateTakeaway": 0,
              "price": 0,
              "priceEatIn": 0,
              "finalPrice": 0,
              "name": "string",
              "slug": "string",
              "straightToPickup": true,
              "itemUUID": "string",
              "uuid": "string",
              "customizations": [
                {
                  "type": "string",
                  "uuid": "string",
                  "text": "string",
                  "variations": [
                    {}
                  ],
                  "current": "string",
                  "meta": {
                    "text": "string",
                    "defaultValue": "string"
                  }
                }
              ]
            }
          ]
        }
      ],
      "taxExempt": 0,
      "vatRateEatIn": 0,
      "vatRateTakeaway": 0,
      "price": 0,
      "priceEatIn": 0,
      "finalPrice": 0,
      "name": "string",
      "basketUUID": "string",
      "hasItemsModifiers": true,
      "type": "string",
      "uuid": "string",
      "straightToPickup": true,
      "category": {
        "uuid": "string",
        "slug": "string",
        "name": "string"
      },
      "grouped": true
    }
  ],
  "takeaway": true
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|bundles|[object]|true|none|none|
|» itemTypes|[object]|true|none|none|
|»» uuid|string|true|none|none|
|»» name|string|false|none|none|
|»» slug|string|false|none|none|
|»» isDefault|boolean|false|none|none|
|»» ticketGroup|string|false|none|none|
|»» maxRestriction|integer|false|none|none|
|»» minRestriction|integer|false|none|none|
|»» items|[object]|true|none|none|
|»»» taxExempt|number|true|none|none|
|»»» vatRateEatIn|number|true|none|none|
|»»» vatRateTakeaway|number|true|none|none|
|»»» price|number|true|none|none|
|»»» priceEatIn|number|false|none|none|
|»»» finalPrice|number|true|none|none|
|»»» name|string|false|none|none|
|»»» slug|string|false|none|none|
|»»» straightToPickup|boolean|false|none|none|
|»»» itemUUID|string|true|none|none|
|»»» uuid|string|true|none|none|
|»»» customizations|[object]|false|none|none|
|»»»» type|string|false|none|none|
|»»»» uuid|string|true|none|none|
|»»»» text|string|false|none|none|
|»»»» variations|[object]|false|none|none|
|»»»»» uuid|string|true|none|none|
|»»»»» unit|object|false|none|none|
|»»»»» price|number|true|none|none|
|»»»»» step|integer|false|none|none|
|»»»»» type|string|false|none|none|
|»»»»» value|string|false|none|none|
|»»»»» printText|string|false|none|none|
|»»»» current|string|false|none|none|
|»»»» meta|object|false|none|none|
|»»»»» text|string|true|none|none|
|»»»»» defaultValue|string|true|none|none|
|»»»» taxExempt|number|true|none|none|
|»»»» vatRateEatIn|number|true|none|none|
|»»»» vatRateTakeaway|number|true|none|none|
|»»»» price|number|false|none|none|
|»»»» priceEatIn|number|false|none|none|
|»»»» finalPrice|number|false|none|none|
|»»»» name|string|false|none|none|
|»»»» basketUUID|string|false|none|none|
|»»»» hasItemsModifiers|boolean|false|none|none|
|»»»» type|string|false|none|none|
|»»»» uuid|string|true|none|none|
|»»»» straightToPickup|boolean|false|none|none|
|»»»» category|object|false|none|none|
|»»»»» uuid|string|true|none|none|
|»»»»» slug|string|true|none|none|
|»»»»» name|string|true|none|none|
|»»»» grouped|boolean|false|none|none|
|»»» takeaway|boolean|true|none|none|

<h3 id="tocSbundlemodel">BundleModel</h3>

<a id="schemabundlemodel"></a>

```json
{
  "payload": {
    "uuid": "string",
    "taxExempt": 0,
    "vatRateEatIn": 0,
    "vatRateTakeaway": 0,
    "name": "string",
    "description": "string",
    "isGrouped": true,
    "onlineDescription": "string",
    "kitchenTicketGroup": "string",
    "upsellText": "string",
    "upsellItemTypeUUID": "string",
    "category": {
      "name": "string",
      "uuid": "string"
    },
    "rootCategory": {
      "name": "string",
      "uuid": "string"
    },
    "hasModifiers": false,
    "diets": [
      "string"
    ],
    "allergens": [
      "string"
    ],
    "items": [
      {
        "uuid": "string",
        "sortOrder": 0,
        "name": "string",
        "price": 0,
        "nutritionalMeta": {},
        "description": null,
        "onlineDescription": "string",
        "itemType": {
          "uuid": "string",
          "name": "string",
          "sortOrder": 0,
          "minRestriction": 0,
          "maxRestriction": 0
        },
        "kitchenZone": {
          "uuid": "string",
          "name": "string",
          "slug": "string",
          "sortOrderOnPrint": 0,
          "capacity": 0
        },
        "customizations": [
          {
            "type": "string",
            "uuid": "string",
            "current": "string",
            "text": "string",
            "meta": {},
            "variations": [
              {
                "step": 0,
                "value": "string",
                "price": 0,
                "uuid": "string",
                "type": "string",
                "text": "string",
                "unit": {
                  "slug": "string",
                  "name": "string",
                  "value": 0
                }
              }
            ]
          }
        ]
      }
    ]
  }
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|payload|object|true|none|none|
|» uuid|string|true|none|none|
|» taxExempt|number|true|none|none|
|» vatRateEatIn|number|true|none|none|
|» vatRateTakeaway|number|true|none|none|
|» name|string|true|none|none|
|» description|string|false|none|none|
|» isGrouped|boolean|false|none|none|
|» onlineDescription|string|false|none|none|
|» kitchenTicketGroup|string|false|none|none|
|» upsellText|string|false|none|none|
|» upsellItemTypeUUID|string|false|none|none|
|» category|object|false|none|none|
|»» name|string|true|none|none|
|»» uuid|string|true|none|none|
|» rootCategory|object|false|none|none|
|»» name|string|true|none|none|
|»» uuid|string|true|none|none|
|» hasModifiers|boolean|true|none|none|
|» diets|[string]|true|none|none|
|» allergens|[string]|true|none|none|
|» items|[object]|true|none|none|
|»» uuid|string|true|none|none|
|»» sortOrder|integer|true|none|none|
|»» name|string|true|none|none|
|»» price|number|true|none|none|
|»» nutritionalMeta|object|false|none|none|
|»» description|string|false|none|none|
|»» onlineDescription|string|false|none|none|
|»» itemType|object|true|none|none|
|»»» uuid|string|true|none|none|
|»»» name|string|true|none|none|
|»»» sortOrder|integer|true|none|none|
|»»» minRestriction|integer|true|none|none|
|»»» maxRestriction|integer|true|none|none|
|»» kitchenZone|object|false|none|none|
|»»» uuid|string|true|none|none|
|»»» name|string|true|none|none|
|»»» slug|string|true|none|none|
|»»» sortOrderOnPrint|integer|true|none|none|
|»»» capacity|integer|true|none|none|
|»» customizations|[object]|true|none|none|
|»»» type|string|true|none|none|
|»»» uuid|string|true|none|none|
|»»» current|string|true|none|none|
|»»» text|string|true|none|none|
|»»» meta|object|false|none|none|
|»»» variations|[object]|true|none|none|
|»»»» step|integer|true|none|none|
|»»»» value|string|true|none|none|
|»»»» price|number|true|none|none|
|»»»» uuid|string|true|none|none|
|»»»» type|string|true|none|none|
|»»»» text|string|false|none|none|
|»»»» unit|object|true|none|none|
|»»»»» slug|string|true|none|none|
|»»»»» name|string|true|none|none|
|»»»»» value|number|true|none|none|

<h3 id="tocSbundleitemtypesitems">BundleItemTypesItems</h3>

<a id="schemabundleitemtypesitems"></a>

```json
{
  "payload": [
    {
      "uuid": "string",
      "name": "string",
      "sortOrder": 0,
      "minRestriction": 0,
      "maxRestriction": 0,
      "description": "string",
      "onlineDescription": "string",
      "ticketGroup": "string",
      "items": [
        {
          "uuid": "string",
          "taxExempt": 0,
          "vatRateEatIn": 0,
          "vatRateTakeaway": 0,
          "sortOrder": 0,
          "name": "string",
          "price": 0,
          "nutritionalMeta": {},
          "kitchenZone": {
            "uuid": "string",
            "name": "string",
            "slug": "string",
            "sortOrderOnPrint": 0,
            "capacity": 0
          },
          "itemType": {
            "uuid": "string",
            "name": "string",
            "sortOrder": 0,
            "minRestriction": 0,
            "maxRestriction": 0
          },
          "customizations": [
            {
              "type": "string",
              "uuid": "string",
              "text": "string",
              "variations": [
                {
                  "step": 0,
                  "value": "string",
                  "price": 0,
                  "uuid": "string",
                  "type": "string"
                }
              ],
              "current": "string"
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
|payload|[object]|true|none|none|
|» uuid|string|true|none|none|
|» name|string|true|none|none|
|» sortOrder|integer|true|none|none|
|» minRestriction|integer|false|none|none|
|» maxRestriction|integer|false|none|none|
|» description|string|false|none|none|
|» onlineDescription|string|false|none|none|
|» ticketGroup|string|false|none|none|
|» items|[object]|true|none|none|
|»» uuid|string|true|none|none|
|»» taxExempt|number|true|none|none|
|»» vatRateEatIn|number|true|none|none|
|»» vatRateTakeaway|number|true|none|none|
|»» sortOrder|integer|false|none|none|
|»» name|string|true|none|none|
|»» price|number|true|none|none|
|»» nutritionalMeta|object|false|none|none|
|»» kitchenZone|object|false|none|none|
|»»» uuid|string|true|none|none|
|»»» name|string|true|none|none|
|»»» slug|string|true|none|none|
|»»» sortOrderOnPrint|integer|true|none|none|
|»»» capacity|integer|true|none|none|
|»» itemType|object|true|none|none|
|»»» uuid|string|true|none|none|
|»»» name|string|true|none|none|
|»»» sortOrder|integer|false|none|none|
|»»» minRestriction|integer|false|none|none|
|»»» maxRestriction|integer|false|none|none|
|»» customizations|[object]|true|none|none|
|»»» type|string|true|none|none|
|»»» uuid|string|true|none|none|
|»»» text|string|true|none|none|
|»»» variations|[object]|true|none|none|
|»»»» step|integer|true|none|none|
|»»»» value|string|true|none|none|
|»»»» price|number|true|none|none|
|»»»» uuid|string|true|none|none|
|»»»» type|string|true|none|none|
|»»» current|string|false|none|none|

<h3 id="tocSdietresponsemodel">DietResponseModel</h3>

<a id="schemadietresponsemodel"></a>

```json
{
  "payload": {
    "diets": [
      {
        "uuid": "string",
        "name": "string",
        "image": "string",
        "selectImage": "string",
        "description": "string"
      }
    ],
    "allergens": [
      {
        "uuid": "string",
        "image": "string",
        "selectImage": "string",
        "name": "string",
        "description": "string"
      }
    ]
  }
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|payload|object|true|none|none|
|» diets|[object]|true|none|none|
|»» uuid|string|true|none|none|
|»» name|string|true|none|none|
|»» image|string|true|none|none|
|»» selectImage|string|true|none|none|
|»» description|string|true|none|none|
|» allergens|[object]|true|none|none|
|»» uuid|string|true|none|none|
|»» image|string|true|none|none|
|»» selectImage|string|true|none|none|
|»» name|string|true|none|none|
|»» description|string|true|none|none|

<h3 id="tocSmanagementbundledto">ManagementBundleDto</h3>

<a id="schemamanagementbundledto"></a>

```json
{
  "uuid": "string",
  "isFixedPrice": true,
  "status": true,
  "name": "string",
  "slug": "string",
  "description": "string",
  "taxExempt": "string",
  "straightToPickup": true,
  "isPrintable": true,
  "hasEatInPrice": true,
  "isGrouped": true,
  "upsellText": "string",
  "upsellItemTypeUUID": "string",
  "type": "CUSTOMISED",
  "onlineDescription": "string",
  "kitchenTicketGroup": "string",
  "price": 0,
  "priceFrom": 0,
  "priceEatInFrom": 0,
  "priceEatIn": 0,
  "tags": [
    {
      "name": "string",
      "uuid": "string"
    }
  ],
  "itemTypes": [
    {
      "uuid": "string",
      "name": "string",
      "sortOrder": 0,
      "minRestriction": 0,
      "maxRestriction": 0,
      "ticketGroup": "string",
      "isDefault": true,
      "isUpsellItemType": true,
      "items": [
        {
          "uuid": "string",
          "isPreselected": true,
          "isRequired": true,
          "sortOrder": 0,
          "price": 0
        }
      ]
    }
  ],
  "menus": [
    {
      "uuid": "string",
      "isActive": true,
      "isSoldOut": true,
      "price": 0
    }
  ]
}

```

*This contract is used for CREATE/UPDATE 'bundle' requests*

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|uuid|string|false|none|none|
|isFixedPrice|boolean|true|none|none|
|status|boolean|true|none|none|
|name|string|true|none|none|
|slug|string|false|none|none|
|description|string|true|none|none|
|taxExempt|string|true|none|none|
|straightToPickup|boolean|true|none|none|
|isPrintable|boolean|true|none|none|
|hasEatInPrice|boolean|false|none|none|
|isGrouped|boolean|true|none|none|
|upsellText|string|false|none|none|
|upsellItemTypeUUID|string|false|none|none|
|type|string|false|none|none|
|onlineDescription|string|false|none|none|
|kitchenTicketGroup|string|false|none|none|
|price|number|false|none|none|
|priceFrom|number|false|none|none|
|priceEatInFrom|number|false|none|none|
|priceEatIn|number|false|none|none|
|tags|[object]|true|none|none|
|» name|string|true|none|none|
|» uuid|string|false|none|uuid is not required, because of on create/update bundle, we also can create new tags|
|itemTypes|[object]|true|none|none|
|» uuid|string|true|none|none|
|» name|string|true|none|none|
|» sortOrder|integer|true|none|none|
|» minRestriction|integer|true|none|none|
|» maxRestriction|integer|true|none|none|
|» ticketGroup|string|true|none|none|
|» isDefault|boolean|true|none|none|
|» isUpsellItemType|boolean|false|none|none|
|» items|[object]|true|none|none|
|»» uuid|string|true|none|none|
|»» isPreselected|boolean|true|none|none|
|»» isRequired|boolean|true|none|none|
|»» sortOrder|integer|true|none|none|
|»» price|integer|false|none|none|
|» menus|[object]|true|none|none|
|»» uuid|string|true|none|none|
|»» isActive|boolean|true|none|none|
|»» isSoldOut|boolean|true|none|none|
|»» price|number|false|none|none|

#### Enumerated Values

|Property|Value|
|---|---|
|type|CUSTOMISED|
|type|VIRTUAL|
|type|BUILD_YOUR_OWN|

<h3 id="tocSmanagementbundlemodel">ManagementBundleModel</h3>

<a id="schemamanagementbundlemodel"></a>

```json
{
  "payload": {
    "uuid": "string",
    "name": "string",
    "description": "string",
    "taxExempt": 0,
    "straightToPickup": true,
    "isPrintable": true,
    "hasEatInPrice": true,
    "price": 0,
    "priceFrom": 0,
    "priceEatInFrom": 0,
    "priceEatIn": 0,
    "upsellText": "string",
    "upsellItemTypeUUID": "string",
    "type": "CUSTOMISED",
    "tags": [
      {
        "uuid": "string",
        "name": "string"
      }
    ],
    "itemTypes": [
      {
        "uuid": "string",
        "name": "string",
        "sortOrder": 0,
        "minRestriction": 0,
        "maxRestriction": 0,
        "ticketGroup": "string",
        "isDefault": true,
        "isUpsellItemType": true,
        "items": [
          {
            "uuid": "string",
            "name": "string",
            "isPreselected": true,
            "isRequired": true,
            "sortOrder": 0,
            "price": "string",
            "basePrice": "string",
            "priceEatIn": "string",
            "hasEatInPrice": true,
            "itemModifiers": [
              {
                "uuid": "string",
                "meta": {},
                "modifier": {
                  "uuid": "string",
                  "name": "string",
                  "meta": {},
                  "slug": "string"
                },
                "itemModifierOptions": [
                  {
                    "uuid": "string",
                    "meta": {},
                    "measurementUnit": {},
                    "price": "string"
                  }
                ]
              }
            ]
          }
        ]
      }
    ],
    "menus": [
      {
        "uuid": "string",
        "name": "string",
        "isActive": true,
        "isSoldOut": true,
        "price": "string"
      }
    ]
  }
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|payload|object|true|none|none|
|» uuid|string|true|none|none|
|» name|string|true|none|none|
|» description|string|true|none|none|
|» taxExempt|number|true|none|none|
|» straightToPickup|boolean|true|none|none|
|» isPrintable|boolean|true|none|none|
|» hasEatInPrice|boolean|false|none|none|
|» price|number|false|none|none|
|» priceFrom|number|false|none|none|
|» priceEatInFrom|number|false|none|none|
|» priceEatIn|number|false|none|none|
|» upsellText|string|false|none|none|
|» upsellItemTypeUUID|string|false|none|none|
|» type|string|true|none|none|
|» tags|[object]|true|none|none|
|»» uuid|string|true|none|none|
|»» name|string|true|none|none|
|» itemTypes|[object]|true|none|none|
|»» uuid|string|true|none|none|
|»» name|string|true|none|none|
|»» sortOrder|integer|true|none|none|
|»» minRestriction|integer|true|none|none|
|»» maxRestriction|integer|true|none|none|
|»» ticketGroup|string|true|none|none|
|»» isDefault|boolean|true|none|none|
|»» isUpsellItemType|boolean|false|none|none|
|»» items|[object]|true|none|none|
|»»» uuid|string|true|none|none|
|»»» name|string|true|none|none|
|»»» isPreselected|boolean|true|none|none|
|»»» isRequired|boolean|true|none|none|
|»»» sortOrder|integer|true|none|none|
|»»» price|string|false|none|item price overrided by itemType|
|»»» basePrice|string|true|none|base item price, defined on create/update item(management)|
|»»» priceEatIn|string|true|none|eatIn item price, defined on create/update item(management)|
|»»» hasEatInPrice|boolean|true|none|hasEatInPrice flag, defined on create/update item(management)|
|»»» itemModifiers|[object]|true|none|none|
|»»»» uuid|string|true|none|none|
|»»»» meta|object|false|none|none|
|»»»» modifier|object|true|none|none|
|»»»»» uuid|string|true|none|none|
|»»»»» name|string|true|none|none|
|»»»»» meta|object|false|none|none|
|»»»»» slug|string|false|none|none|
|»»»» itemModifierOptions|[object]|true|none|none|
|»»»»» uuid|string|true|none|none|
|»»»»» meta|object|false|none|none|
|»»»»» measurementUnit|object|false|none|none|
|»»»»» price|string|false|none|none|
|»»»» menus|[object]|true|none|none|
|»»»»» uuid|string|true|none|none|
|»»»»» name|string|true|none|none|
|»»»»» isActive|boolean|true|none|none|
|»»»»» isSoldOut|boolean|true|none|none|
|»»»»» price|string|false|none|none|

#### Enumerated Values

|Property|Value|
|---|---|
|type|CUSTOMISED|
|type|VIRTUAL|
|type|BUILD_YOUR_OWN|
|type|FIXED_PRICE|

<h3 id="tocSstatusupdatedto">StatusUpdateDto</h3>

<a id="schemastatusupdatedto"></a>

```json
{
  "active": true
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|active|boolean|true|none|none|

<h3 id="tocSitemsmodel">ItemsModel</h3>

<a id="schemaitemsmodel"></a>

```json
{
  "required": [
    "meta",
    "payload"
  ],
  "type": "object",
  "properties": {
    "meta": {
      "required": [
        "page",
        "limit",
        "pageCount",
        "totalCount"
      ],
      "type": "object",
      "properties": {
        "page": {
          "type": "integer"
        },
        "limit": {
          "type": "integer"
        },
        "pageCount": {
          "type": "integer"
        },
        "totalCount": {
          "type": "integer"
        }
      }
    },
    "payload": {
      "type": "array",
      "items": {
        "required": [
          "uuid",
          "name",
          "tags",
          "status",
          "price"
        ],
        "type": "object",
        "properties": {
          "uuid": {
            "type": "string"
          },
          "name": {
            "type": "string"
          },
          "tags": {
            "type": "array",
            "items": {
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
            }
          },
          "status": {
            "type": "string"
          },
          "price": {
            "type": "number"
          },
          "itemModifiers": {
            "type": "array",
            "items": {
              "required": [
                "uuid",
                "modifier",
                "itemModifierOptions"
              ],
              "type": "object",
              "properties": {
                "uuid": {
                  "type": "string"
                },
                "meta": {
                  "type": "object"
                },
                "modifier": {
                  "required": [
                    "uuid",
                    "name"
                  ],
                  "type": "object",
                  "properties": {
                    "uuid": {},
                    "name": {},
                    "meta": {},
                    "slug": {}
                  }
                },
                "itemModifierOptions": {
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
|meta|object|true|none|none|
|» page|integer|true|none|none|
|» limit|integer|true|none|none|
|» pageCount|integer|true|none|none|
|» totalCount|integer|true|none|none|
|payload|[object]|true|none|none|
|» uuid|string|true|none|none|
|» name|string|true|none|none|
|» tags|[object]|true|none|none|
|»» uuid|string|true|none|none|
|»» name|string|true|none|none|
|» status|string|true|none|none|
|» price|number|true|none|none|
|» itemModifiers|[object]|false|none|none|
|»» uuid|string|true|none|none|
|»» meta|object|false|none|none|
|»» modifier|object|true|none|none|
|»»» uuid|string|true|none|none|
|»»» name|string|true|none|none|
|»»» meta|object|false|none|none|
|»»» slug|string|false|none|none|
|»» itemModifierOptions|[object]|true|none|none|
|»»» uuid|string|true|none|none|
|»»» meta|object|false|none|none|
|»»» measurementUnit|string|false|none|none|

*allOf*

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|»»»» *anonymous*|string|false|none|none|

*and*

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|»»»» *anonymous*|object|false|none|none|

*continued*

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|»»» price|string|true|none|none|

<h3 id="tocSitembyuuidmodel">ItemByUUIDModel</h3>

<a id="schemaitembyuuidmodel"></a>

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
        "name",
        "kitchenTicketName",
        "taxExempt",
        "kitchenZoneUUID",
        "isPrintable",
        "tags",
        "price",
        "straightToPickup",
        "menus",
        "itemModifiers",
        "allergens",
        "diets"
      ],
      "type": "object",
      "properties": {
        "uuid": {
          "type": "string"
        },
        "name": {
          "type": "string"
        },
        "kitchenTicketName": {
          "type": "string"
        },
        "description": {
          "type": "string"
        },
        "taxRate": {
          "type": "number"
        },
        "taxExempt": {
          "type": "number"
        },
        "kitchenZoneUUID": {
          "type": "string"
        },
        "nutritionalMeta": {
          "type": "object"
        },
        "isPrintable": {
          "type": "boolean"
        },
        "hasEatInPrice": {
          "type": "boolean"
        },
        "slug": {
          "type": "string"
        },
        "tags": {
          "type": "array",
          "items": {
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
          }
        },
        "price": {
          "type": "number"
        },
        "priceEatIn": {
          "type": "number"
        },
        "straightToPickup": {
          "type": "boolean"
        },
        "allergens": {
          "type": "array",
          "items": {
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
              },
              "description": {
                "type": "string"
              },
              "image": {
                "type": "string"
              },
              "selectImage": {
                "type": "string"
              }
            }
          }
        },
        "diets": {
          "type": "array",
          "items": {
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
              },
              "description": {
                "type": "string"
              },
              "image": {
                "type": "string"
              },
              "selectImage": {
                "type": "string"
              }
            }
          }
        },
        "menus": {
          "type": "array",
          "items": {
            "required": [
              "menuUUID",
              "price",
              "isActive",
              "isSoldOut"
            ],
            "type": "object",
            "properties": {
              "menuUUID": {
                "type": "string"
              },
              "menu": {
                "required": [
                  "name",
                  "sortOrder",
                  "uuid"
                ],
                "type": "object",
                "properties": {
                  "name": {
                    "type": "string"
                  },
                  "sortOrder": {
                    "type": "number"
                  },
                  "uuid": {
                    "type": "string"
                  }
                }
              },
              "price": {
                "type": "string"
              },
              "isActive": {
                "type": "boolean"
              },
              "isSoldOut": {
                "type": "boolean"
              }
            }
          }
        },
        "itemModifiers": {
          "type": "array",
          "items": {
            "required": [
              "uuid",
              "modifier",
              "itemModifierOptions"
            ],
            "type": "object",
            "properties": {
              "uuid": {
                "type": "string"
              },
              "meta": {
                "type": "object"
              },
              "modifier": {
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
                  },
                  "meta": {
                    "type": "object"
                  },
                  "slug": {
                    "type": "string"
                  }
                }
              },
              "itemModifierOptions": {
                "type": "array",
                "items": {
                  "required": [
                    "uuid",
                    "price"
                  ],
                  "type": "object",
                  "properties": {
                    "uuid": {},
                    "meta": {},
                    "measurementUnit": {},
                    "price": {}
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
|» name|string|true|none|none|
|» kitchenTicketName|string|true|none|none|
|» description|string|false|none|none|
|» taxRate|number|false|none|none|
|» taxExempt|number|true|none|none|
|» kitchenZoneUUID|string|true|none|none|
|» nutritionalMeta|object|false|none|none|
|» isPrintable|boolean|true|none|none|
|» hasEatInPrice|boolean|false|none|none|
|» slug|string|false|none|none|
|» tags|[object]|true|none|none|
|»» uuid|string|true|none|none|
|»» name|string|true|none|none|
|» price|number|true|none|none|
|» priceEatIn|number|false|none|none|
|» straightToPickup|boolean|true|none|none|
|» allergens|[object]|true|none|none|
|»» uuid|string|true|none|none|
|»» name|string|true|none|none|
|»» description|string|false|none|none|
|»» image|string|false|none|none|
|»» selectImage|string|false|none|none|
|» diets|[object]|true|none|none|
|»» uuid|string|true|none|none|
|»» name|string|true|none|none|
|»» description|string|false|none|none|
|»» image|string|false|none|none|
|»» selectImage|string|false|none|none|
|» menus|[object]|true|none|none|
|»» menuUUID|string|true|none|none|
|»» menu|object|false|none|none|
|»»» name|string|true|none|none|
|»»» sortOrder|number|true|none|none|
|»»» uuid|string|true|none|none|
|»» price|string|true|none|none|
|»» isActive|boolean|true|none|none|
|»» isSoldOut|boolean|true|none|none|
|» itemModifiers|[object]|true|none|none|
|»» uuid|string|true|none|none|
|»» meta|object|false|none|none|
|»» modifier|object|true|none|none|
|»»» uuid|string|true|none|none|
|»»» name|string|true|none|none|
|»»» meta|object|false|none|none|
|»»» slug|string|false|none|none|
|»» itemModifierOptions|[object]|true|none|none|
|»»» uuid|string|true|none|none|
|»»» meta|object|false|none|none|
|»»» measurementUnit|string|false|none|none|

*allOf*

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|»»»» *anonymous*|string|false|none|none|

*and*

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|»»»» *anonymous*|object|false|none|none|

*continued*

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|»»» price|string|true|none|none|

<h3 id="tocSitemmanagementdto">ItemManagementDto</h3>

<a id="schemaitemmanagementdto"></a>

```json
{
  "name": "string",
  "media": "string",
  "description": "string",
  "onlineDescription": "string",
  "taxRate": 0,
  "taxExempt": 0,
  "kitchenTicketName": "string",
  "kitchenZoneUUID": "string",
  "isPrintable": true,
  "price": 0,
  "straightToPickup": true,
  "slug": "string",
  "tags": [],
  "menus": [
    {
      "name": "string",
      "slug": "string",
      "description": "string",
      "sortOrder": 0,
      "interval": 0
    }
  ],
  "allergens": [
    "string"
  ],
  "diets": [
    "string"
  ],
  "itemModifiers": []
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|name|string|true|none|none|
|media|string|true|none|none|
|description|string|true|none|none|
|onlineDescription|string|true|none|none|
|taxRate|number|true|none|none|
|taxExempt|number|true|none|none|
|kitchenTicketName|string|true|none|none|
|kitchenZoneUUID|string|true|none|none|
|isPrintable|boolean|true|none|none|
|price|number|true|none|none|
|straightToPickup|boolean|true|none|none|
|slug|string|true|none|none|
|tags|[[TagDto](#schematagdto)]|true|none|none|
|menus|[[MenuDto](#schemamenudto)]|true|none|none|
|allergens|[string]|true|none|none|
|diets|[string]|true|none|none|
|itemModifiers|[[ItemModifierDto](#schemaitemmodifierdto)]|true|none|none|

<h3 id="tocSkitchenzone">KitchenZone</h3>

<a id="schemakitchenzone"></a>

```json
{
  "payload": [
    {
      "uuid": "string",
      "name": "string",
      "slug": "string",
      "sortOrderOnPrint": 0,
      "capacity": 0
    }
  ]
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|payload|[object]|true|none|none|
|» uuid|string|true|none|none|
|» name|string|true|none|none|
|» slug|string|true|none|none|
|» sortOrderOnPrint|integer|true|none|none|
|» capacity|integer|true|none|none|

<h3 id="tocSmeasurementunits">MeasurementUnits</h3>

<a id="schemameasurementunits"></a>

```json
{
  "payload": [
    {
      "uuid": "string",
      "slug": "string",
      "name": "string",
      "value": 0
    }
  ]
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|payload|[object]|true|none|none|
|» uuid|string|true|none|none|
|» slug|string|false|none|none|
|» name|string|true|none|none|
|» value|integer|true|none|none|

<h3 id="tocSmanagementallergens">ManagementAllergens</h3>

<a id="schemamanagementallergens"></a>

```json
{
  "payload": [
    {
      "uuid": "string",
      "name": "string",
      "description": "string",
      "image": "string",
      "selectImage": "string"
    }
  ]
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|payload|[object]|true|none|none|
|» uuid|string|true|none|none|
|» name|string|true|none|none|
|» description|string|true|none|none|
|» image|string|true|none|none|
|» selectImage|string|true|none|none|

<h3 id="tocSmanagementdiets">ManagementDiets</h3>

<a id="schemamanagementdiets"></a>

```json
{
  "payload": [
    {
      "uuid": "string",
      "name": "string",
      "description": "string",
      "image": "string",
      "selectImage": "string"
    }
  ]
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|payload|[object]|true|none|none|
|» uuid|string|true|none|none|
|» name|string|true|none|none|
|» description|string|true|none|none|
|» image|string|true|none|none|
|» selectImage|string|true|none|none|

<h3 id="tocSmenu">Menu</h3>

<a id="schemamenu"></a>

```json
{
  "payload": {
    "name": "string",
    "slug": "string",
    "description": "string",
    "sortOrder": 0,
    "interval": 0
  }
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|payload|object|true|none|none|
|» name|string|true|none|none|
|» slug|string|true|none|none|
|» description|string|false|none|none|
|» sortOrder|integer|true|none|none|
|» interval|integer|false|none|none|

<h3 id="tocSmenudto">MenuDto</h3>

<a id="schemamenudto"></a>

```json
{
  "name": "string",
  "slug": "string",
  "description": "string",
  "sortOrder": 0,
  "interval": 0
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|name|string|true|none|none|
|slug|string|true|none|none|
|description|string|false|none|none|
|sortOrder|integer|true|none|none|
|interval|integer|false|none|none|

<h3 id="tocSmodifier">Modifier</h3>

<a id="schemamodifier"></a>

```json
{
  "payload": [
    {
      "uuid": "string",
      "name": "string",
      "meta": {},
      "slug": "string"
    }
  ]
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|payload|[object]|true|none|none|
|» uuid|string|true|none|none|
|» name|string|true|none|none|
|» meta|object|false|none|none|
|» slug|string|true|none|none|

<h3 id="tocStag">Tag</h3>

<a id="schematag"></a>

```json
{
  "payload": [
    {
      "uuid": "string",
      "name": "string"
    }
  ]
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|payload|[object]|true|none|none|
|» uuid|string|true|none|none|
|» name|string|true|none|none|

<h3 id="tocSunit">Unit</h3>

<a id="schemaunit"></a>

```json
{
  "payload": [
    {
      "slug": "string",
      "name": "string"
    }
  ]
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|payload|[object]|true|none|none|
|» slug|string|true|none|none|
|» name|string|true|none|none|

<h3 id="tocSlayoutmenumodel">LayoutMenuModel</h3>

<a id="schemalayoutmenumodel"></a>

```json
{
  "payload": [
    {
      "uuid": "string",
      "name": "string",
      "isActive": true,
      "isVisible": true
    }
  ]
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|payload|[object]|true|none|none|
|» uuid|string|true|none|none|
|» name|string|true|none|none|
|» isActive|boolean|true|none|none|
|» isVisible|boolean|true|none|none|

<h3 id="tocSlayoutmenus">LayoutMenus</h3>

<a id="schemalayoutmenus"></a>

```json
{
  "menus": [
    {
      "uuid": "string",
      "name": "string",
      "isActive": true,
      "isVisible": true
    }
  ]
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|menus|[object]|true|none|none|
|» uuid|string|true|none|none|
|» name|string|true|none|none|
|» isActive|boolean|true|none|none|
|» isVisible|boolean|true|none|none|

<h3 id="tocSmovebundledto">MoveBundleDto</h3>

<a id="schemamovebundledto"></a>

```json
{
  "products": [
    {
      "uuid": "string",
      "type": "string"
    }
  ]
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|products|[object]|true|none|none|
|» uuid|string|true|none|none|
|» type|string|true|none|none|

<h3 id="tocSmovecategorydto">MoveCategoryDto</h3>

<a id="schemamovecategorydto"></a>

```json
{
  "uuid": "string",
  "name": "string",
  "sortOrder": 0
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|uuid|string|true|none|none|
|name|string|true|none|none|
|sortOrder|integer|true|none|none|

<h3 id="tocScategoryproducts">CategoryProducts</h3>

<a id="schemacategoryproducts"></a>

```json
{
  "meta": {
    "page": 0,
    "limit": 0,
    "pageCount": 0,
    "totalCount": 0
  },
  "payload": [
    {
      "uuid": "string",
      "name": "string",
      "tags": [
        {
          "name": "string"
        }
      ],
      "isActive": true,
      "isSoldout": true,
      "type": "string"
    }
  ]
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|meta|object|true|none|none|
|» page|integer|true|none|none|
|» limit|integer|true|none|none|
|» pageCount|integer|true|none|none|
|» totalCount|integer|true|none|none|
|payload|[object]|true|none|none|
|» uuid|string|true|none|none|
|» name|string|true|none|none|
|» tags|[object]|true|none|none|
|»» name|string|true|none|none|
|» isActive|boolean|true|none|none|
|» isSoldout|boolean|true|none|none|
|» type|string|true|none|none|

<h3 id="tocSlayoutmenucategories">LayoutMenuCategories</h3>

<a id="schemalayoutmenucategories"></a>

```json
{
  "payload": [
    {
      "uuid": "string",
      "name": "string",
      "type": "string",
      "sortOrder": 0
    }
  ]
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|payload|[object]|true|none|none|
|» uuid|string|true|none|none|
|» name|string|true|none|none|
|» type|string|true|none|none|
|» sortOrder|integer|true|none|none|

<h3 id="tocSrootcategoryproducts">RootCategoryProducts</h3>

<a id="schemarootcategoryproducts"></a>

```json
{
  "payload": {
    "bundles": [
      {
        "uuid": "string",
        "itemUUID": "string",
        "name": "string",
        "tags": [
          {
            "name": "string"
          }
        ],
        "isActive": true,
        "isSoldOut": true,
        "sortOrder": 0
      }
    ],
    "categories": [
      {
        "name": "string",
        "uuid": "string",
        "sortOrder": 0,
        "bundles": [
          {
            "uuid": "string",
            "itemUUID": "string",
            "name": "string",
            "tags": [
              {
                "name": "string"
              }
            ],
            "isActive": true,
            "isSoldOut": true,
            "sortOrder": 0
          }
        ]
      }
    ]
  }
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|payload|object|true|none|none|
|» bundles|[object]|true|none|none|
|»» uuid|string|true|none|none|
|»» itemUUID|string|false|none|none|
|»» name|string|true|none|none|
|»» tags|[object]|true|none|none|
|»»» name|string|true|none|none|
|»» isActive|boolean|true|none|none|
|»» isSoldOut|boolean|true|none|none|
|»» sortOrder|integer|true|none|none|
|» categories|[object]|true|none|none|
|»» name|string|true|none|none|
|»» uuid|string|true|none|none|
|»» sortOrder|integer|true|none|none|
|»» bundles|[object]|true|none|none|
|»»» uuid|string|true|none|none|
|»»» itemUUID|string|false|none|none|
|»»» name|string|true|none|none|
|»»» tags|[object]|true|none|none|
|»»»» name|string|true|none|none|
|»»» isActive|boolean|true|none|none|
|»»» isSoldOut|boolean|true|none|none|
|»»» sortOrder|integer|true|none|none|

<h3 id="tocScategory">Category</h3>

<a id="schemacategory"></a>

```json
{
  "payload": {
    "name": "string",
    "uuid": "string",
    "sortOrder": 0
  }
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|payload|object|true|none|none|
|» name|string|true|none|none|
|» uuid|string|true|none|none|
|» sortOrder|integer|true|none|none|

<h3 id="tocScategorydto">CategoryDto</h3>

<a id="schemacategorydto"></a>

```json
{
  "name": "string",
  "sortOrder": 0
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|name|string|true|none|none|
|sortOrder|integer|true|none|none|

<h3 id="tocScategoryproductsdto">CategoryProductsDto</h3>

<a id="schemacategoryproductsdto"></a>

```json
{
  "products": [
    {
      "uuid": "string",
      "type": "string"
    }
  ]
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|products|[object]|true|none|none|
|» uuid|string|true|none|none|
|» type|string|true|none|none|

<h3 id="tocSreordercategorybundlesdto">ReorderCategoryBundlesDto</h3>

<a id="schemareordercategorybundlesdto"></a>

```json
{
  "products": [
    {
      "uuid": "string",
      "sortOrder": 0
    }
  ]
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|products|[object]|true|none|none|
|» uuid|string|true|none|none|
|» sortOrder|integer|true|none|none|

<h3 id="tocSreordercategoriesdto">ReorderCategoriesDto</h3>

<a id="schemareordercategoriesdto"></a>

```json
{
  "categories": [
    {
      "uuid": "string",
      "sortOrder": 0
    }
  ]
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|categories|[object]|true|none|none|
|» uuid|string|true|none|none|
|» sortOrder|integer|true|none|none|

<h3 id="tocSbundlebyuuid">BundleByUUID</h3>

<a id="schemabundlebyuuid"></a>

```json
{
  "payload": {
    "uuid": "string",
    "name": "string",
    "description": "string",
    "taxExempt": 0,
    "straightToPickup": true,
    "isPrintable": true,
    "hasEatInPrice": true,
    "price": 0,
    "priceFrom": 0,
    "priceEatInFrom": 0,
    "priceEatIn": 0,
    "upsellText": "string",
    "upsellItemTypeUUID": "string",
    "type": "CUSTOMISED",
    "tags": [
      {
        "uuid": "string",
        "name": "string"
      }
    ],
    "itemTypes": [
      {
        "uuid": "string",
        "name": "string",
        "sortOrder": 0,
        "minRestriction": 0,
        "maxRestriction": 0,
        "ticketGroup": "string",
        "isDefault": true,
        "isUpsellItemType": true,
        "items": [
          {
            "uuid": "string",
            "name": "string",
            "isPreselected": true,
            "isRequired": true,
            "sortOrder": 0,
            "price": "string",
            "basePrice": "string",
            "priceEatIn": "string",
            "hasEatInPrice": true,
            "itemModifiers": [
              {
                "uuid": "string",
                "meta": {},
                "modifier": {
                  "uuid": "string",
                  "name": "string",
                  "meta": {},
                  "slug": "string"
                },
                "itemModifierOptions": [
                  {
                    "uuid": "string",
                    "meta": {},
                    "measurementUnit": {},
                    "price": "string"
                  }
                ]
              }
            ]
          }
        ]
      }
    ],
    "menus": [
      {
        "uuid": "string",
        "name": "string",
        "isActive": true,
        "isSoldOut": true,
        "price": "string"
      }
    ]
  }
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|payload|object|true|none|none|
|» uuid|string|true|none|none|
|» name|string|true|none|none|
|» description|string|true|none|none|
|» taxExempt|number|true|none|none|
|» straightToPickup|boolean|true|none|none|
|» isPrintable|boolean|true|none|none|
|» hasEatInPrice|boolean|false|none|none|
|» price|number|false|none|none|
|» priceFrom|number|false|none|none|
|» priceEatInFrom|number|false|none|none|
|» priceEatIn|number|false|none|none|
|» upsellText|string|false|none|none|
|» upsellItemTypeUUID|string|false|none|none|
|» type|string|true|none|none|
|» tags|[object]|true|none|none|
|»» uuid|string|true|none|none|
|»» name|string|true|none|none|
|» itemTypes|[object]|true|none|none|
|»» uuid|string|true|none|none|
|»» name|string|true|none|none|
|»» sortOrder|integer|true|none|none|
|»» minRestriction|integer|true|none|none|
|»» maxRestriction|integer|true|none|none|
|»» ticketGroup|string|true|none|none|
|»» isDefault|boolean|true|none|none|
|»» isUpsellItemType|boolean|false|none|none|
|»» items|[object]|true|none|none|
|»»» uuid|string|true|none|none|
|»»» name|string|true|none|none|
|»»» isPreselected|boolean|true|none|none|
|»»» isRequired|boolean|true|none|none|
|»»» sortOrder|integer|true|none|none|
|»»» price|string|false|none|item price overrided by itemType|
|»»» basePrice|string|true|none|base item price, defined on create/update item(management)|
|»»» priceEatIn|string|true|none|eatIn item price, defined on create/update item(management)|
|»»» hasEatInPrice|boolean|true|none|hasEatInPrice flag, defined on create/update item(management)|
|»»» itemModifiers|[object]|true|none|none|
|»»»» uuid|string|true|none|none|
|»»»» meta|object|false|none|none|
|»»»» modifier|object|true|none|none|
|»»»»» uuid|string|true|none|none|
|»»»»» name|string|true|none|none|
|»»»»» meta|object|false|none|none|
|»»»»» slug|string|false|none|none|
|»»»» itemModifierOptions|[object]|true|none|none|
|»»»»» uuid|string|true|none|none|
|»»»»» meta|object|false|none|none|
|»»»»» measurementUnit|object|false|none|none|
|»»»»» price|string|false|none|none|
|»»»» menus|[object]|true|none|none|
|»»»»» uuid|string|true|none|none|
|»»»»» name|string|true|none|none|
|»»»»» isActive|boolean|true|none|none|
|»»»»» isSoldOut|boolean|true|none|none|
|»»»»» price|string|false|none|none|

#### Enumerated Values

|Property|Value|
|---|---|
|type|CUSTOMISED|
|type|VIRTUAL|
|type|BUILD_YOUR_OWN|
|type|FIXED_PRICE|

<h3 id="tocSmenumodel">MenuModel</h3>

<a id="schemamenumodel"></a>

```json
{
  "payload": [
    {
      "name": "string",
      "uuid": "string",
      "sortOrder": 0,
      "currentDayWorkHours": {
        "weekday": 0,
        "from": "string",
        "to": "string"
      },
      "categories": [
        {
          "name": "string",
          "uuid": "string",
          "sortOrder": 0,
          "type": "string"
        }
      ]
    }
  ]
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|payload|[object]|true|none|none|
|» name|string|true|none|none|
|» uuid|string|true|none|none|
|» sortOrder|integer|true|none|none|
|» currentDayWorkHours|object|true|none|none|
|»» weekday|number|true|none|none|
|»» from|string|true|none|none|
|»» to|string|true|none|none|
|» categories|[object]|true|none|none|
|»» name|string|true|none|none|
|»» uuid|string|true|none|none|
|»» sortOrder|integer|true|none|none|
|»» type|string|true|none|none|

<h3 id="tocSmanagementbundleuuid">ManagementBundleUUID</h3>

<a id="schemamanagementbundleuuid"></a>

```json
{
  "payload": "string"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|payload|string|true|none|none|

