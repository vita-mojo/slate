---
title: User/Auth Service
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

<h1 id="user-auth-service">User/Auth Service</h1>

> Scroll down for code samples, example requests and responses. Select a language for code samples from the tabs above or the mobile navigation menu.

User/Auth Service  Api Doc

<h2 id="user-auth-service-healthcheck">Healthcheck</h2>

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

<h2 id="user-auth-service-v1-auth">v1/auth</h2>

### POST_v1-auth

<a id="opIdPOST_v1-auth"></a>

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
const inputBody = '{}';
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

*Get authenticated*

> Body parameter

```json
{}
```

<h4 id="post_v1-auth-parameters">Parameters</h4>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|tenant|header|string|false|Tenant UUID|
|body|body|object|true|none|

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

<h4 id="post_v1-auth-responses">Responses</h4>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|201|[Created](https://tools.ietf.org/html/rfc7231#section-6.3.2)|Authentication, token and user data returned|Inline|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Email or password is not valid|None|

<h4 id="post_v1-auth-responseschema">Response Schema</h4>

<aside class="success">
This operation does not require authentication
</aside>

### GET_v1-auth-check

<a id="opIdGET_v1-auth-check"></a>

> Code samples

```shell
# You can also use wget
curl -X GET /v1/auth/check \
  -H 'Accept: application/json; charset=utf-8' \
  -H 'Authorization: API_KEY'

```

```javascript
var headers = {
  'Accept':'application/json; charset=utf-8',
  'Authorization':'API_KEY'

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
  'Authorization':'API_KEY'

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
  'Authorization': 'API_KEY'
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
  'Authorization' => 'API_KEY'
}

result = RestClient.get '/v1/auth/check',
  params: {
  }, headers: headers

p JSON.parse(result)

```

`GET /v1/auth/check`

*Check Token (is token valid)*

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

<h4 id="get_v1-auth-check-responses">Responses</h4>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|none|Inline|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Not authenticated to perform this action|None|

<h4 id="get_v1-auth-check-responseschema">Response Schema</h4>

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
bearer
</aside>

### PUT_v1-auth-refresh-value

<a id="opIdPUT_v1-auth-refresh-value"></a>

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

*Refresh token*

<h4 id="put_v1-auth-refresh-value-parameters">Parameters</h4>

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

<h4 id="put_v1-auth-refresh-value-responses">Responses</h4>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|none|Inline|

<h4 id="put_v1-auth-refresh-value-responseschema">Response Schema</h4>

<aside class="success">
This operation does not require authentication
</aside>

<h2 id="user-auth-service-v1-user">v1/user</h2>

### POST_v1-user

<a id="opIdPOST_v1-user"></a>

> Code samples

```shell
# You can also use wget
curl -X POST /v1/user \
  -H 'Content-Type: application/json; charset=utf-8' \
  -H 'Accept: application/json; charset=utf-8' \
  -H 'store: string' \
  -H 'tenant: string'

```

```javascript
var headers = {
  'Content-Type':'application/json; charset=utf-8',
  'Accept':'application/json; charset=utf-8',
  'store':'string',
  'tenant':'string'

};

$.ajax({
  url: '/v1/user',
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
  "password": "string",
  "subscriptions": [
    "marketing"
  ],
  "profile": {
    "firstName": "string"
  }
}';
const headers = {
  'Content-Type':'application/json; charset=utf-8',
  'Accept':'application/json; charset=utf-8',
  'store':'string',
  'tenant':'string'

};

fetch('/v1/user',
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
  'store': 'string',
  'tenant': 'string'
}

r = requests.post('/v1/user', params={

}, headers = headers)

print r.json()

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Content-Type' => 'application/json; charset=utf-8',
  'Accept' => 'application/json; charset=utf-8',
  'store' => 'string',
  'tenant' => 'string'
}

result = RestClient.post '/v1/user',
  params: {
  }, headers: headers

p JSON.parse(result)

```

`POST /v1/user`

*Create user*

> Body parameter

```json
{
  "email": "string",
  "password": "string",
  "subscriptions": [
    "marketing"
  ],
  "profile": {
    "firstName": "string"
  }
}
```

<h4 id="post_v1-user-parameters">Parameters</h4>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|store|header|string|false|none|
|tenant|header|string|true|none|
|body|body|object|true|none|
|» email|body|string|true|none|
|» password|body|string|true|none|
|» subscriptions|body|[string]|false|none|
|» profile|body|object|false|none|
|»» firstName|body|string|false|none|

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

<h4 id="post_v1-user-responses">Responses</h4>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|201|[Created](https://tools.ietf.org/html/rfc7231#section-6.3.2)|none|Inline|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|none|Inline|

<h4 id="post_v1-user-responseschema">Response Schema</h4>

<aside class="success">
This operation does not require authentication
</aside>

### GET_v1-user-uuid-email

<a id="opIdGET_v1-user-uuid-email"></a>

> Code samples

```shell
# You can also use wget
curl -X GET /v1/user/{uuid}/email \
  -H 'Accept: application/json; charset=utf-8' \
  -H 'Authorization: API_KEY'

```

```javascript
var headers = {
  'Accept':'application/json; charset=utf-8',
  'Authorization':'API_KEY'

};

$.ajax({
  url: '/v1/user/{uuid}/email',
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

fetch('/v1/user/{uuid}/email',
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

r = requests.get('/v1/user/{uuid}/email', params={

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

result = RestClient.get '/v1/user/{uuid}/email',
  params: {
  }, headers: headers

p JSON.parse(result)

```

`GET /v1/user/{uuid}/email`

*Get profile for email*

<h4 id="get_v1-user-uuid-email-parameters">Parameters</h4>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|uuid|path|string|true|none|

> Example responses

> 200 Response

```json
{
  "payload": {
    "uuid": "Genesis",
    "email": "user@vitamojo.dev",
    "profile": {
      "firstName": "Genesis",
      "lastName": "Leannon"
    },
    "subscriptions": [
      "order",
      "marketing"
    ]
  }
}
```

<h4 id="get_v1-user-uuid-email-responses">Responses</h4>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|none|Inline|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Not authenticated to perform this action|None|

<h4 id="get_v1-user-uuid-email-responseschema">Response Schema</h4>

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
bearer
</aside>

### GET_v1-user-check-email

<a id="opIdGET_v1-user-check-email"></a>

> Code samples

```shell
# You can also use wget
curl -X GET /v1/user/check/{email} \
  -H 'Accept: application/json; charset=utf-8' \
  -H 'tenant: string'

```

```javascript
var headers = {
  'Accept':'application/json; charset=utf-8',
  'tenant':'string'

};

$.ajax({
  url: '/v1/user/check/{email}',
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

fetch('/v1/user/check/{email}',
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

r = requests.get('/v1/user/check/{email}', params={

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

result = RestClient.get '/v1/user/check/{email}',
  params: {
  }, headers: headers

p JSON.parse(result)

```

`GET /v1/user/check/{email}`

*Check if user exists by a given email*

<h4 id="get_v1-user-check-email-parameters">Parameters</h4>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|tenant|header|string|true|none|
|email|path|string|true|none|

> Example responses

> 200 Response

```json
"{\n   payload: {\n     exists: true\n   }\n}\n"
```

<h4 id="get_v1-user-check-email-responses">Responses</h4>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|none|Inline|

<h4 id="get_v1-user-check-email-responseschema">Response Schema</h4>

<aside class="success">
This operation does not require authentication
</aside>

### GET_v1-user-subscriptions

<a id="opIdGET_v1-user-subscriptions"></a>

> Code samples

```shell
# You can also use wget
curl -X GET /v1/user/subscriptions \
  -H 'Accept: application/json; charset=utf-8' \
  -H 'Authorization: API_KEY'

```

```javascript
var headers = {
  'Accept':'application/json; charset=utf-8',
  'Authorization':'API_KEY'

};

$.ajax({
  url: '/v1/user/subscriptions',
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

fetch('/v1/user/subscriptions',
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

r = requests.get('/v1/user/subscriptions', params={

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

result = RestClient.get '/v1/user/subscriptions',
  params: {
  }, headers: headers

p JSON.parse(result)

```

`GET /v1/user/subscriptions`

*Get user subscriptions (email)*

> Example responses

> 200 Response

```json
{
  "payload": {
    "subscriptions": [
      "order",
      "marketing"
    ]
  }
}
```

<h4 id="get_v1-user-subscriptions-responses">Responses</h4>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|none|Inline|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Not authenticated to perform this action|None|

<h4 id="get_v1-user-subscriptions-responseschema">Response Schema</h4>

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
bearer
</aside>

### PUT_v1-user-subscriptions

<a id="opIdPUT_v1-user-subscriptions"></a>

> Code samples

```shell
# You can also use wget
curl -X PUT /v1/user/subscriptions \
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
  url: '/v1/user/subscriptions',
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
  "subscriptions": [
    "marketing"
  ]
}';
const headers = {
  'Content-Type':'application/json; charset=utf-8',
  'Accept':'application/json; charset=utf-8',
  'Authorization':'API_KEY'

};

fetch('/v1/user/subscriptions',
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

r = requests.put('/v1/user/subscriptions', params={

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

result = RestClient.put '/v1/user/subscriptions',
  params: {
  }, headers: headers

p JSON.parse(result)

```

`PUT /v1/user/subscriptions`

*Update marketing subscription for user*

> Body parameter

```json
{
  "subscriptions": [
    "marketing"
  ]
}
```

<h4 id="put_v1-user-subscriptions-parameters">Parameters</h4>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|object|true|none|
|» subscriptions|body|[string]|true|none|

> Example responses

> 200 Response

```json
{
  "payload": {
    "subscriptions": [
      "order",
      "marketing"
    ]
  }
}
```

<h4 id="put_v1-user-subscriptions-responses">Responses</h4>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|none|Inline|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|none|Inline|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Not authenticated to perform this action|None|

<h4 id="put_v1-user-subscriptions-responseschema">Response Schema</h4>

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
bearer
</aside>

<h2 id="user-auth-service-v1-user-profile">v1/user/profile</h2>

### GET_v1-user-profile

<a id="opIdGET_v1-user-profile"></a>

> Code samples

```shell
# You can also use wget
curl -X GET /v1/user/profile \
  -H 'Accept: application/json; charset=utf-8' \
  -H 'Authorization: API_KEY'

```

```javascript
var headers = {
  'Accept':'application/json; charset=utf-8',
  'Authorization':'API_KEY'

};

$.ajax({
  url: '/v1/user/profile',
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

fetch('/v1/user/profile',
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

r = requests.get('/v1/user/profile', params={

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

result = RestClient.get '/v1/user/profile',
  params: {
  }, headers: headers

p JSON.parse(result)

```

`GET /v1/user/profile`

*Get profile for user*

> Example responses

> 200 Response

```json
{
  "payload": {
    "firstName": "Genesis",
    "lastName": "Leannon",
    "birthDate": null,
    "gender": "m",
    "height": 180,
    "weight": 70,
    "mealsPerDay": 1,
    "nutritionGoalCustom": "{'fats': 25, 'carbs': 60, 'proteins': 150}",
    "phone": "(507) 332-5029",
    "address": "Konopelski Prairie",
    "postcode": "65230",
    "nutritionGoal": {
      "name": "Muscle Build",
      "alias": "muscle-build",
      "proteins": 10,
      "fats": 20,
      "carbs": 30
    },
    "activityLevel": {
      "name": "Lightly Active",
      "description": "Lightly Active description",
      "ratioPortion": 1.38
    },
    "additional": {
      "diets": [
        "197926f5-9c05-4ce7-8397-a8446ab5369e",
        "ed5a57cb-6f14-4a0a-91ff-dc79b441b70e"
      ],
      "allergens": [
        "0cbc4a8a-1c5d-4153-9d21-34388e269869",
        "4ea72d26-69f4-4645-86af-0d018b7751a9"
      ]
    }
  }
}
```

<h4 id="get_v1-user-profile-responses">Responses</h4>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|none|Inline|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Not authenticated to perform this action|None|

<h4 id="get_v1-user-profile-responseschema">Response Schema</h4>

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
bearer
</aside>

### POST_v1-user-profile-diets

<a id="opIdPOST_v1-user-profile-diets"></a>

> Code samples

```shell
# You can also use wget
curl -X POST /v1/user/profile/diets \
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
  url: '/v1/user/profile/diets',
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
  "type": "allergen"
}';
const headers = {
  'Content-Type':'application/json; charset=utf-8',
  'Accept':'application/json; charset=utf-8',
  'Authorization':'API_KEY'

};

fetch('/v1/user/profile/diets',
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

r = requests.post('/v1/user/profile/diets', params={

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

result = RestClient.post '/v1/user/profile/diets',
  params: {
  }, headers: headers

p JSON.parse(result)

```

`POST /v1/user/profile/diets`

*Add diets to user profile*

> Body parameter

```json
{
  "uuid": "string",
  "type": "allergen"
}
```

<h4 id="post_v1-user-profile-diets-parameters">Parameters</h4>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|object|true|none|
|» uuid|body|string|true|none|
|» type|body|string|true|none|

> Example responses

> 201 Response

```json
{
  "payload": {
    "firstName": "Genesis",
    "lastName": "Leannon",
    "birthDate": null,
    "gender": "m",
    "height": 180,
    "weight": 70,
    "mealsPerDay": 1,
    "nutritionGoalCustom": "{'fats': 25, 'carbs': 60, 'proteins': 150}",
    "phone": "(507) 332-5029",
    "address": "Konopelski Prairie",
    "postcode": "65230",
    "nutritionGoal": {
      "name": "Muscle Build",
      "alias": "muscle-build",
      "proteins": 10,
      "fats": 20,
      "carbs": 30
    },
    "activityLevel": {
      "name": "Lightly Active",
      "description": "Lightly Active description",
      "ratioPortion": 1.38
    },
    "additional": {
      "diets": [
        "197926f5-9c05-4ce7-8397-a8446ab5369e",
        "ed5a57cb-6f14-4a0a-91ff-dc79b441b70e"
      ],
      "allergens": [
        "0cbc4a8a-1c5d-4153-9d21-34388e269869",
        "4ea72d26-69f4-4645-86af-0d018b7751a9"
      ]
    }
  }
}
```

<h4 id="post_v1-user-profile-diets-responses">Responses</h4>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|201|[Created](https://tools.ietf.org/html/rfc7231#section-6.3.2)|none|Inline|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Not authenticated to perform this action|None|

<h4 id="post_v1-user-profile-diets-responseschema">Response Schema</h4>

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
bearer
</aside>

<h2 id="user-auth-service-v1-user-password">v1/user/password</h2>

### POST_v1-user-password-forgotten

<a id="opIdPOST_v1-user-password-forgotten"></a>

> Code samples

```shell
# You can also use wget
curl -X POST /v1/user/password/forgotten \
  -H 'Content-Type: application/json; charset=utf-8' \
  -H 'Accept: application/json' \
  -H 'tenant: string'

```

```javascript
var headers = {
  'Content-Type':'application/json; charset=utf-8',
  'Accept':'application/json',
  'tenant':'string'

};

$.ajax({
  url: '/v1/user/password/forgotten',
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
  "email": "string"
}';
const headers = {
  'Content-Type':'application/json; charset=utf-8',
  'Accept':'application/json',
  'tenant':'string'

};

fetch('/v1/user/password/forgotten',
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
  'Accept': 'application/json',
  'tenant': 'string'
}

r = requests.post('/v1/user/password/forgotten', params={

}, headers = headers)

print r.json()

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Content-Type' => 'application/json; charset=utf-8',
  'Accept' => 'application/json',
  'tenant' => 'string'
}

result = RestClient.post '/v1/user/password/forgotten',
  params: {
  }, headers: headers

p JSON.parse(result)

```

`POST /v1/user/password/forgotten`

*Send Forgotten token link for*

> Body parameter

```json
{
  "email": "string"
}
```

<h4 id="post_v1-user-password-forgotten-parameters">Parameters</h4>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|tenant|header|string|true|none|
|body|body|object|true|none|
|» email|body|string|true|none|

> Example responses

> 201 Response

```json
{
  "payload": true
}
```

<h4 id="post_v1-user-password-forgotten-responses">Responses</h4>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|201|[Created](https://tools.ietf.org/html/rfc7231#section-6.3.2)|none|Inline|

<h4 id="post_v1-user-password-forgotten-responseschema">Response Schema</h4>

<aside class="success">
This operation does not require authentication
</aside>

### GET_v1-user-password-forgotten-token

<a id="opIdGET_v1-user-password-forgotten-token"></a>

> Code samples

```shell
# You can also use wget
curl -X GET /v1/user/password/forgotten/{token} \
  -H 'Accept: application/json; charset=utf-8'

```

```javascript
var headers = {
  'Accept':'application/json; charset=utf-8'

};

$.ajax({
  url: '/v1/user/password/forgotten/{token}',
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

fetch('/v1/user/password/forgotten/{token}',
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

r = requests.get('/v1/user/password/forgotten/{token}', params={

}, headers = headers)

print r.json()

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json; charset=utf-8'
}

result = RestClient.get '/v1/user/password/forgotten/{token}',
  params: {
  }, headers: headers

p JSON.parse(result)

```

`GET /v1/user/password/forgotten/{token}`

*Check forgotten token*

<h4 id="get_v1-user-password-forgotten-token-parameters">Parameters</h4>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|token|path|string|true|none|

> Example responses

> 200 Response

```json
{
  "payload": true
}
```

<h4 id="get_v1-user-password-forgotten-token-responses">Responses</h4>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|none|Inline|

<h4 id="get_v1-user-password-forgotten-token-responseschema">Response Schema</h4>

<aside class="success">
This operation does not require authentication
</aside>

### PATCH_v1-user-password-forgotten-token

<a id="opIdPATCH_v1-user-password-forgotten-token"></a>

> Code samples

```shell
# You can also use wget
curl -X PATCH /v1/user/password/forgotten/{token} \
  -H 'Content-Type: application/json; charset=utf-8' \
  -H 'Accept: application/json; charset=utf-8'

```

```javascript
var headers = {
  'Content-Type':'application/json; charset=utf-8',
  'Accept':'application/json; charset=utf-8'

};

$.ajax({
  url: '/v1/user/password/forgotten/{token}',
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
  "password": "string"
}';
const headers = {
  'Content-Type':'application/json; charset=utf-8',
  'Accept':'application/json; charset=utf-8'

};

fetch('/v1/user/password/forgotten/{token}',
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
  'Content-Type': 'application/json; charset=utf-8',
  'Accept': 'application/json; charset=utf-8'
}

r = requests.patch('/v1/user/password/forgotten/{token}', params={

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

result = RestClient.patch '/v1/user/password/forgotten/{token}',
  params: {
  }, headers: headers

p JSON.parse(result)

```

`PATCH /v1/user/password/forgotten/{token}`

*Reset password by forgotten token*

> Body parameter

```json
{
  "password": "string"
}
```

<h4 id="patch_v1-user-password-forgotten-token-parameters">Parameters</h4>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|object|true|none|
|» password|body|string|true|none|
|token|path|string|true|none|

> Example responses

> 200 Response

```json
{
  "payload": true
}
```

<h4 id="patch_v1-user-password-forgotten-token-responses">Responses</h4>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|none|Inline|

<h4 id="patch_v1-user-password-forgotten-token-responseschema">Response Schema</h4>

<aside class="success">
This operation does not require authentication
</aside>

<h2 id="user-auth-service-v1-management-user">v1/management/user</h2>

### GET_v1-management-user

<a id="opIdGET_v1-management-user"></a>

> Code samples

```shell
# You can also use wget
curl -X GET /v1/management/user \
  -H 'Accept: application/json; charset=utf-8' \
  -H 'Authorization: API_KEY'

```

```javascript
var headers = {
  'Accept':'application/json; charset=utf-8',
  'Authorization':'API_KEY'

};

$.ajax({
  url: '/v1/management/user',
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

fetch('/v1/management/user',
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

r = requests.get('/v1/management/user', params={

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

result = RestClient.get '/v1/management/user',
  params: {
  }, headers: headers

p JSON.parse(result)

```

`GET /v1/management/user`

*Get list of users*

<h4 id="get_v1-management-user-parameters">Parameters</h4>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|limit|query|number|false|Limit the number of users returned (default 100)|
|page|query|number|false|Page number (default 1)|
|status|query|number|false|User status (active = 1, inactive = 0), if not specified all users are returned|
|search|query|string|false|Filter users by email and name (case insensitive)|

> Example responses

> 200 Response

```json
{
  "meta": {
    "limit": 100,
    "page": 1,
    "pageCount": 1,
    "totalCount": 2
  },
  "payload": [
    {
      "uuid": "55eb2fa3-9a2b-4ee1-8272-a1f06672af67",
      "profile": {
        "firstName": "Ana",
        "lastName": "Smith"
      },
      "role": {
        "name": "Admin",
        "uuid": "00faeafd-819d-47e8-a1d1-ef983b3f36a1"
      },
      "email": "ana@vitamojo.dev",
      "active": true,
      "storeUUID": "fe45bb11-3c1d-43a6-99f4-aaef947662d2"
    },
    {
      "uuid": "ec7f86d4-b371-4b4a-a50d-79f4a3a830fd",
      "profile": {
        "firstName": "Beth",
        "lastName": "Daniels"
      },
      "role": {
        "name": "Manager",
        "uuid": "f8b1b41d-36d1-4618-8926-7c2cadab4af0"
      },
      "email": "beth@vitamojo.dev",
      "active": true,
      "storeUUID": "fe45bb11-3c1d-43a6-99f4-aaef947662d2"
    }
  ]
}
```

<h4 id="get_v1-management-user-responses">Responses</h4>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|none|Inline|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Not authenticated to perform this action|None|

<h4 id="get_v1-management-user-responseschema">Response Schema</h4>

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
bearer
</aside>

### POST_v1-management-user

<a id="opIdPOST_v1-management-user"></a>

> Code samples

```shell
# You can also use wget
curl -X POST /v1/management/user \
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
  url: '/v1/management/user',
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
  "profile": {
    "firstName": "string",
    "lastName": "string",
    "phone": "string"
  },
  "role": {
    "uuid": "string",
    "slug": "string"
  },
  "email": "string",
  "active": true,
  "storeUUID": "string"
}';
const headers = {
  'Content-Type':'application/json; charset=utf-8',
  'Accept':'application/json; charset=utf-8',
  'Authorization':'API_KEY'

};

fetch('/v1/management/user',
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

r = requests.post('/v1/management/user', params={

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

result = RestClient.post '/v1/management/user',
  params: {
  }, headers: headers

p JSON.parse(result)

```

`POST /v1/management/user`

*Create new user*

> Body parameter

```json
{
  "profile": {
    "firstName": "string",
    "lastName": "string",
    "phone": "string"
  },
  "role": {
    "uuid": "string",
    "slug": "string"
  },
  "email": "string",
  "active": true,
  "storeUUID": "string"
}
```

<h4 id="post_v1-management-user-parameters">Parameters</h4>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|[ManagementCreateUpdate](#schemamanagementcreateupdate)|true|none|

> Example responses

> 201 Response

```json
{
  "payload": {
    "uuid": "55eb2fa3-9a2b-4ee1-8272-a1f06672af67",
    "profile": {
      "firstName": "Ana",
      "lastName": "Smith",
      "phone": "012345678"
    },
    "role": {
      "name": "Admin",
      "uuid": "00faeafd-819d-47e8-a1d1-ef983b3f36a1"
    },
    "email": "ana@vitamojo.dev",
    "active": true,
    "storeUUID": "fe45bb11-3c1d-43a6-99f4-aaef947662d2"
  }
}
```

<h4 id="post_v1-management-user-responses">Responses</h4>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|201|[Created](https://tools.ietf.org/html/rfc7231#section-6.3.2)|none|Inline|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Body is not valid|None|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Not authenticated to perform this action|None|

<h4 id="post_v1-management-user-responseschema">Response Schema</h4>

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
bearer
</aside>

### GET_v1-management-user-uuid

<a id="opIdGET_v1-management-user-uuid"></a>

> Code samples

```shell
# You can also use wget
curl -X GET /v1/management/user/{uuid} \
  -H 'Accept: application/json; charset=utf-8' \
  -H 'Authorization: API_KEY'

```

```javascript
var headers = {
  'Accept':'application/json; charset=utf-8',
  'Authorization':'API_KEY'

};

$.ajax({
  url: '/v1/management/user/{uuid}',
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

fetch('/v1/management/user/{uuid}',
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

r = requests.get('/v1/management/user/{uuid}', params={

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

result = RestClient.get '/v1/management/user/{uuid}',
  params: {
  }, headers: headers

p JSON.parse(result)

```

`GET /v1/management/user/{uuid}`

*Get user by UUID*

<h4 id="get_v1-management-user-uuid-parameters">Parameters</h4>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|uuid|path|string|true|none|

> Example responses

> 200 Response

```json
{
  "payload": {
    "uuid": "55eb2fa3-9a2b-4ee1-8272-a1f06672af67",
    "profile": {
      "firstName": "Ana",
      "lastName": "Smith",
      "phone": "012345678"
    },
    "role": {
      "name": "Admin",
      "uuid": "00faeafd-819d-47e8-a1d1-ef983b3f36a1"
    },
    "email": "ana@vitamojo.dev",
    "active": true,
    "storeUUID": "fe45bb11-3c1d-43a6-99f4-aaef947662d2"
  }
}
```

<h4 id="get_v1-management-user-uuid-responses">Responses</h4>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|none|Inline|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Not authenticated to perform this action|None|

<h4 id="get_v1-management-user-uuid-responseschema">Response Schema</h4>

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
bearer
</aside>

### PUT_v1-management-user-uuid

<a id="opIdPUT_v1-management-user-uuid"></a>

> Code samples

```shell
# You can also use wget
curl -X PUT /v1/management/user/{uuid} \
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
  url: '/v1/management/user/{uuid}',
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
  "profile": {
    "firstName": "string",
    "lastName": "string",
    "phone": "string"
  },
  "role": {
    "uuid": "string",
    "slug": "string"
  },
  "email": "string",
  "active": true,
  "storeUUID": "string"
}';
const headers = {
  'Content-Type':'application/json; charset=utf-8',
  'Accept':'application/json; charset=utf-8',
  'Authorization':'API_KEY'

};

fetch('/v1/management/user/{uuid}',
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

r = requests.put('/v1/management/user/{uuid}', params={

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

result = RestClient.put '/v1/management/user/{uuid}',
  params: {
  }, headers: headers

p JSON.parse(result)

```

`PUT /v1/management/user/{uuid}`

*Update user (including profile and role)*

> Body parameter

```json
{
  "profile": {
    "firstName": "string",
    "lastName": "string",
    "phone": "string"
  },
  "role": {
    "uuid": "string",
    "slug": "string"
  },
  "email": "string",
  "active": true,
  "storeUUID": "string"
}
```

<h4 id="put_v1-management-user-uuid-parameters">Parameters</h4>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|[ManagementCreateUpdate](#schemamanagementcreateupdate)|true|none|
|uuid|path|string|true|none|

> Example responses

> 200 Response

```json
{
  "payload": {
    "uuid": "55eb2fa3-9a2b-4ee1-8272-a1f06672af67",
    "profile": {
      "firstName": "Ana",
      "lastName": "Smith",
      "phone": "012345678"
    },
    "role": {
      "name": "Admin",
      "uuid": "00faeafd-819d-47e8-a1d1-ef983b3f36a1"
    },
    "email": "ana@vitamojo.dev",
    "active": true,
    "storeUUID": "fe45bb11-3c1d-43a6-99f4-aaef947662d2"
  }
}
```

<h4 id="put_v1-management-user-uuid-responses">Responses</h4>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|none|Inline|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Body is not valid|None|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Not authenticated to perform this action|None|

<h4 id="put_v1-management-user-uuid-responseschema">Response Schema</h4>

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
bearer
</aside>

<h2 id="user-auth-service-v1-management-role">v1/management/role</h2>

### GET_v1-management-role

<a id="opIdGET_v1-management-role"></a>

> Code samples

```shell
# You can also use wget
curl -X GET /v1/management/role \
  -H 'Accept: application/json; charset=utf-8' \
  -H 'Authorization: API_KEY'

```

```javascript
var headers = {
  'Accept':'application/json; charset=utf-8',
  'Authorization':'API_KEY'

};

$.ajax({
  url: '/v1/management/role',
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

fetch('/v1/management/role',
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

r = requests.get('/v1/management/role', params={

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

result = RestClient.get '/v1/management/role',
  params: {
  }, headers: headers

p JSON.parse(result)

```

`GET /v1/management/role`

*Get list of roles*

> Example responses

> 200 Response

```json
{
  "payload": [
    {
      "name": "Admin",
      "uuid": "00faeafd-819d-47e8-a1d1-ef983b3f36a1"
    },
    {
      "name": "Manager",
      "uuid": "f8b1b41d-36d1-4618-8926-7c2cadab4af0"
    }
  ]
}
```

<h4 id="get_v1-management-role-responses">Responses</h4>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|none|Inline|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Not authenticated to perform this action|None|

<h4 id="get_v1-management-role-responseschema">Response Schema</h4>

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
bearer
</aside>

## Schemas

<h3 id="tocSmanagementcreateupdate">ManagementCreateUpdate</h3>

<a id="schemamanagementcreateupdate"></a>

```json
{
  "profile": {
    "firstName": "string",
    "lastName": "string",
    "phone": "string"
  },
  "role": {
    "uuid": "string",
    "slug": "string"
  },
  "email": "string",
  "active": true,
  "storeUUID": "string"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|profile|object|true|none|none|
|» firstName|string|true|none|none|
|» lastName|string|true|none|none|
|» phone|string|true|none|none|
|role|object|true|none|none|
|» uuid|string|true|none|none|
|» slug|string|true|none|none|
|email|string|true|none|none|
|active|boolean|true|none|none|
|storeUUID|string|false|none|none|

