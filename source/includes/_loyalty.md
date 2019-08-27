---
title: Loyalty Service
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

<h1 id="loyalty-service">Loyalty Service</h1>

> Scroll down for code samples, example requests and responses. Select a language for code samples from the tabs above or the mobile navigation menu.

The Loyalty Service API Documentation

<h2 id="loyalty-service-default">Default</h2>

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

<h2 id="loyalty-service-promotions">promotions</h2>

### Get Promotions

<a id="opIdGet Promotions"></a>

> Code samples

```shell
# You can also use wget
curl -X GET /promotions \
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
  url: '/promotions',
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

fetch('/promotions',
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

r = requests.get('/promotions', params={

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

result = RestClient.get '/promotions',
  params: {
  }, headers: headers

p JSON.parse(result)

```

`GET /promotions`

Get a list of promotions active for store

<h4 id="get-promotions-parameters">Parameters</h4>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|store|header|string|true|External Store UUID (876b34ad-45654-4ds7-cdd8-bfc47686d999)|

> Example responses

> 200 Response

```json
{
  "payload": [
    {
      "uuid": "111-111-222-333",
      "value": 2,
      "type": "fixed",
      "name": "Summer promo"
    },
    {
      "uuid": "222-333-111-111",
      "value": 25,
      "type": "percentage",
      "name": "Summer promo 2"
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

<h4 id="get-promotions-responses">Responses</h4>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|none|[PromotionsModel](#schemapromotionsmodel)|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|none|[BadRequestError](#schemabadrequesterror)|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|none|[UnauthorizedError](#schemaunauthorizederror)|
|403|[Forbidden](https://tools.ietf.org/html/rfc7231#section-6.5.3)|none|[ForbiddenError](#schemaforbiddenerror)|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|none|[InternalServerError](#schemainternalservererror)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
bearer ( Scopes: ADMINISTRATOR MANAGER STAFF )
</aside>

### Get Promotion

<a id="opIdGet Promotion"></a>

> Code samples

```shell
# You can also use wget
curl -X GET /promotions/{promotionUUID} \
  -H 'Accept: application/json' \
  -H 'Authorization: API_KEY'

```

```javascript
var headers = {
  'Accept':'application/json',
  'Authorization':'API_KEY'

};

$.ajax({
  url: '/promotions/{promotionUUID}',
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

fetch('/promotions/{promotionUUID}',
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

r = requests.get('/promotions/{promotionUUID}', params={

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

result = RestClient.get '/promotions/{promotionUUID}',
  params: {
  }, headers: headers

p JSON.parse(result)

```

`GET /promotions/{promotionUUID}`

Get s promotion by ID

<h4 id="get-promotion-parameters">Parameters</h4>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|promotionUUID|path|string|true|none|

> Example responses

> 200 Response

```json
{
  "payload": {
    "uuid": "111-111-222-333",
    "value": 2,
    "type": "fixed",
    "name": "Summer promo"
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

<h4 id="get-promotion-responses">Responses</h4>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|none|[PromotionModel](#schemapromotionmodel)|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|none|[BadRequestError](#schemabadrequesterror)|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|none|[UnauthorizedError](#schemaunauthorizederror)|
|403|[Forbidden](https://tools.ietf.org/html/rfc7231#section-6.5.3)|none|[ForbiddenError](#schemaforbiddenerror)|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|none|[InternalServerError](#schemainternalservererror)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
bearer ( Scopes: ADMINISTRATOR MANAGER STAFF )
</aside>

### Validate Promotions

<a id="opIdValidate Promotions"></a>

> Code samples

```shell
# You can also use wget
curl -X POST /promotions/validate \
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
  url: '/promotions/validate',
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
      "basketUUID": "string",
      "finalPrice": 0,
      "subtotalAmount": 0,
      "promotion": {
        "uuid": "string",
        "name": "string",
        "value": 0,
        "type": "string"
      }
    }
  ]
}';
const headers = {
  'Content-Type':'application/json',
  'Accept':'application/json',
  'store':'string',
  'Authorization':'API_KEY'

};

fetch('/promotions/validate',
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

r = requests.post('/promotions/validate', params={

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

result = RestClient.post '/promotions/validate',
  params: {
  }, headers: headers

p JSON.parse(result)

```

`POST /promotions/validate`

Validates a list of products with applied promotions.

> Body parameter

```json
{
  "products": [
    {
      "uuid": "string",
      "basketUUID": "string",
      "finalPrice": 0,
      "subtotalAmount": 0,
      "promotion": {
        "uuid": "string",
        "name": "string",
        "value": 0,
        "type": "string"
      }
    }
  ]
}
```

<h4 id="validate-promotions-parameters">Parameters</h4>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|store|header|string|true|External Store UUID (876b34ad-45654-4ds7-cdd8-bfc47686d999)|
|body|body|[ProductsModel](#schemaproductsmodel)|true|none|

> Example responses

> 200 Response

```json
{
  "status": true
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

<h4 id="validate-promotions-responses">Responses</h4>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|none|Inline|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|none|[BadRequestError](#schemabadrequesterror)|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|none|[UnauthorizedError](#schemaunauthorizederror)|
|403|[Forbidden](https://tools.ietf.org/html/rfc7231#section-6.5.3)|none|[ForbiddenError](#schemaforbiddenerror)|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|none|[InternalServerError](#schemainternalservererror)|

<h4 id="validate-promotions-responseschema">Response Schema</h4>

Status Code **200**

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» status|boolean|true|none|none|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
bearer ( Scopes: ADMINISTRATOR MANAGER STAFF )
</aside>

### Apply Promotion

<a id="opIdApply Promotion"></a>

> Code samples

```shell
# You can also use wget
curl -X POST /promotions/{promotionUUID}/apply \
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
  url: '/promotions/{promotionUUID}/apply',
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
      "finalPrice": 0,
      "subtotalAmount": 0,
      "basketUUID": "string",
      "promotion": {
        "uuid": "string",
        "name": "string",
        "value": 0,
        "type": "string"
      }
    }
  ]
}';
const headers = {
  'Content-Type':'application/json',
  'Accept':'application/json',
  'store':'string',
  'Authorization':'API_KEY'

};

fetch('/promotions/{promotionUUID}/apply',
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

r = requests.post('/promotions/{promotionUUID}/apply', params={

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

result = RestClient.post '/promotions/{promotionUUID}/apply',
  params: {
  }, headers: headers

p JSON.parse(result)

```

`POST /promotions/{promotionUUID}/apply`

Apply a promotion to a list of producs

> Body parameter

```json
{
  "products": [
    {
      "uuid": "string",
      "finalPrice": 0,
      "subtotalAmount": 0,
      "basketUUID": "string",
      "promotion": {
        "uuid": "string",
        "name": "string",
        "value": 0,
        "type": "string"
      }
    }
  ]
}
```

<h4 id="apply-promotion-parameters">Parameters</h4>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|store|header|string|true|External Store UUID (876b34ad-45654-4ds7-cdd8-bfc47686d999)|
|body|body|[RequestProductsPromoApplyModel](#schemarequestproductspromoapplymodel)|true|none|
|promotionUUID|path|string|true|none|

> Example responses

> 200 Response

```json
{
  "payload": [
    {
      "uuid": "111",
      "type": "VIRTUAL",
      "basketUUID": "222",
      "finalPrice": 10,
      "promotion": {
        "uuid": "111",
        "type": "fixed",
        "value": 10
      }
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

<h4 id="apply-promotion-responses">Responses</h4>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|none|[ProductsPromoApplyModel](#schemaproductspromoapplymodel)|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|none|[BadRequestError](#schemabadrequesterror)|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|none|[UnauthorizedError](#schemaunauthorizederror)|
|403|[Forbidden](https://tools.ietf.org/html/rfc7231#section-6.5.3)|none|[ForbiddenError](#schemaforbiddenerror)|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|none|[InternalServerError](#schemainternalservererror)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
bearer ( Scopes: ADMINISTRATOR MANAGER STAFF )
</aside>

## Schemas

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

<h3 id="tocSpromotionsmodel">PromotionsModel</h3>

<a id="schemapromotionsmodel"></a>

```json
{
  "payload": [
    {
      "uuid": "string",
      "name": "string",
      "isActive": true
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

<h3 id="tocSpromotionmodel">PromotionModel</h3>

<a id="schemapromotionmodel"></a>

```json
{
  "payload": {
    "uuid": "string",
    "name": "string",
    "isActive": true,
    "value": 0,
    "type": "string"
  }
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|payload|object|true|none|none|
|» uuid|string|true|none|none|
|» name|string|true|none|none|
|» isActive|boolean|true|none|none|
|» value|number|true|none|none|
|» type|string|true|none|none|

<h3 id="tocSproductsmodel">ProductsModel</h3>

<a id="schemaproductsmodel"></a>

```json
{
  "products": [
    {
      "uuid": "string",
      "basketUUID": "string",
      "finalPrice": 0,
      "subtotalAmount": 0,
      "promotion": {
        "uuid": "string",
        "name": "string",
        "value": 0,
        "type": "string"
      }
    }
  ]
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|products|[object]|true|none|none|
|» uuid|string|true|none|none|
|» basketUUID|string|true|none|none|
|» finalPrice|number|true|none|none|
|» subtotalAmount|number|true|none|none|
|» promotion|object|false|none|none|
|»» uuid|string|true|none|none|
|»» name|string|false|none|none|
|»» value|number|true|none|none|
|»» type|string|true|none|none|

<h3 id="tocSrequestproductspromoapplymodel">RequestProductsPromoApplyModel</h3>

<a id="schemarequestproductspromoapplymodel"></a>

```json
{
  "products": [
    {
      "uuid": "string",
      "finalPrice": 0,
      "subtotalAmount": 0,
      "basketUUID": "string",
      "promotion": {
        "uuid": "string",
        "name": "string",
        "value": 0,
        "type": "string"
      }
    }
  ]
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|products|[object]|true|none|none|
|» uuid|string|true|none|none|
|» finalPrice|number|true|none|none|
|» subtotalAmount|number|true|none|none|
|» basketUUID|string|true|none|none|
|» promotion|object|false|none|none|
|»» uuid|string|true|none|none|
|»» name|string|false|none|none|
|»» value|number|true|none|none|
|»» type|string|true|none|none|

<h3 id="tocSproductspromoapplymodel">ProductsPromoApplyModel</h3>

<a id="schemaproductspromoapplymodel"></a>

```json
{
  "payload": [
    {
      "uuid": "string",
      "finalPrice": 0,
      "subtotalAmount": 0,
      "basketUUID": "string",
      "promotion": {
        "uuid": "string",
        "name": "string",
        "value": 0,
        "type": "string"
      }
    }
  ]
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|payload|[object]|true|none|none|
|» uuid|string|true|none|none|
|» finalPrice|number|true|none|none|
|» subtotalAmount|number|true|none|none|
|» basketUUID|string|true|none|none|
|» promotion|object|true|none|none|
|»» uuid|string|true|none|none|
|»» name|string|true|none|none|
|»» value|number|true|none|none|
|»» type|string|true|none|none|

