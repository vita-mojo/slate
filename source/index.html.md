---
title: API Reference

language_tabs: # must be one of https://git.io/vQNgJ
  - javascript--nodejs: Node.JS
  - shell: curl
  - javascript: JavaScript
  - python: Python
  - ruby: Ruby

toc_footers:
  - <a href='https://github.com/lord/slate'>Documentation Powered by Slate</a>

includes:
  - order
  - catalog
  - payment
  - user
  - tenant
  - loyalty

search: true
---

# Introduction

Welcome to the VMOS API! You can use our API most of the functionality on the VMOS platform.

In order to gain access to use these apis please email support@vmos.io. We will be able to provide the right credentials and other details required to use the APIs. More information about this in the Authentication section.

Some of the endpoints are marked as `Deep integrations only!`. Your level of access will probably not allow you to use any of those but in depth guides and support can be provided for deep integrations.

We have language bindings in Shell, Ruby, Python, and JavaScript! You can view code examples in the dark area to the right, and you can switch the programming language of the examples with the tabs in the top right.

# Authentication
Our Authentication uses Oauth 2 refresh token grant: https://tools.ietf.org/html/rfc6749#section-1.5

You need to use `POST /v1/auth` to get authenticated. You will get a refresh token that is valid indefinitely. 

Use the refresh token to get an auth token from `PUT /v1/auth/refresh/{value}` before each API call. 

You will need correct tenant and store UUID for most API calls. You will need credentials with sufficient permissions for the required operations. Please contact support@vmos.io to get credentials and required UUIDs.

### Auth

<a id="opIdAuth"></a>

> Code samples

```shell
# You can also use wget
curl -X POST /v1/auth \
  -H 'Content-Type: application/json; charset=utf-8' \
  -H 'Accept: application/json; charset=utf-8' \
  -H 'tenant: string'

```

```javascript
var headers = {
  'Content-Type':'application/json; charset=utf-8',
  'Accept':'application/json; charset=utf-8',
  'tenant':'string'

};

$.ajax({
  url: '/v1/auth',
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
  "email": "string",
  "password": "string"
}';
const headers = {
  'Content-Type':'application/json; charset=utf-8',
  'Accept':'application/json; charset=utf-8',
  'tenant':'string'

};

fetch('/v1/auth',
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
  'tenant': 'string'
}

r = requests.post('/v1/auth', params={

}, headers = headers)

print r.json()

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Content-Type' => 'application/json; charset=utf-8',
  'Accept' => 'application/json; charset=utf-8',
  'tenant' => 'string'
}

result = RestClient.post '/v1/auth',
  params: {
  }, headers: headers

p JSON.parse(result)

```

`POST /v1/auth`

*Get authenticated. Refresh token is valid indefinitely, should be stored and used to get an access token before each API request. Access token expires in 10 minutes.*

> Body parameter

```json
{
  "email": "string",
  "password": "string"
}
```

<h4 id="auth-parameters">Parameters</h4>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|tenant|header|string|false|Tenant UUID|
|body|body|[AuthReq](#schemaauthreq)|true|none|

> Example responses

> 201 Response

```json
{
  "payload": {
    "token": {
      "value": "dTut7buyVPTBKa6PLeYEK4O4Fan7nb3zRVgKUxe_6vYgOSk2k2OhLKX6BA_gDaPy9khRnkbSHQKF-wCKUl2cO7dgcSR_1gI63tDV",
      "refresh": "z8gclBTjDD1oGOkcAh0T6AyHs41TCW7jcMyaI0hmLWnChotmrprj1eW1RKX8VQZJq6Nj46ta2dTnykn2zx6Yj-Ijs5n8v-PeZbOb5LFWw8HtUeWFka0ZRXtVMTSTUh7p2FOokjFAPVwriDyyOdzaVfWPspL94wrun79L53Uok1tt6XJ39FkfWmL7mIcC-bufSElsxdh0"
    },
    "user": {
      "uuid": "c36578d8-ffa6-4a5e-a808-400ee422028a",
      "tenantUUID": "random tenant uuid",
      "storeUUID": null,
      "email": "admin@vitamojo.dev",
      "active": true,
      "createdAt": "2018-12-10T15:40:14.000Z",
      "updatedAt": "2018-12-10T15:40:14.000Z",
      "role": {
        "uuid": "98287263-e9f4-4ab8-8a26-d468527765ee",
        "rank": 1,
        "slug": "admin",
        "displayName": "Admin",
        "description": "Admin",
        "permissions": [
          "can.create.users",
          "can.create.users.lower_role",
          "can.access.order_history",
          "can.access.management_panel_and_pos",
          "can.access.all_staff_areas"
        ]
      }
    }
  }
}
```

<h4 id="auth-responses">Responses</h4>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|201|[Created](https://tools.ietf.org/html/rfc7231#section-6.3.2)|Authentication, token and user data returned|[AuthRes](#schemaauthres)|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Email or password is not valid|None|

<aside class="success">
This operation does not require authentication
</aside>

### Check Token

<a id="opIdCheck Token"></a>

> Code samples

```shell
# You can also use wget
curl -X GET /v1/auth/check \
  -H 'Accept: application/json; charset=utf-8' \
  -H 'Authorization: Bearer {access-token}'

```

```javascript
var headers = {
  'Accept':'application/json; charset=utf-8',
  'Authorization':'Bearer {access-token}'

};

$.ajax({
  url: '/v1/auth/check',
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
  'Authorization':'Bearer {access-token}'

};

fetch('/v1/auth/check',
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
  'Authorization': 'Bearer {access-token}'
}

r = requests.get('/v1/auth/check', params={

}, headers = headers)

print r.json()

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json; charset=utf-8',
  'Authorization' => 'Bearer {access-token}'
}

result = RestClient.get '/v1/auth/check',
  params: {
  }, headers: headers

p JSON.parse(result)

```

`GET /v1/auth/check`

*Check token is valid*

> Example responses

> 200 Response

```json
{
  "payload": {
    "token": {
      "value": "dTut7buyVPTBKa6PLeYEK4O4Fan7nb3zRVgKUxe_6vYgOSk2k2OhLKX6BA_gDaPy9khRnkbSHQKF-wCKUl2cO7dgcSR_1gI63tDV",
      "refresh": "z8gclBTjDD1oGOkcAh0T6AyHs41TCW7jcMyaI0hmLWnChotmrprj1eW1RKX8VQZJq6Nj46ta2dTnykn2zx6Yj-Ijs5n8v-PeZbOb5LFWw8HtUeWFka0ZRXtVMTSTUh7p2FOokjFAPVwriDyyOdzaVfWPspL94wrun79L53Uok1tt6XJ39FkfWmL7mIcC-bufSElsxdh0"
    },
    "user": {
      "uuid": "c36578d8-ffa6-4a5e-a808-400ee422028a",
      "tenantUUID": "random tenant uuid",
      "storeUUID": null,
      "email": "admin@vitamojo.dev",
      "active": true,
      "createdAt": "2018-12-10T15:40:14.000Z",
      "updatedAt": "2018-12-10T15:40:14.000Z",
      "role": {
        "uuid": "98287263-e9f4-4ab8-8a26-d468527765ee",
        "rank": 1,
        "slug": "admin",
        "displayName": "Admin",
        "description": "Admin",
        "permissions": [
          "can.create.users",
          "can.create.users.lower_role",
          "can.access.order_history",
          "can.access.management_panel_and_pos",
          "can.access.all_staff_areas"
        ]
      }
    }
  }
}
```

<h4 id="check-token-responses">Responses</h4>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|none|[AuthRes](#schemaauthres)|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Not authenticated to perform this action|None|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
oauth_2_0 ( Scopes: SUPER_ADMIN ADMINISTRATOR MANAGER STAFF CUSTOMER SERVICE_ACCOUNT SALES_REPORTING ), oauth_2_0
</aside>

### Refresh Token

<a id="opIdRefresh Token"></a>

> Code samples

```shell
# You can also use wget
curl -X PUT /v1/auth/refresh/{value} \
  -H 'Accept: application/json; charset=utf-8'

```

```javascript
var headers = {
  'Accept':'application/json; charset=utf-8'

};

$.ajax({
  url: '/v1/auth/refresh/{value}',
  method: 'put',

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

fetch('/v1/auth/refresh/{value}',
{
  method: 'PUT',

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

r = requests.put('/v1/auth/refresh/{value}', params={

}, headers = headers)

print r.json()

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json; charset=utf-8'
}

result = RestClient.put '/v1/auth/refresh/{value}',
  params: {
  }, headers: headers

p JSON.parse(result)

```

`PUT /v1/auth/refresh/{value}`

*Use the Refresh token to get new access token. Access token is valid 10 minutes. You should get a new access token before any API request.*

<h4 id="refresh-token-parameters">Parameters</h4>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|value|path|string|true|none|

> Example responses

> 200 Response

```json
{
  "payload": {
    "token": {
      "value": "dTut7buyVPTBKa6PLeYEK4O4Fan7nb3zRVgKUxe_6vYgOSk2k2OhLKX6BA_gDaPy9khRnkbSHQKF-wCKUl2cO7dgcSR_1gI63tDV",
      "refresh": "z8gclBTjDD1oGOkcAh0T6AyHs41TCW7jcMyaI0hmLWnChotmrprj1eW1RKX8VQZJq6Nj46ta2dTnykn2zx6Yj-Ijs5n8v-PeZbOb5LFWw8HtUeWFka0ZRXtVMTSTUh7p2FOokjFAPVwriDyyOdzaVfWPspL94wrun79L53Uok1tt6XJ39FkfWmL7mIcC-bufSElsxdh0"
    },
    "user": {
      "uuid": "c36578d8-ffa6-4a5e-a808-400ee422028a",
      "tenantUUID": "random tenant uuid",
      "storeUUID": null,
      "email": "admin@vitamojo.dev",
      "active": true,
      "createdAt": "2018-12-10T15:40:14.000Z",
      "updatedAt": "2018-12-10T15:40:14.000Z",
      "role": {
        "uuid": "98287263-e9f4-4ab8-8a26-d468527765ee",
        "rank": 1,
        "slug": "admin",
        "displayName": "Admin",
        "description": "Admin",
        "permissions": [
          "can.create.users",
          "can.create.users.lower_role",
          "can.access.order_history",
          "can.access.management_panel_and_pos",
          "can.access.all_staff_areas"
        ]
      }
    }
  }
}
```

<h4 id="refresh-token-responses">Responses</h4>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|none|Inline|

<h4 id="refresh-token-responseschema">Response Schema</h4>

<aside class="success">
This operation does not require authentication
</aside>


