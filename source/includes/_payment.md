---
title: Payment Service
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

<h1 id="payment-service">Payment Service</h1>

> Scroll down for code samples, example requests and responses. Select a language for code samples from the tabs above or the mobile navigation menu.

Payment Service API

<h2 id="payment-service-healthcheck">Healthcheck</h2>

### GET_healthcheck

<a id="opIdGET_healthcheck"></a>

> Code samples

```shell
# You can also use wget
curl -X GET /healthcheck \
  -H 'Accept: application/json; charset=utf-8'

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

```javascript--nodejs
const fetch = require('node-fetch');

const headers = {
  'Accept':'application/json; charset=utf-8'

};

fetch('/healthcheck',
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
  'Accept': 'application/json; charset=utf-8'
}

r = requests.get('/healthcheck', params={

}, headers = headers)

print r.json()

```

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

`GET /healthcheck`

*Check API health*

> Example responses

> 200 Response

```json
{}
```

<h4 id="get_healthcheck-responses">Responses</h4>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|none|Inline|

<h4 id="get_healthcheck-responseschema">Response Schema</h4>

<aside class="success">
This operation does not require authentication
</aside>

<h2 id="payment-service-transactions">Transactions</h2>

### Create Transaction

<a id="opIdCreate Transaction"></a>

> Code samples

```shell
# You can also use wget
curl -X POST /v1/transactions/order \
  -H 'Content-Type: application/json; charset=utf-8' \
  -H 'Accept: application/json; charset=utf-8' \
  -H 'Authorization: API_KEY'

```

```javascript
var headers = {
  'Content-Type':'application/json; charset=utf-8',
  'Accept':'application/json; charset=utf-8',
  'Authorization':'API_KEY'

};

$.ajax({
  url: '/v1/transactions/order',
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
  "order": {
    "required": "string"
  },
  "providerUUID": "string",
  "card": {
    "id": "string",
    "token": "string"
  },
  "currency": "string",
  "meta": {}
}';
const headers = {
  'Content-Type':'application/json; charset=utf-8',
  'Accept':'application/json; charset=utf-8',
  'Authorization':'API_KEY'

};

fetch('/v1/transactions/order',
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
  'Content-Type': 'application/json; charset=utf-8',
  'Accept': 'application/json; charset=utf-8',
  'Authorization': 'API_KEY'
}

r = requests.post('/v1/transactions/order', params={

}, headers = headers)

print r.json()

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Content-Type' => 'application/json; charset=utf-8',
  'Accept' => 'application/json; charset=utf-8',
  'Authorization' => 'API_KEY'
}

result = RestClient.post '/v1/transactions/order',
  params: {
  }, headers: headers

p JSON.parse(result)

```

`POST /v1/transactions/order`

*Create order transaction*

Deep integrations only! Register a payment for order

> Body parameter

```json
{
  "order": {
    "required": "string"
  },
  "providerUUID": "string",
  "card": {
    "id": "string",
    "token": "string"
  },
  "currency": "string",
  "meta": {}
}
```

<h4 id="create-transaction-parameters">Parameters</h4>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|[transactionReq](#schematransactionreq)|true|none|

> Example responses

> 201 Response

```json
{
  "payload": {
    "uuid": "6bf3a91d-56d2-48ec-8a3d-8080ecc7a39f",
    "orderUUID": "84544519-8919-48d6-ae7f-04f1a2058edb",
    "transaction": "yEE1u9axI3RXxlRDutGui",
    "type": "intent",
    "amount": 5.25,
    "currency": "gbp",
    "failureCode": null,
    "failureMessage": null,
    "status": "pending",
    "meta": null,
    "createdAt": "2019-01-02T12:15:36.000Z",
    "details": {
      "clientSecret": "pi_1Ejm0WJYShqG0xF5yVIbINbl_secret_q7IyDjD6ntyeAeGMlrtQYIrlW"
    }
  }
}
```

<h4 id="create-transaction-responses">Responses</h4>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|201|[Created](https://tools.ietf.org/html/rfc7231#section-6.3.2)|none|[transaction](#schematransaction)|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|none|None|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Not authenticated to perform this action|None|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
bearer ( Scopes: ADMINISTRATOR MANAGER STAFF CUSTOMER ), bearer
</aside>

### Create Refund

<a id="opIdCreate Refund"></a>

> Code samples

```shell
# You can also use wget
curl -X GET /v1/transactions/order/{uuid} \
  -H 'Accept: application/json; charset=utf-8' \
  -H 'Authorization: API_KEY'

```

```javascript
var headers = {
  'Accept':'application/json; charset=utf-8',
  'Authorization':'API_KEY'

};

$.ajax({
  url: '/v1/transactions/order/{uuid}',
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
  'Accept':'application/json; charset=utf-8',
  'Authorization':'API_KEY'

};

fetch('/v1/transactions/order/{uuid}',
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
  'Accept': 'application/json; charset=utf-8',
  'Authorization': 'API_KEY'
}

r = requests.get('/v1/transactions/order/{uuid}', params={

}, headers = headers)

print r.json()

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json; charset=utf-8',
  'Authorization' => 'API_KEY'
}

result = RestClient.get '/v1/transactions/order/{uuid}',
  params: {
  }, headers: headers

p JSON.parse(result)

```

`GET /v1/transactions/order/{uuid}`

*Get all transactions by order UUID, status and type*

Get all transactions by order UUID, status and type

<h4 id="create-refund-parameters">Parameters</h4>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|status|query|array[string]|false|Filter results by transaction status|
|types|query|array[string]|false|Filter results by transaction type|
|uuid|path|string|true|Order UUID|

#### Enumerated Values

|Parameter|Value|
|---|---|
|status|success|
|status|failed|
|types|charge|
|types|refund|

> Example responses

> 200 Response

```json
{
  "payload": [
    {
      "uuid": "6bf3a91d-56d2-48ec-8a3d-8080ecc7a39f",
      "orderUUID": "84544519-8919-48d6-ae7f-04f1a2058edb",
      "transaction": "yEE1u9axI3RXxlRDutGui",
      "type": "charge",
      "amount": 5.25,
      "currency": "gbp",
      "failureCode": null,
      "failureMessage": null,
      "status": "success",
      "meta": null,
      "createdAt": "2019-01-02T12:15:36.000Z",
      "provider": {
        "uuid": "d2e71110-d57c-431f-99d3-c7bd50537ee1",
        "slug": "stripe",
        "sdk": "https://js.stripe.com/v3/",
        "supportCards": true,
        "createCustomer": true
      }
    },
    {
      "uuid": "fe3e0461-529d-4769-8cd3-b9b338f34b09",
      "orderUUID": "84544519-8919-48d6-ae7f-04f1a2058edb",
      "transaction": "a3d733ad-6924-43b6-aa14-ad6e755b9544",
      "type": "refund",
      "amount": 5.25,
      "currency": "gbp",
      "failureCode": null,
      "failureMessage": null,
      "status": "success",
      "meta": null,
      "createdAt": "2019-01-03T12:15:36.000Z",
      "provider": {
        "uuid": "d2e71110-d57c-431f-99d3-c7bd50537ee1",
        "slug": "stripe",
        "sdk": "https://js.stripe.com/v3/",
        "supportCards": true,
        "createCustomer": true
      }
    }
  ]
}
```

<h4 id="create-refund-responses">Responses</h4>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|none|[transactions](#schematransactions)|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|none|None|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Not authenticated to perform this action|None|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
bearer ( Scopes: ADMINISTRATOR MANAGER STAFF CUSTOMER ), bearer
</aside>

### Is Refundable

<a id="opIdIs Refundable"></a>

> Code samples

```shell
# You can also use wget
curl -X GET /v1/transactions/order/{uuid}/is-refundable \
  -H 'Accept: application/json; charset=utf-8' \
  -H 'Authorization: API_KEY'

```

```javascript
var headers = {
  'Accept':'application/json; charset=utf-8',
  'Authorization':'API_KEY'

};

$.ajax({
  url: '/v1/transactions/order/{uuid}/is-refundable',
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
  'Accept':'application/json; charset=utf-8',
  'Authorization':'API_KEY'

};

fetch('/v1/transactions/order/{uuid}/is-refundable',
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
  'Accept': 'application/json; charset=utf-8',
  'Authorization': 'API_KEY'
}

r = requests.get('/v1/transactions/order/{uuid}/is-refundable', params={

}, headers = headers)

print r.json()

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json; charset=utf-8',
  'Authorization' => 'API_KEY'
}

result = RestClient.get '/v1/transactions/order/{uuid}/is-refundable',
  params: {
  }, headers: headers

p JSON.parse(result)

```

`GET /v1/transactions/order/{uuid}/is-refundable`

*Check if transaction is refundable*

Check if transaction is refundable

<h4 id="is-refundable-parameters">Parameters</h4>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|uuid|path|string|true|Order UUID|

> Example responses

> 200 Response

```json
{
  "payload": {
    "isRefundable": true
  }
}
```

<h4 id="is-refundable-responses">Responses</h4>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|none|[transactionRefundable](#schematransactionrefundable)|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|none|None|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Not authenticated to perform this action|None|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
bearer ( Scopes: ADMINISTRATOR MANAGER STAFF CUSTOMER ), bearer
</aside>

### Transaction Details

<a id="opIdTransaction Details"></a>

> Code samples

```shell
# You can also use wget
curl -X GET /v1/transactions/order/{uuid}/details \
  -H 'Accept: application/json; charset=utf-8' \
  -H 'Authorization: API_KEY'

```

```javascript
var headers = {
  'Accept':'application/json; charset=utf-8',
  'Authorization':'API_KEY'

};

$.ajax({
  url: '/v1/transactions/order/{uuid}/details',
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
  'Accept':'application/json; charset=utf-8',
  'Authorization':'API_KEY'

};

fetch('/v1/transactions/order/{uuid}/details',
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
  'Accept': 'application/json; charset=utf-8',
  'Authorization': 'API_KEY'
}

r = requests.get('/v1/transactions/order/{uuid}/details', params={

}, headers = headers)

print r.json()

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json; charset=utf-8',
  'Authorization' => 'API_KEY'
}

result = RestClient.get '/v1/transactions/order/{uuid}/details',
  params: {
  }, headers: headers

p JSON.parse(result)

```

`GET /v1/transactions/order/{uuid}/details`

*Get charge transaction details by order*

Get charge transaction details by order

<h4 id="transaction-details-parameters">Parameters</h4>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|uuid|path|string|true|Order UUID|

> Example responses

> 200 Response

```json
{
  "payload": {
    "orderUUID": "84544519-8919-48d6-ae7f-04f1a2058edb",
    "transaction": "yEE1u9axI3RXxlRDutGui",
    "type": "charge",
    "amount": 5.25,
    "currency": "gbp",
    "failureCode": null,
    "failureMessage": null,
    "status": "success",
    "meta": null,
    "createdAt": "2019-01-02T12:15:36.000Z",
    "details": {
      "card": {
        "id": "card_1CeJxCJYShqG0xF5kqbTRzpB",
        "brand": "Mastercard",
        "last4": "3232",
        "expYear": 2019,
        "expMonth": 10,
        "tokenizationMethod": "apple_pay"
      }
    }
  }
}
```

<h4 id="transaction-details-responses">Responses</h4>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|none|[transactionDetails](#schematransactiondetails)|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|none|None|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Not authenticated to perform this action|None|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
bearer ( Scopes: ADMINISTRATOR MANAGER STAFF CUSTOMER ), bearer
</aside>

<h2 id="payment-service-providers">Providers</h2>

### Get Proviers

<a id="opIdGet Proviers"></a>

> Code samples

```shell
# You can also use wget
curl -X GET /v1/providers \
  -H 'Accept: application/json; charset=utf-8' \
  -H 'tenant: string'

```

```javascript
var headers = {
  'Accept':'application/json; charset=utf-8',
  'tenant':'string'

};

$.ajax({
  url: '/v1/providers',
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
  'Accept':'application/json; charset=utf-8',
  'tenant':'string'

};

fetch('/v1/providers',
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
  'Accept': 'application/json; charset=utf-8',
  'tenant': 'string'
}

r = requests.get('/v1/providers', params={

}, headers = headers)

print r.json()

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json; charset=utf-8',
  'tenant' => 'string'
}

result = RestClient.get '/v1/providers',
  params: {
  }, headers: headers

p JSON.parse(result)

```

`GET /v1/providers`

*Get providers*

Deep integrations only! Get available payment providers for tenant

<h4 id="get-proviers-parameters">Parameters</h4>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|tenant|header|string|true|External tenant UUID|

> Example responses

> 200 Response

```json
{
  "payload": [
    {
      "uuid": "d2e71110-d57c-431f-99d3-c7bd50537ee1",
      "slug": "stripe",
      "sdk": "https://js.stripe.com/v3/",
      "supportCards": true,
      "createCustomer": true,
      "config": {
        "apiKey": "pk_test_IwHwDqRSgwLldCU3uuuBxQiD",
        "status": true,
        "isDefault": true,
        "currency": "gbp"
      }
    },
    {
      "uuid": "b5966827-0e3e-4dc9-8f2e-ba0c5145f764",
      "slug": "izettle",
      "sdk": null,
      "supportCards": false,
      "createCustomer": false,
      "config": {
        "apiKey": null,
        "status": true,
        "isDefault": false,
        "currency": "gbp"
      }
    }
  ]
}
```

<h4 id="get-proviers-responses">Responses</h4>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|none|[tenantProviders](#schematenantproviders)|

<aside class="success">
This operation does not require authentication
</aside>

### Create Customer

<a id="opIdCreate Customer"></a>

> Code samples

```shell
# You can also use wget
curl -X POST /v1/providers/customer \
  -H 'Authorization: API_KEY'

```

```javascript
var headers = {
  'Authorization':'API_KEY'

};

$.ajax({
  url: '/v1/providers/customer',
  method: 'post',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

```javascript--nodejs
const fetch = require('node-fetch');

const headers = {
  'Authorization':'API_KEY'

};

fetch('/v1/providers/customer',
{
  method: 'POST',

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
  'Authorization': 'API_KEY'
}

r = requests.post('/v1/providers/customer', params={

}, headers = headers)

print r.json()

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Authorization' => 'API_KEY'
}

result = RestClient.post '/v1/providers/customer',
  params: {
  }, headers: headers

p JSON.parse(result)

```

`POST /v1/providers/customer`

*Create customer by provider*

Deep integrations only! Create customer profile for providers

<h4 id="create-customer-responses">Responses</h4>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|403|[Forbidden](https://tools.ietf.org/html/rfc7231#section-6.5.3)|Not authorized to perform this action|None|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
bearer ( Scopes: CUSTOMER )
</aside>

<h2 id="payment-service-customer-cards">Customer Cards</h2>

### Get Cards

<a id="opIdGet Cards"></a>

> Code samples

```shell
# You can also use wget
curl -X GET /v1/cards \
  -H 'Accept: application/json; charset=utf-8' \
  -H 'Authorization: API_KEY'

```

```javascript
var headers = {
  'Accept':'application/json; charset=utf-8',
  'Authorization':'API_KEY'

};

$.ajax({
  url: '/v1/cards',
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
  'Accept':'application/json; charset=utf-8',
  'Authorization':'API_KEY'

};

fetch('/v1/cards',
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
  'Accept': 'application/json; charset=utf-8',
  'Authorization': 'API_KEY'
}

r = requests.get('/v1/cards', params={

}, headers = headers)

print r.json()

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json; charset=utf-8',
  'Authorization' => 'API_KEY'
}

result = RestClient.get '/v1/cards',
  params: {
  }, headers: headers

p JSON.parse(result)

```

`GET /v1/cards`

*Get customer cards*

Deep integrations only! Get a list of saved cards. These will be card references and not actual card details.

> Example responses

> 200 Response

```json
{
  "payload": [
    {
      "id": "card_1CeJxCJYShqG0xF5kqbTRzpV",
      "brand": "Visa",
      "last4": "4242",
      "expYear": 2019,
      "expMonth": 8,
      "tokenizationMethod": null,
      "provider": "stripe",
      "isDefault": true
    },
    {
      "id": "card_1CeJxCJYShqG0xF5kqbTRzpB",
      "brand": "Mastercard",
      "last4": "3232",
      "expYear": 2019,
      "expMonth": 10,
      "tokenizationMethod": "apple_pay",
      "provider": "stripe",
      "isDefault": false
    },
    {
      "id": "card_1CeJxCJYShqG0xF5kqbTRzpA",
      "brand": "HSBC",
      "last4": "5454",
      "expYear": 2019,
      "expMonth": 12,
      "tokenizationMethod": null,
      "provider": "stripe",
      "isDefault": false
    }
  ]
}
```

<h4 id="get-cards-responses">Responses</h4>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|none|[cards](#schemacards)|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|none|None|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Not authenticated to perform this action|None|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
bearer ( Scopes: CUSTOMER ), bearer
</aside>

### Link Card to Customer

<a id="opIdLink Card to Customer"></a>

> Code samples

```shell
# You can also use wget
curl -X POST /v1/cards \
  -H 'Content-Type: application/json; charset=utf-8' \
  -H 'Accept: application/json; charset=utf-8' \
  -H 'Authorization: API_KEY'

```

```javascript
var headers = {
  'Content-Type':'application/json; charset=utf-8',
  'Accept':'application/json; charset=utf-8',
  'Authorization':'API_KEY'

};

$.ajax({
  url: '/v1/cards',
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
  "token": "string",
  "providerUUID": "string"
}';
const headers = {
  'Content-Type':'application/json; charset=utf-8',
  'Accept':'application/json; charset=utf-8',
  'Authorization':'API_KEY'

};

fetch('/v1/cards',
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
  'Content-Type': 'application/json; charset=utf-8',
  'Accept': 'application/json; charset=utf-8',
  'Authorization': 'API_KEY'
}

r = requests.post('/v1/cards', params={

}, headers = headers)

print r.json()

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Content-Type' => 'application/json; charset=utf-8',
  'Accept' => 'application/json; charset=utf-8',
  'Authorization' => 'API_KEY'
}

result = RestClient.post '/v1/cards',
  params: {
  }, headers: headers

p JSON.parse(result)

```

`POST /v1/cards`

*Create customer card*

Deep integrations only! Links a card token to curent customer.

> Body parameter

```json
{
  "token": "string",
  "providerUUID": "string"
}
```

<h4 id="link-card-to-customer-parameters">Parameters</h4>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|[cardReq](#schemacardreq)|true|none|

> Example responses

> 201 Response

```json
{
  "payload": [
    {
      "id": "card_1CeJxCJYShqG0xF5kqbTRzpV",
      "brand": "Visa",
      "last4": "4242",
      "expYear": 2019,
      "expMonth": 8,
      "tokenizationMethod": null,
      "provider": "stripe",
      "isDefault": true
    },
    {
      "id": "card_1CeJxCJYShqG0xF5kqbTRzpB",
      "brand": "Mastercard",
      "last4": "3232",
      "expYear": 2019,
      "expMonth": 10,
      "tokenizationMethod": "apple_pay",
      "provider": "stripe",
      "isDefault": false
    },
    {
      "id": "card_1CeJxCJYShqG0xF5kqbTRzpA",
      "brand": "HSBC",
      "last4": "5454",
      "expYear": 2019,
      "expMonth": 12,
      "tokenizationMethod": null,
      "provider": "stripe",
      "isDefault": false
    }
  ]
}
```

<h4 id="link-card-to-customer-responses">Responses</h4>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|201|[Created](https://tools.ietf.org/html/rfc7231#section-6.3.2)|none|[cards](#schemacards)|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|none|None|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Not authenticated to perform this action|None|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
bearer ( Scopes: CUSTOMER ), bearer
</aside>

### Get Card

<a id="opIdGet Card"></a>

> Code samples

```shell
# You can also use wget
curl -X GET /v1/cards/{cardId} \
  -H 'Accept: application/json; charset=utf-8' \
  -H 'Authorization: API_KEY'

```

```javascript
var headers = {
  'Accept':'application/json; charset=utf-8',
  'Authorization':'API_KEY'

};

$.ajax({
  url: '/v1/cards/{cardId}',
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
  'Accept':'application/json; charset=utf-8',
  'Authorization':'API_KEY'

};

fetch('/v1/cards/{cardId}',
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
  'Accept': 'application/json; charset=utf-8',
  'Authorization': 'API_KEY'
}

r = requests.get('/v1/cards/{cardId}', params={

}, headers = headers)

print r.json()

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json; charset=utf-8',
  'Authorization' => 'API_KEY'
}

result = RestClient.get '/v1/cards/{cardId}',
  params: {
  }, headers: headers

p JSON.parse(result)

```

`GET /v1/cards/{cardId}`

*Get customer card by card ID*

Deep integrations only! Get card by id.

<h4 id="get-card-parameters">Parameters</h4>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|cardId|path|string|true|Card ID|

> Example responses

> 200 Response

```json
{
  "payload": {
    "id": "card_1CeJxCJYShqG0xF5kqbTRzpB",
    "brand": "Mastercard",
    "last4": "3232",
    "expYear": 2019,
    "expMonth": 10,
    "tokenizationMethod": "apple_pay",
    "provider": "stripe",
    "isDefault": false
  }
}
```

<h4 id="get-card-responses">Responses</h4>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|none|[card](#schemacard)|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|none|None|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Not authenticated to perform this action|None|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
bearer ( Scopes: CUSTOMER ), bearer
</aside>

### Default Card

<a id="opIdDefault Card"></a>

> Code samples

```shell
# You can also use wget
curl -X PATCH /v1/cards/{cardId} \
  -H 'Accept: application/json; charset=utf-8' \
  -H 'Authorization: API_KEY'

```

```javascript
var headers = {
  'Accept':'application/json; charset=utf-8',
  'Authorization':'API_KEY'

};

$.ajax({
  url: '/v1/cards/{cardId}',
  method: 'patch',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

```javascript--nodejs
const fetch = require('node-fetch');

const headers = {
  'Accept':'application/json; charset=utf-8',
  'Authorization':'API_KEY'

};

fetch('/v1/cards/{cardId}',
{
  method: 'PATCH',

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
  'Accept': 'application/json; charset=utf-8',
  'Authorization': 'API_KEY'
}

r = requests.patch('/v1/cards/{cardId}', params={

}, headers = headers)

print r.json()

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json; charset=utf-8',
  'Authorization' => 'API_KEY'
}

result = RestClient.patch '/v1/cards/{cardId}',
  params: {
  }, headers: headers

p JSON.parse(result)

```

`PATCH /v1/cards/{cardId}`

*Set customer default card*

Deep integrations only! Set customer default card

<h4 id="default-card-parameters">Parameters</h4>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|cardId|path|string|true|Card ID|

> Example responses

> 200 Response

```json
{
  "payload": [
    {
      "id": "card_1CeJxCJYShqG0xF5kqbTRzpV",
      "brand": "Visa",
      "last4": "4242",
      "expYear": 2019,
      "expMonth": 8,
      "tokenizationMethod": null,
      "provider": "stripe",
      "isDefault": true
    },
    {
      "id": "card_1CeJxCJYShqG0xF5kqbTRzpB",
      "brand": "Mastercard",
      "last4": "3232",
      "expYear": 2019,
      "expMonth": 10,
      "tokenizationMethod": "apple_pay",
      "provider": "stripe",
      "isDefault": false
    },
    {
      "id": "card_1CeJxCJYShqG0xF5kqbTRzpA",
      "brand": "HSBC",
      "last4": "5454",
      "expYear": 2019,
      "expMonth": 12,
      "tokenizationMethod": null,
      "provider": "stripe",
      "isDefault": false
    }
  ]
}
```

<h4 id="default-card-responses">Responses</h4>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|none|[cards](#schemacards)|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|none|None|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Not authenticated to perform this action|None|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
bearer ( Scopes: CUSTOMER ), bearer
</aside>

### Delete Card

<a id="opIdDelete Card"></a>

> Code samples

```shell
# You can also use wget
curl -X DELETE /v1/cards/{cardId} \
  -H 'Accept: application/json; charset=utf-8' \
  -H 'Authorization: API_KEY'

```

```javascript
var headers = {
  'Accept':'application/json; charset=utf-8',
  'Authorization':'API_KEY'

};

$.ajax({
  url: '/v1/cards/{cardId}',
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
  'Accept':'application/json; charset=utf-8',
  'Authorization':'API_KEY'

};

fetch('/v1/cards/{cardId}',
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
  'Accept': 'application/json; charset=utf-8',
  'Authorization': 'API_KEY'
}

r = requests.delete('/v1/cards/{cardId}', params={

}, headers = headers)

print r.json()

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json; charset=utf-8',
  'Authorization' => 'API_KEY'
}

result = RestClient.delete '/v1/cards/{cardId}',
  params: {
  }, headers: headers

p JSON.parse(result)

```

`DELETE /v1/cards/{cardId}`

*Delete customer card by card ID*

Deep integrations only! Delete customer card

<h4 id="delete-card-parameters">Parameters</h4>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|cardId|path|string|true|Card ID|

> Example responses

> 200 Response

```json
{
  "payload": [
    {
      "id": "card_1CeJxCJYShqG0xF5kqbTRzpV",
      "brand": "Visa",
      "last4": "4242",
      "expYear": 2019,
      "expMonth": 8,
      "tokenizationMethod": null,
      "provider": "stripe",
      "isDefault": true
    },
    {
      "id": "card_1CeJxCJYShqG0xF5kqbTRzpB",
      "brand": "Mastercard",
      "last4": "3232",
      "expYear": 2019,
      "expMonth": 10,
      "tokenizationMethod": "apple_pay",
      "provider": "stripe",
      "isDefault": false
    },
    {
      "id": "card_1CeJxCJYShqG0xF5kqbTRzpA",
      "brand": "HSBC",
      "last4": "5454",
      "expYear": 2019,
      "expMonth": 12,
      "tokenizationMethod": null,
      "provider": "stripe",
      "isDefault": false
    }
  ]
}
```

<h4 id="delete-card-responses">Responses</h4>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|none|[cards](#schemacards)|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|none|None|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Not authenticated to perform this action|None|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
bearer ( Scopes: CUSTOMER ), bearer
</aside>

<h2 id="payment-service-webhooks">Webhooks</h2>

### Stripe Payment Intents Webhook

<a id="opIdStripe Payment Intents Webhook"></a>

> Code samples

```shell
# You can also use wget
curl -X POST /v1/webhooks/stripe-intents/tenant/{uuid} \
  -H 'Content-Type: application/json; charset=utf-8' \
  -H 'Accept: application/json; charset=utf-8'

```

```javascript
var headers = {
  'Content-Type':'application/json; charset=utf-8',
  'Accept':'application/json; charset=utf-8'

};

$.ajax({
  url: '/v1/webhooks/stripe-intents/tenant/{uuid}',
  method: 'post',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

```javascript--nodejs
const fetch = require('node-fetch');
const inputBody = 'string';
const headers = {
  'Content-Type':'application/json; charset=utf-8',
  'Accept':'application/json; charset=utf-8'

};

fetch('/v1/webhooks/stripe-intents/tenant/{uuid}',
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
  'Content-Type': 'application/json; charset=utf-8',
  'Accept': 'application/json; charset=utf-8'
}

r = requests.post('/v1/webhooks/stripe-intents/tenant/{uuid}', params={

}, headers = headers)

print r.json()

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Content-Type' => 'application/json; charset=utf-8',
  'Accept' => 'application/json; charset=utf-8'
}

result = RestClient.post '/v1/webhooks/stripe-intents/tenant/{uuid}',
  params: {
  }, headers: headers

p JSON.parse(result)

```

`POST /v1/webhooks/stripe-intents/tenant/{uuid}`

*stripe intents*

Only used by Stripe

> Body parameter

```json
"string"
```

<h4 id="stripe-payment-intents-webhook-parameters">Parameters</h4>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|string|true|none|
|uuid|path|string|true|Tenant UUID|

> Example responses

> 201 Response

```json
{
  "payload": {
    "uuid": "6bf3a91d-56d2-48ec-8a3d-8080ecc7a39f",
    "orderUUID": "84544519-8919-48d6-ae7f-04f1a2058edb",
    "transaction": "yEE1u9axI3RXxlRDutGui",
    "type": "intent",
    "amount": 5.25,
    "currency": "gbp",
    "failureCode": null,
    "failureMessage": null,
    "status": "pending",
    "meta": null,
    "createdAt": "2019-01-02T12:15:36.000Z",
    "details": {
      "clientSecret": "pi_1Ejm0WJYShqG0xF5yVIbINbl_secret_q7IyDjD6ntyeAeGMlrtQYIrlW"
    }
  }
}
```

<h4 id="stripe-payment-intents-webhook-responses">Responses</h4>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|201|[Created](https://tools.ietf.org/html/rfc7231#section-6.3.2)|none|[transaction](#schematransaction)|

<aside class="success">
This operation does not require authentication
</aside>

<h2 id="payment-service-management">Management</h2>

### Get Tenant Configs

<a id="opIdGet Tenant Configs"></a>

> Code samples

```shell
# You can also use wget
curl -X GET /v1/management/tenants-configs \
  -H 'Accept: application/json; charset=utf-8' \
  -H 'Authorization: API_KEY'

```

```javascript
var headers = {
  'Accept':'application/json; charset=utf-8',
  'Authorization':'API_KEY'

};

$.ajax({
  url: '/v1/management/tenants-configs',
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
  'Accept':'application/json; charset=utf-8',
  'Authorization':'API_KEY'

};

fetch('/v1/management/tenants-configs',
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
  'Accept': 'application/json; charset=utf-8',
  'Authorization': 'API_KEY'
}

r = requests.get('/v1/management/tenants-configs', params={

}, headers = headers)

print r.json()

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json; charset=utf-8',
  'Authorization' => 'API_KEY'
}

result = RestClient.get '/v1/management/tenants-configs',
  params: {
  }, headers: headers

p JSON.parse(result)

```

`GET /v1/management/tenants-configs`

*Get List of configs for all tenants*

Deep integration only! Get List of configs for all tenants

> Example responses

> 200 Response

```json
{
  "payload": [
    {
      "uuid": "2a45d6b7-702c-4dc3-985e-1086b179744c",
      "tenantUUID": "832b34ad-2608-4cc7-bee8-bfc47686d801",
      "apiKey": null,
      "apiSecret": null,
      "status": true,
      "isDefault": true,
      "currency": "gbp",
      "provider": {
        "uuid": "d7930b2f-d44d-4a5f-87a0-0b4883a8ec6b",
        "name": "Izettle"
      }
    },
    {
      "uuid": "faa0044a-5e8d-4aba-9c70-dd8fc12bacc2",
      "tenantUUID": "10c18540-d32e-48ce-aae3-7eba340f0f21",
      "apiKey": "pk_test_IwHwDqRSgwLldCU3uuuBxQiD",
      "apiSecret": "sk_test_vvObHFGDdfO8ZzE5WzqquiCx",
      "status": true,
      "isDefault": false,
      "currency": "gbp",
      "provider": {
        "uuid": "dc4f36f6-eb53-4b43-978f-82711d17686b",
        "name": "Stripe"
      }
    },
    {
      "uuid": "c1f996f3-5b2f-4749-939b-264017560528",
      "tenantUUID": "10c18540-d32e-48ce-aae3-7eba340f0f21",
      "apiKey": "pk_test_IwHwDqRSgwLldCU3uuuBxQiD",
      "apiSecret": "sk_test_vvObHFGDdfO8ZzE5WzqquiCx",
      "status": true,
      "isDefault": false,
      "currency": "gbp",
      "provider": {
        "uuid": "9053f139-238c-48c9-8566-5c88edf4c5aa",
        "name": "StripeIntents"
      }
    },
    {
      "uuid": "bad89bd7-f914-46dd-80b6-2d475db44922",
      "tenantUUID": "f006b92c-20a7-4192-a16a-29fea272191a",
      "apiKey": null,
      "apiSecret": null,
      "status": true,
      "isDefault": true,
      "currency": "gbp",
      "provider": {
        "uuid": "66f4a971-9e7b-4b55-b3e0-730cdbd28bea",
        "name": "Cash"
      }
    },
    {
      "uuid": "cbf9a6a8-83ec-45c9-99d9-b1b14cb0604d",
      "tenantUUID": "10c18540-d32e-48ce-aae3-7eba340f0f21",
      "apiKey": null,
      "apiSecret": null,
      "status": false,
      "isDefault": false,
      "currency": "gbp",
      "provider": {
        "uuid": "66f4a971-9e7b-4b55-b3e0-730cdbd28bea",
        "name": "Cash"
      }
    }
  ]
}
```

<h4 id="get-tenant-configs-responses">Responses</h4>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|none|[tenantProviderConfigList](#schematenantproviderconfiglist)|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Not authenticated to perform this action|None|
|403|[Forbidden](https://tools.ietf.org/html/rfc7231#section-6.5.3)|Not authorized to perform this action|None|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
bearer ( Scopes: SUPER_ADMIN ), bearer
</aside>

### Create Tenant Config

<a id="opIdCreate Tenant Config"></a>

> Code samples

```shell
# You can also use wget
curl -X POST /v1/management/tenants-configs \
  -H 'Content-Type: application/json; charset=utf-8' \
  -H 'Accept: application/json; charset=utf-8' \
  -H 'Authorization: API_KEY'

```

```javascript
var headers = {
  'Content-Type':'application/json; charset=utf-8',
  'Accept':'application/json; charset=utf-8',
  'Authorization':'API_KEY'

};

$.ajax({
  url: '/v1/management/tenants-configs',
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
  "tenantUUID": "string",
  "apiKey": "string",
  "apiSecret": "string",
  "status": true,
  "isDefault": true,
  "currency": "string",
  "provider": {
    "uuid": "string"
  }
}';
const headers = {
  'Content-Type':'application/json; charset=utf-8',
  'Accept':'application/json; charset=utf-8',
  'Authorization':'API_KEY'

};

fetch('/v1/management/tenants-configs',
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
  'Content-Type': 'application/json; charset=utf-8',
  'Accept': 'application/json; charset=utf-8',
  'Authorization': 'API_KEY'
}

r = requests.post('/v1/management/tenants-configs', params={

}, headers = headers)

print r.json()

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Content-Type' => 'application/json; charset=utf-8',
  'Accept' => 'application/json; charset=utf-8',
  'Authorization' => 'API_KEY'
}

result = RestClient.post '/v1/management/tenants-configs',
  params: {
  }, headers: headers

p JSON.parse(result)

```

`POST /v1/management/tenants-configs`

*Create a tenant config*

Deep integration only! Create a tenant config

> Body parameter

```json
{
  "tenantUUID": "string",
  "apiKey": "string",
  "apiSecret": "string",
  "status": true,
  "isDefault": true,
  "currency": "string",
  "provider": {
    "uuid": "string"
  }
}
```

<h4 id="create-tenant-config-parameters">Parameters</h4>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|[tenantProviderConfigCreate](#schematenantproviderconfigcreate)|true|none|

> Example responses

> 201 Response

```json
{
  "payload": {
    "uuid": "2a45d6b7-702c-4dc3-985e-1086b179744c",
    "tenantUUID": "832b34ad-2608-4cc7-bee8-bfc47686d801",
    "apiKey": null,
    "apiSecret": null,
    "status": true,
    "isDefault": true,
    "currency": "gbp",
    "provider": {
      "uuid": "d7930b2f-d44d-4a5f-87a0-0b4883a8ec6b",
      "name": "Izettle"
    }
  }
}
```

<h4 id="create-tenant-config-responses">Responses</h4>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|201|[Created](https://tools.ietf.org/html/rfc7231#section-6.3.2)|none|[tenantProviderConfig](#schematenantproviderconfig)|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Not authenticated to perform this action|None|
|403|[Forbidden](https://tools.ietf.org/html/rfc7231#section-6.5.3)|Not authorized to perform this action|None|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
bearer ( Scopes: SUPER_ADMIN ), bearer
</aside>

### Get Tenant Config

<a id="opIdGet Tenant Config"></a>

> Code samples

```shell
# You can also use wget
curl -X GET /v1/management/tenants-configs/{uuid} \
  -H 'Accept: application/json; charset=utf-8' \
  -H 'Authorization: API_KEY'

```

```javascript
var headers = {
  'Accept':'application/json; charset=utf-8',
  'Authorization':'API_KEY'

};

$.ajax({
  url: '/v1/management/tenants-configs/{uuid}',
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
  'Accept':'application/json; charset=utf-8',
  'Authorization':'API_KEY'

};

fetch('/v1/management/tenants-configs/{uuid}',
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
  'Accept': 'application/json; charset=utf-8',
  'Authorization': 'API_KEY'
}

r = requests.get('/v1/management/tenants-configs/{uuid}', params={

}, headers = headers)

print r.json()

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json; charset=utf-8',
  'Authorization' => 'API_KEY'
}

result = RestClient.get '/v1/management/tenants-configs/{uuid}',
  params: {
  }, headers: headers

p JSON.parse(result)

```

`GET /v1/management/tenants-configs/{uuid}`

*Get One config by uuid*

Deep integration only! Get One config by uuid

<h4 id="get-tenant-config-parameters">Parameters</h4>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|uuid|path|string|true|none|

> Example responses

> 200 Response

```json
{
  "payload": {
    "uuid": "2a45d6b7-702c-4dc3-985e-1086b179744c",
    "tenantUUID": "832b34ad-2608-4cc7-bee8-bfc47686d801",
    "apiKey": null,
    "apiSecret": null,
    "status": true,
    "isDefault": true,
    "currency": "gbp",
    "provider": {
      "uuid": "d7930b2f-d44d-4a5f-87a0-0b4883a8ec6b",
      "name": "Izettle"
    }
  }
}
```

<h4 id="get-tenant-config-responses">Responses</h4>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|none|[tenantProviderConfig](#schematenantproviderconfig)|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Not authenticated to perform this action|None|
|403|[Forbidden](https://tools.ietf.org/html/rfc7231#section-6.5.3)|Not authorized to perform this action|None|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
bearer ( Scopes: SUPER_ADMIN ), bearer
</aside>

### Update Tenant Config

<a id="opIdUpdate Tenant Config"></a>

> Code samples

```shell
# You can also use wget
curl -X PUT /v1/management/tenants-configs/{uuid} \
  -H 'Content-Type: application/json; charset=utf-8' \
  -H 'Accept: application/json; charset=utf-8' \
  -H 'Authorization: API_KEY'

```

```javascript
var headers = {
  'Content-Type':'application/json; charset=utf-8',
  'Accept':'application/json; charset=utf-8',
  'Authorization':'API_KEY'

};

$.ajax({
  url: '/v1/management/tenants-configs/{uuid}',
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
  "tenantUUID": "string",
  "apiKey": "string",
  "apiSecret": "string",
  "status": true,
  "isDefault": true,
  "currency": "string"
}';
const headers = {
  'Content-Type':'application/json; charset=utf-8',
  'Accept':'application/json; charset=utf-8',
  'Authorization':'API_KEY'

};

fetch('/v1/management/tenants-configs/{uuid}',
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
  'Content-Type': 'application/json; charset=utf-8',
  'Accept': 'application/json; charset=utf-8',
  'Authorization': 'API_KEY'
}

r = requests.put('/v1/management/tenants-configs/{uuid}', params={

}, headers = headers)

print r.json()

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Content-Type' => 'application/json; charset=utf-8',
  'Accept' => 'application/json; charset=utf-8',
  'Authorization' => 'API_KEY'
}

result = RestClient.put '/v1/management/tenants-configs/{uuid}',
  params: {
  }, headers: headers

p JSON.parse(result)

```

`PUT /v1/management/tenants-configs/{uuid}`

*Update a tenant config*

Deep integration only! Update a tenant config

> Body parameter

```json
{
  "tenantUUID": "string",
  "apiKey": "string",
  "apiSecret": "string",
  "status": true,
  "isDefault": true,
  "currency": "string"
}
```

<h4 id="update-tenant-config-parameters">Parameters</h4>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|[tenantProviderConfigUpdate](#schematenantproviderconfigupdate)|true|none|
|uuid|path|string|true|none|

> Example responses

> 200 Response

```json
{
  "payload": {
    "uuid": "2a45d6b7-702c-4dc3-985e-1086b179744c",
    "tenantUUID": "832b34ad-2608-4cc7-bee8-bfc47686d801",
    "apiKey": null,
    "apiSecret": null,
    "status": true,
    "isDefault": true,
    "currency": "gbp",
    "provider": {
      "uuid": "d7930b2f-d44d-4a5f-87a0-0b4883a8ec6b",
      "name": "Izettle"
    }
  }
}
```

<h4 id="update-tenant-config-responses">Responses</h4>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|none|[tenantProviderConfig](#schematenantproviderconfig)|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Not authenticated to perform this action|None|
|403|[Forbidden](https://tools.ietf.org/html/rfc7231#section-6.5.3)|Not authorized to perform this action|None|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
bearer ( Scopes: SUPER_ADMIN ), bearer
</aside>

<h2 id="payment-service-setup-intents">Setup Intents</h2>

### Setup Stripe Payment Intents

<a id="opIdSetup Stripe Payment Intents"></a>

> Code samples

```shell
# You can also use wget
curl -X POST /v1/setup-intents \
  -H 'Content-Type: application/json; charset=utf-8' \
  -H 'Accept: application/json; charset=utf-8' \
  -H 'Authorization: API_KEY'

```

```javascript
var headers = {
  'Content-Type':'application/json; charset=utf-8',
  'Accept':'application/json; charset=utf-8',
  'Authorization':'API_KEY'

};

$.ajax({
  url: '/v1/setup-intents',
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
  "provider": {
    "uuid": "string"
  }
}';
const headers = {
  'Content-Type':'application/json; charset=utf-8',
  'Accept':'application/json; charset=utf-8',
  'Authorization':'API_KEY'

};

fetch('/v1/setup-intents',
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
  'Content-Type': 'application/json; charset=utf-8',
  'Accept': 'application/json; charset=utf-8',
  'Authorization': 'API_KEY'
}

r = requests.post('/v1/setup-intents', params={

}, headers = headers)

print r.json()

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Content-Type' => 'application/json; charset=utf-8',
  'Accept' => 'application/json; charset=utf-8',
  'Authorization' => 'API_KEY'
}

result = RestClient.post '/v1/setup-intents',
  params: {
  }, headers: headers

p JSON.parse(result)

```

`POST /v1/setup-intents`

*Create a setup intent object*

Deep integrations only! Create Strie Payment Intents required configuration.

> Body parameter

```json
{
  "provider": {
    "uuid": "string"
  }
}
```

<h4 id="setup-stripe-payment-intents-parameters">Parameters</h4>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|[setupIntent](#schemasetupintent)|true|none|

> Example responses

> 201 Response

```json
{
  "payload": {
    "id": "seti_1F1aOcJYShqG0xF5B3B1m3AA",
    "clientSecret": "seti_1F1aOcJYShqG0xF5B3B1m3AA_secret_FWdfkcgetiJ0I2TctQ96mjftC5Zizwe"
  }
}
```

<h4 id="setup-stripe-payment-intents-responses">Responses</h4>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|201|[Created](https://tools.ietf.org/html/rfc7231#section-6.3.2)|none|Inline|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Not authenticated to perform this action|None|

<h4 id="setup-stripe-payment-intents-responseschema">Response Schema</h4>

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
bearer ( Scopes: SUPER_ADMIN ), bearer
</aside>

## Schemas

<h3 id="tocScards">cards</h3>

<a id="schemacards"></a>

```json
{
  "payload": [
    {
      "id": "string",
      "brand": "string",
      "last4": "string",
      "expYear": 0,
      "expMonth": 0,
      "tokenizationMethod": "string",
      "provider": "string",
      "isDefault": true
    }
  ]
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|payload|[object]|true|none|none|
|» The Items Schema|object|false|none|none|
|»» id|string|true|none|none|
|»» brand|string|true|none|none|
|»» last4|string|true|none|none|
|»» expYear|integer|true|none|none|
|»» expMonth|integer|true|none|none|
|»» tokenizationMethod|string|true|none|none|
|»» provider|string|true|none|none|
|»» isDefault|boolean|true|none|none|

<h3 id="tocScardreq">cardReq</h3>

<a id="schemacardreq"></a>

```json
{
  "token": "string",
  "providerUUID": "string"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|token|string|true|none|none|
|providerUUID|string|true|none|none|

<h3 id="tocScard">card</h3>

<a id="schemacard"></a>

```json
{
  "payload": {
    "id": "string",
    "brand": "string",
    "last4": "string",
    "expYear": 0,
    "expMonth": 0,
    "tokenizationMethod": "string",
    "provider": "string",
    "isDefault": true
  }
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|payload|object|true|none|none|
|» id|string|true|none|none|
|» brand|string|true|none|none|
|» last4|string|true|none|none|
|» expYear|integer|true|none|none|
|» expMonth|integer|true|none|none|
|» tokenizationMethod|string|true|none|none|
|» provider|string|true|none|none|
|» isDefault|boolean|true|none|none|

<h3 id="tocStransaction">transaction</h3>

<a id="schematransaction"></a>

```json
{
  "payload": {
    "uuid": "string",
    "orderUUID": "string",
    "transaction": "string",
    "type": "string",
    "amount": 0,
    "currency": "string",
    "failureCode": "string",
    "failureMessage": "string",
    "status": "string",
    "meta": "string",
    "createdAt": "string",
    "details": {
      "clientSecret": "string"
    }
  }
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|payload|object|true|none|none|
|» uuid|string|true|none|none|
|» orderUUID|string|true|none|none|
|» transaction|string|true|none|none|
|» type|string|true|none|none|
|» amount|number|true|none|none|
|» currency|string|true|none|none|
|» failureCode|string|true|none|none|
|» failureMessage|string|true|none|none|
|» status|string|true|none|none|
|» meta|string|true|none|none|
|» createdAt|string|true|none|none|
|» details|object|true|none|none|
|»» clientSecret|string|true|none|Required only for stripe payment intents|

<h3 id="tocStransactionreq">transactionReq</h3>

<a id="schematransactionreq"></a>

```json
{
  "order": {
    "required": "string"
  },
  "providerUUID": "string",
  "card": {
    "id": "string",
    "token": "string"
  },
  "currency": "string",
  "meta": {}
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|order|object|true|none|none|
|» required|string|true|none|none|
|providerUUID|string|true|none|none|
|card|object|false|none|none|
|» id|string|true|none|none|
|» token|string|true|none|none|
|currency|string|false|none|none|
|meta|object|false|none|none|

<h3 id="tocStransactions">transactions</h3>

<a id="schematransactions"></a>

```json
{
  "payload": [
    {
      "uuid": "string",
      "orderUUID": "string",
      "transaction": "string",
      "type": "string",
      "amount": 0,
      "currency": "string",
      "failureCode": "string",
      "failureMessage": "string",
      "status": "string",
      "meta": {},
      "createdAt": "string",
      "provider": {}
    }
  ]
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|payload|[object]|true|none|none|
|» The Items Schema|object|false|none|none|
|»» uuid|string|true|none|none|
|»» orderUUID|string|true|none|none|
|»» transaction|string|true|none|none|
|»» type|string|true|none|none|
|»» amount|number|true|none|none|
|»» currency|string|true|none|none|
|»» failureCode|string|true|none|none|
|»» failureMessage|string|true|none|none|
|»» status|string|true|none|none|
|»» meta|object|true|none|none|
|»» createdAt|string|true|none|none|
|»» provider|object|true|none|none|

<h3 id="tocStransactionrefundable">transactionRefundable</h3>

<a id="schematransactionrefundable"></a>

```json
{
  "payload": {
    "isRefundable": true
  }
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|payload|object|true|none|none|
|» isRefundable|boolean|true|none|none|

<h3 id="tocStransactiondetails">transactionDetails</h3>

<a id="schematransactiondetails"></a>

```json
{
  "payload": {
    "uuid": "string",
    "orderUUID": "string",
    "transaction": "string",
    "type": "string",
    "amount": 0,
    "currency": "string",
    "failureCode": "string",
    "failureMessage": "string",
    "status": "string",
    "meta": "string",
    "createdAt": "string",
    "details": {
      "card": {
        "id": "string",
        "brand": "string",
        "last4": "string",
        "expYear": 0,
        "expMonth": 0,
        "tokenizationMethod": "string"
      }
    }
  }
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|payload|object|true|none|none|
|» uuid|string|false|none|none|
|» orderUUID|string|true|none|none|
|» transaction|string|true|none|none|
|» type|string|true|none|none|
|» amount|number|true|none|none|
|» currency|string|true|none|none|
|» failureCode|string|true|none|none|
|» failureMessage|string|true|none|none|
|» status|string|true|none|none|
|» meta|string|true|none|none|
|» createdAt|string|true|none|none|
|» details|object|true|none|none|
|»» card|object|true|none|none|
|»»» id|string|true|none|none|
|»»» brand|string|true|none|none|
|»»» last4|string|true|none|none|
|»»» expYear|integer|true|none|none|
|»»» expMonth|integer|true|none|none|
|»»» tokenizationMethod|string|true|none|none|

<h3 id="tocStenantproviders">tenantProviders</h3>

<a id="schematenantproviders"></a>

```json
{
  "payload": [
    {
      "uuid": "string",
      "slug": "string",
      "supportCards": true,
      "createCustomer": true,
      "sdk": "string",
      "config": {
        "apiKey": "string",
        "status": true,
        "isDefault": true,
        "currency": "string"
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
|» slug|string|true|none|none|
|» supportCards|boolean|true|none|none|
|» createCustomer|boolean|true|none|none|
|» sdk|string|true|none|none|
|» config|object|true|none|none|
|»» apiKey|string|true|none|none|
|»» status|boolean|true|none|none|
|»» isDefault|boolean|true|none|none|
|»» currency|string|true|none|none|

<h3 id="tocStenantproviderconfig">tenantProviderConfig</h3>

<a id="schematenantproviderconfig"></a>

```json
{
  "payload": {
    "uuid": "string",
    "tenantUUID": "string",
    "apiKey": "string",
    "apiSecret": "string",
    "status": true,
    "isDefault": true,
    "currency": "string",
    "provider": {
      "uuid": "string",
      "name": "string"
    }
  }
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|payload|object|true|none|none|
|» uuid|string|true|none|none|
|» tenantUUID|string|true|none|none|
|» apiKey|string|true|none|none|
|» apiSecret|string|true|none|none|
|» status|boolean|true|none|none|
|» isDefault|boolean|true|none|none|
|» currency|string|true|none|none|
|» provider|object|true|none|none|
|»» uuid|string|true|none|none|
|»» name|string|true|none|none|

<h3 id="tocStenantproviderconfiglist">tenantProviderConfigList</h3>

<a id="schematenantproviderconfiglist"></a>

```json
{
  "payload": [
    {
      "uuid": "string",
      "tenantUUID": "string",
      "apiKey": "string",
      "apiSecret": "string",
      "status": true,
      "isDefault": true,
      "currency": "string",
      "provider": {
        "uuid": "string",
        "name": "string"
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
|» tenantUUID|string|true|none|none|
|» apiKey|string|true|none|none|
|» apiSecret|string|true|none|none|
|» status|boolean|true|none|none|
|» isDefault|boolean|true|none|none|
|» currency|string|true|none|none|
|» provider|object|true|none|none|
|»» uuid|string|true|none|none|
|»» name|string|true|none|none|

<h3 id="tocStenantproviderconfigcreate">tenantProviderConfigCreate</h3>

<a id="schematenantproviderconfigcreate"></a>

```json
{
  "tenantUUID": "string",
  "apiKey": "string",
  "apiSecret": "string",
  "status": true,
  "isDefault": true,
  "currency": "string",
  "provider": {
    "uuid": "string"
  }
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|tenantUUID|string|true|none|none|
|apiKey|string|true|none|none|
|apiSecret|string|true|none|none|
|status|boolean|true|none|none|
|isDefault|boolean|true|none|none|
|currency|string|true|none|none|
|provider|object|true|none|none|
|» uuid|string|true|none|none|

<h3 id="tocStenantproviderconfigupdate">tenantProviderConfigUpdate</h3>

<a id="schematenantproviderconfigupdate"></a>

```json
{
  "tenantUUID": "string",
  "apiKey": "string",
  "apiSecret": "string",
  "status": true,
  "isDefault": true,
  "currency": "string"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|tenantUUID|string|true|none|none|
|apiKey|string|true|none|none|
|apiSecret|string|true|none|none|
|status|boolean|true|none|none|
|isDefault|boolean|true|none|none|
|currency|string|true|none|none|

<h3 id="tocSsetupintent">setupIntent</h3>

<a id="schemasetupintent"></a>

```json
{
  "provider": {
    "uuid": "string"
  }
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|provider|object|true|none|none|
|» uuid|string|true|none|none|

