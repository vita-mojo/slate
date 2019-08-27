---
title: Tenant Service
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

<h1 id="tenant-service">Tenant Service</h1>

> Scroll down for code samples, example requests and responses. Select a language for code samples from the tabs above or the mobile navigation menu.

Tenant Microservice API

<h2 id="tenant-service-healthcheck">Healthcheck</h2>

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

<h2 id="tenant-service-bootstrap">Bootstrap</h2>

### Get Bootstrap

<a id="opIdGet Bootstrap"></a>

> Code samples

```shell
# You can also use wget
curl -X GET /v1/bootstrap \
  -H 'Accept: application/json; charset=utf-8' \
  -H 'tenant: string' \
  -H 'origin: string' \
  -H 'referer: string' \
  -H 'x-requested-from: string'

```

```javascript
var headers = {
  'Accept':'application/json; charset=utf-8',
  'tenant':'string',
  'origin':'string',
  'referer':'string',
  'x-requested-from':'string'

};

$.ajax({
  url: '/v1/bootstrap',
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
  'tenant':'string',
  'origin':'string',
  'referer':'string',
  'x-requested-from':'string'

};

fetch('/v1/bootstrap',
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
  'tenant': 'string',
  'origin': 'string',
  'referer': 'string',
  'x-requested-from': 'string'
}

r = requests.get('/v1/bootstrap', params={

}, headers = headers)

print r.json()

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json; charset=utf-8',
  'tenant' => 'string',
  'origin' => 'string',
  'referer' => 'string',
  'x-requested-from' => 'string'
}

result = RestClient.get '/v1/bootstrap',
  params: {
  }, headers: headers

p JSON.parse(result)

```

`GET /v1/bootstrap`

*Deep integrations only! Get bootstrap data*

Get bootstrap data for the selected tenant.
If tenant UUID is missing from headers, tenant will be automatically detected from the hostname.

<h4 id="get-bootstrap-parameters">Parameters</h4>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|tenant|header|string|false|Tenant UUID|
|origin|header|string|false|Origin request header, used to detect tenant if tenant UUID is missing in headers|
|referer|header|string|false|Referer request header, used to detect tenant if tenant UUID and origin header are missing|
|x-requested-from|header|string|false|Identifies the app making the request (kiosk, pos, preorder)|

> Example responses

> 200 Response

```json
{
  "payload": {
    "tenant": {
      "name": "Vitamojo",
      "alias": "vitamojo",
      "description": "Vitamojo Restaurant",
      "uuid": "832b34ad-2608-4cc7-bee8-bfc47686d801",
      "settings": {
        "app.webUrl": "https://vmos2-staging-kiosk.vitamojo.com",
        "bugsnag.apiKey": "e34171bd3be15f23403e7616d5e219c2",
        "email.default": "support@vitamojo.com",
        "email.instore.text": "",
        "order.automaticallyMoveToPreparation": "1",
        "order.takeaway.default": "1",
        "vat.rate.eatIn": "18",
        "vat.rate.takeaway": "20",
        "nutrition.disclaimer.enabled": "1",
        "nutrition.disclaimer.text": "Lorem ipsum dolor sit amet, consectetur adipiscing elit. Curabitur est arcu, tincidunt non urna hendrerit, pretium volutpat justo. Integer quam felis, ullamcorper eget eros egestas, tincidunt posuere nisl. Pellentesque sagittis odio sit amet lacinia tempus. Class aptent taciti sociosqu ad litora torquent per conubia nostra, per inceptos himenaeos. Sed et diam sem."
      },
      "i18n": {
        "payload": {
          "common": {
            "priceFrom": "From {{price}}",
            "loading": "Loading"
          },
          "buttons": {
            "cancelOrder": "Cancel Order",
            "addAnother": "Add Another",
            "backToMenu": "Back to Menu"
          },
          "checkout": {
            "myOrder": "My order",
            "discountApplied": "{{discount}} discount applied",
            "codeExpires": "Code: {{couponCode}} - expires {expireDate}"
          },
          "dietAllergies": {
            "filterMenu": "Filter menu",
            "toolTipText": "Filter by nutrition and allergens",
            "allergensTooltipLine1": "Tap on the filters below to make the menu yours.",
            "allergensTooltipLine2": "Sign up so we can remember your settings for next time",
            "signIn": "Sign in",
            "done": "Done",
            "dietTitle": "Only Show",
            "allergenTitle": "Filter out Allergens",
            "allergenDescription": "- if you have a severe allergy please talk to a staff member"
          },
          "footer": {
            "viewOrder ": "View order",
            "addToOrderButton": "Add to order",
            "goToNextStep": "Continue to {{nextStep}}",
            "goToReview": "Continue to review"
          },
          "modifiers": {
            "unit": "{{unitValue}} of {{unitName}}"
          },
          "nutrition": {
            "fats": "Fats {{fats}}g",
            "carbs": "Carbs {{carbs}}g",
            "proteins": "Proteins {{proteins}}g",
            "calories": "{{calories}} Kcals",
            "nutritionPlateTitle": "My Order",
            "nutritionPlateDescription": "Add meals/items to see nutrition totals."
          },
          "notifications": {
            "rotateYourPhone": "This app is designed to be used in Portrait mode. \nPlease rotate your phone"
          },
          "offers": {
            "offerDescription": "Opt in to promotions and offers"
          },
          "stripeElements": {
            "cvc": "Card CVC",
            "cardExpiry": "Expires on",
            "cardNumber": "Card number"
          },
          "tile": {
            "soldOut": "Sold out",
            "soldOutItems": "Sold out ingredients",
            "calories": "{{calories}} Kcals"
          },
          "validations": {
            "isRequired": "Required field.",
            "invalidEmail": "Invalid email.",
            "isLength": "This field should contain {{minCharacters}} characters."
          },
          "errors": {
            "invalidProvider": "Invalid strategy provided: {{strategy}}",
            "noPayment": "No payment data provided",
            "createTransaction": "Method createTransaction needs to be overridden",
            "createCustomerCard": "Method createCustomerCard needs to be overridden"
          },
          "auth.login": {
            "company_login_header": "Login"
          },
          "storeSelection": {
            "chefsSpecials": "Chefs specials",
            "backToMenu": "Back to Menu"
          },
          "profile.settings": {
            "marketing": "Marketing",
            "sendPromotionsAndOffers": "Send me promotions and offers"
          },
          "profile.orderHistory": {
            "noOrders": "No orders to display",
            "orderSerial": "Order {{serialNumber}} - {{totalAmount}}",
            "cancelOrder": "Cancel"
          },
          "profile.orderDetails": {
            "orderSerial": "Order {{serialNumber}}",
            "myLunch": "My lunch"
          },
          "profile.header": {
            "myOrders": "My Orders",
            "mySettings": "My Settings",
            "signOut": "Sign out"
          },
          "payment": {
            "pay": "Pay now",
            "processingPayment": "Processing Payment"
          },
          "payment.customerCard": {
            "expDate": "Exp. {{month}} \\ {{year}}"
          },
          "payment.customerCards": {
            "header": "Payment",
            "subHeader": "Choose from the options from below",
            "addCard": "Add card",
            "addPromoCode": "Add promo code"
          },
          "payment.orderSummary": {
            "myOrder": "My Order",
            "pickupTimeSubHeader": "{{minutes}} from now"
          },
          "payment.timeSlots": {
            "header": "Pick up time",
            "subHeader": "Choose the time when you will be able to pick up your meal",
            "timeSlotFull": "Time slot full",
            "now": "Now",
            "availableIn": "in {{remainingMinutes}} mins"
          },
          "payment.kiosk": {
            "header": "Payment",
            "headerUserNameForm": "Add your name",
            "subHeaderProcessingPaymentState": "Processing payment",
            "subHeaderCardDeclinedState": "Card declined",
            "retryPayment": "Retry payment",
            "paymentError": "Sorry looks like there was a problem with your payment.",
            "payAtTill": "Pay at till",
            "footerProcessingState": "Processing Payment",
            "footerLoadingState": "Loading...",
            "footerReadyState": "Pay now",
            "enterName": "Enter your name",
            "nameValidationMessage": "Please add your name"
          },
          "payment.stripe": {
            "header": "Payment",
            "subHeader": "Please fill out the fields below",
            "footerLoadingState": "Loading...",
            "footerReadyState": "add card"
          },
          "passwordRecovery": {
            "header": "Reset password"
          },
          "passwordRecovery.form": {
            "password": "Password",
            "confirmPassword": "Confirm Password",
            "confirmPasswordValidation": "Password confirmation should match with password",
            "submitButton": "Set Password"
          },
          "forgottenPassword": {
            "header": "Reset password"
          },
          "forgottenPassword.form": {
            "email": "Email",
            "submitButton": "Reset Password"
          },
          "orderConfirmation": {
            "header": "Order placed",
            "footerButtonOnline": "Return to menu",
            "footerButtonKiosk": "Place new order",
            "thankYouText": "Thanks <1>{{name}}</1>",
            "orderNumber": "Your order number is <1>{{serialNumber}}</1>",
            "collectMealAt": "Please collect your meal at",
            "timeSlotSubTitle": "{{time}} from now",
            "collectFrom": "Please collect your meal from",
            "emailReceipt": "Email me the receipt",
            "guest": "Guest"
          },
          "orderConfirmation.emailReceipt": {
            "header": "Email receipt",
            "submitButton": "Send",
            "subscribe": "Opt in to promotions and offers",
            "cancel": "Cancel"
          },
          "mealBuilder.review": {
            "soldOutIngredient": "Sold out ingredient",
            "reviewSoldOutItemToOrder": "Review and change items to order",
            "addToOrder": "Add to order",
            "changeItem": "Change Item",
            "helperTextFirstLineDesktop": "See the ingredients on the left. Tap on them to adjust them.",
            "helperTextFirstLineMobile": "See the ingredients on the top. Tap on them to adjust them.",
            "helperTextSecondLine": "When you are happy with your choices, tap add to basket."
          },
          "customization": {
            "addToOrder": "Add to order",
            "helperTextFirstLineDesktop": "See the ingredients on the left. Tap on them to adjust them.",
            "helperTextFirstLineMobile": "See the ingredients on the top. Tap on them to adjust them.",
            "helperTextSecondLine": "When you are happy with your choices, tap add to basket."
          },
          "cart": {
            "header": "My Order",
            "placeOrderButton": "Place Order",
            "customiseBundle": "customise"
          },
          "bundles": {
            "noProducts": "No products to display",
            "calories": "{{calories}} Kcals"
          },
          "auth": {
            "header": "Log In or Register",
            "email": "Email address",
            "submitButton": "Next"
          },
          "auth.signIn.form": {
            "password": "Password",
            "passwordRequiredValidation": "Password is required.",
            "forgottenPassword": "Forgotten password?",
            "submitButton": "Log In"
          },
          "auth.signUp.form": {
            "name": "Name",
            "password": "Password",
            "subscribe": "Opt in to promotions and offers",
            "submitButton": "Sign Up In"
          }
        }
      },
      "theme": {
        "default": {
          "typography": {},
          "favicon": "https://s3.vitamojo.com/static/favicon.ico",
          "logo": {
            "size": 60,
            "image": "https://s3.vitamojo.com/static/vm-logo.svg",
            "imageSm": "https://s3.vitamojo.com/static/logo-sm.svg"
          },
          "common": {
            "height": "",
            "width": "",
            "primaryBgColor": "#cdcdcd",
            "secondaryBgColor": "#ffffff ",
            "primaryTextColor": "#484b56",
            "secondaryTextColor": "#ffffff"
          },
          "button": {
            "height": "",
            "width": "",
            "primaryBgColor": "#484b56",
            "secondaryBgColor": "#ffffff ",
            "primaryTextColor": "#ffffff",
            "secondaryTextColor": "#484b56"
          },
          "header": {
            "height": "90px",
            "width": "",
            "primaryBgColor": "#cdcdcd",
            "secondaryBgColor": "#ffffff",
            "primaryTextColor": "#484b56",
            "secondaryTextColor": "#ffffff",
            "text": {
              "active": "#384043",
              "default": "#384043",
              "disabled": "#e2e3e3"
            }
          },
          "footer": {
            "height": "90px",
            "primaryBgColor": "#f9f9f9"
          },
          "menu": {
            "height": "",
            "width": "",
            "primaryBgColor": "#cdcdcd",
            "secondaryBgColor": "#ffffff ",
            "primaryTextColor": "#484b56",
            "secondaryTextColor": "#ffffff",
            "backgroundImage": "https://s3.vitamojo.com/static/bundles-background.jpg"
          },
          "contextPanel": {
            "height": "95vh",
            "width": "460px",
            "notificationHeight": "40px",
            "primaryBgColor": "rgba(249, 249, 249, 0.95)",
            "secondaryBgColor": "#ffffff ",
            "primaryTextColor": "#484b56",
            "secondaryTextColor": "#ffffff",
            "borderColor": "#e5e5e5",
            "footerHeight": "50px",
            "stateColor": {
              "default": "#979c9d",
              "success": "",
              "error": "#ca1010"
            },
            "header": {
              "height": "100px"
            }
          },
          "cart": {
            "backgroundImage": "https://s3.vitamojo.com/static/bag.jpg"
          },
          "payment": {
            "backgroundImage": "https://s3.vitamojo.com/static/vitamojo.jpg"
          },
          "addCard": {
            "backgroundImage": "https://s3.vitamojo.com/static/add-card-background.jpg"
          },
          "orderConfirmation": {
            "kioskBackgroundImage": "https://s3.vitamojo.com/static/kiosk-confirmation-bg.jpg",
            "backgroundImage": "https://s3.vitamojo.com/static/map.jpg"
          },
          "orderHistory": {
            "kioskBackgroundImage": "https://s3.vitamojo.com/static/vitamojo.jpg",
            "backgroundImage": "https://s3.vitamojo.com/static/vitamojo.jpg"
          },
          "auth": {
            "backgroundImage": "https://s3.vitamojo.com/static/bundles-background.jpg"
          }
        }
      }
    },
    "stores": [
      {
        "uuid": "876b34ad-45654-4ds7-cdd8-bfc47686d999",
        "sortOrder": 1,
        "name": "VitaMojo",
        "address": "22 Carter Ln, London EC4V 5AD",
        "email": "carterlane@vitamojo.com",
        "status": true,
        "ordersPerSlot": 32,
        "slotsInterval": 10,
        "url": "vitamojo.com",
        "vatNumber": "GB 123456789",
        "lat": "51.518832",
        "long": "-0.077464",
        "theme": {
          "default": {
            "logo": "https://s3-eu-west-1.amazonaws.com/vitamojo.com-uploads-staging/vmos2/logos/User-ID-button.svg",
            "menu": {
              "width": "",
              "height": "",
              "primaryBgColor": "#cdcdcd",
              "primaryTextColor": "#484b56",
              "secondaryBgColor": "#ffffff ",
              "secondaryTextColor": "#ffffff"
            },
            "button": {
              "width": "",
              "height": "",
              "primaryBgColor": "#82d500",
              "primaryTextColor": "#ffffff",
              "secondaryBgColor": "#ffffff ",
              "secondaryTextColor": "#484b56"
            },
            "common": {
              "width": "",
              "height": "",
              "primaryBgColor": "#cdcdcd",
              "primaryTextColor": "#484b56",
              "secondaryBgColor": "#ffffff ",
              "secondaryTextColor": "#ffffff"
            },
            "footer": {
              "height": "90px",
              "primaryBgColor": "#e6e6e6"
            },
            "header": {
              "width": "",
              "height": "90px",
              "primaryBgColor": "#e6e6e6",
              "primaryTextColor": "#484b56",
              "secondaryBgColor": "#82d500",
              "secondaryTextColor": "#ffffff"
            },
            "typography": {},
            "contextPanel": {
              "width": "400px",
              "height": "90%",
              "borderColor": "#ffffff",
              "footerHeight": "90px",
              "primaryBgColor": "#F7F7F7",
              "primaryTextColor": "#484b56",
              "secondaryBgColor": "#ffffff ",
              "secondaryTextColor": "#ffffff"
            }
          }
        },
        "settings": {
          "notifications": {
            "key": "a983EKKzCnG2YcMg3NPC",
            "options": {
              "channel": "540da1f34a44fdd3130e6178afb2426610156a161a0f1bcd3a0b80c839d1b95c",
              "cluster": "eu",
              "encrypted": "false"
            }
          },
          "hasTableService": "0",
          "hasTables": "1",
          "isRequiredTableNr": "0",
          "hidePaidOrdersOnPickup": "0",
          "includeInOwnDelivery": "0",
          "printReceiptWhenOrderIsPlaced": "0"
        }
      },
      {
        "uuid": "963b34ad-45654-4ds7-cdd8-bfc47686d345",
        "sortOrder": 2,
        "name": "Bruno's Coffee",
        "address": "22 Carter Ln, London EC4V 5AD",
        "email": "carterlane@vitamojo.com",
        "status": true,
        "ordersPerSlot": 32,
        "slotsInterval": 10,
        "url": "vitamojo.com",
        "vatNumber": "GB 123456789",
        "lat": "51.518832",
        "long": "-0.077464",
        "theme": {
          "payload": {
            "logo": "https://s3-eu-west-1.amazonaws.com/vitamojo.com-uploads-staging/vmos2/logos/User-ID-button.svg",
            "menu": {
              "width": "",
              "height": "",
              "primaryBgColor": "#cdcdcd",
              "primaryTextColor": "#484b56",
              "secondaryBgColor": "#ffffff ",
              "secondaryTextColor": "#ffffff"
            },
            "button": {
              "width": "",
              "height": "",
              "primaryBgColor": "#82d500",
              "primaryTextColor": "#ffffff",
              "secondaryBgColor": "#ffffff ",
              "secondaryTextColor": "#484b56"
            },
            "common": {
              "width": "",
              "height": "",
              "primaryBgColor": "#cdcdcd",
              "primaryTextColor": "#484b56",
              "secondaryBgColor": "#ffffff ",
              "secondaryTextColor": "#ffffff"
            },
            "footer": {
              "height": "90px",
              "primaryBgColor": "#e6e6e6"
            },
            "header": {
              "width": "",
              "height": "90px",
              "primaryBgColor": "#e6e6e6",
              "primaryTextColor": "#484b56",
              "secondaryBgColor": "#82d500",
              "secondaryTextColor": "#ffffff"
            },
            "typography": {},
            "contextPanel": {
              "width": "400px",
              "height": "90%",
              "borderColor": "#ffffff",
              "footerHeight": "90px",
              "primaryBgColor": "#F7F7F7",
              "primaryTextColor": "#484b56",
              "secondaryBgColor": "#ffffff ",
              "secondaryTextColor": "#ffffff"
            }
          },
          "uuid": "ewqeq-eqweqwdfs"
        },
        "settings": {
          "notifications": {
            "key": "a983EKKzCnG2YcMg3NPC",
            "options": {
              "channel": "540da1f34a44fdd3130e6178afb2426610156a161a0f1bcd3a0b80c839d1b95c",
              "cluster": "eu",
              "encrypted": "false"
            }
          },
          "hasTableService": "0",
          "hasTables": "1",
          "isRequiredTableNr": "0",
          "hidePaidOrdersOnPickup": "0",
          "includeInOwnDelivery": "0",
          "printReceiptWhenOrderIsPlaced": "0"
        }
      }
    ],
    "features": {
      "epos": false,
      "nutrition": false
    }
  }
}
```

> 400 Response

```json
{
  "tenant_not_found_by_criteria": {
    "statusCode": 400,
    "timestamp": "2019-01-30T15:28:39.233Z",
    "path": "/tenant/v1/bootstrap",
    "message": "Tenant not found by queried criteria",
    "stack": null
  },
  "tenant_uuid_or_host_required": {
    "statusCode": 400,
    "timestamp": "2019-01-30T15:28:39.233Z",
    "path": "/tenant/v1/bootstrap",
    "message": "Either the hostname should be linked to a tenant or tenant UUID should be set in query params",
    "stack": null
  },
  "requested_from_not_valid": {
    "statusCode": 400,
    "timestamp": "2019-01-30T15:28:39.233Z",
    "path": "/tenant/v1/bootstrap",
    "message": "Value of X-Requested-From header is not valid",
    "stack": null
  }
}
```

<h4 id="get-bootstrap-responses">Responses</h4>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|none|[Bootstrap](#schemabootstrap)|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Some samples of bad request response|Inline|

<h4 id="get-bootstrap-responseschema">Response Schema</h4>

<aside class="success">
This operation does not require authentication
</aside>

<h2 id="tenant-service-settings">Settings</h2>

### Get Settings

<a id="opIdGet Settings"></a>

> Code samples

```shell
# You can also use wget
curl -X GET /v1/settings \
  -H 'Accept: application/json; charset=utf-8' \
  -H 'tenant: string' \
  -H 'Authorization: API_KEY'

```

```javascript
var headers = {
  'Accept':'application/json; charset=utf-8',
  'tenant':'string',
  'Authorization':'API_KEY'

};

$.ajax({
  url: '/v1/settings',
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
  'tenant':'string',
  'Authorization':'API_KEY'

};

fetch('/v1/settings',
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
  'tenant': 'string',
  'Authorization': 'API_KEY'
}

r = requests.get('/v1/settings', params={

}, headers = headers)

print r.json()

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json; charset=utf-8',
  'tenant' => 'string',
  'Authorization' => 'API_KEY'
}

result = RestClient.get '/v1/settings',
  params: {
  }, headers: headers

p JSON.parse(result)

```

`GET /v1/settings`

*Deep integrations only! Get all settings*

<h4 id="get-settings-parameters">Parameters</h4>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|tenant|header|string|false|Tenant UUID|

> Example responses

> 200 Response

```json
{
  "payload": [
    {
      "uuid": "00f41001-6bc0-4e7b-b1ee-b116bab89be9",
      "key": "app.webUrl",
      "value": "https://vmos2-staging-kiosk.vitamojo.com",
      "type": "all",
      "description": "App web url"
    },
    {
      "uuid": "7a99f5d3-7305-4722-9eed-b02a6a61e05e",
      "key": "app.managementUrl",
      "value": "https://vmos2.vmos-qa.com",
      "type": "all",
      "description": "Management app url"
    }
  ]
}
```

<h4 id="get-settings-responses">Responses</h4>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|none|[Settings](#schemasettings)|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Not authenticated to perform this action|None|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
bearer ( Scopes: SUPER_ADMIN ), bearer
</aside>

### Create Setting

<a id="opIdCreate Setting"></a>

> Code samples

```shell
# You can also use wget
curl -X POST /v1/settings \
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
  url: '/v1/settings',
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
  "key": "string",
  "value": "string",
  "type": "kiosk",
  "description": "string"
}';
const headers = {
  'Content-Type':'application/json; charset=utf-8',
  'Accept':'application/json; charset=utf-8',
  'Authorization':'API_KEY'

};

fetch('/v1/settings',
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

r = requests.post('/v1/settings', params={

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

result = RestClient.post '/v1/settings',
  params: {
  }, headers: headers

p JSON.parse(result)

```

`POST /v1/settings`

*Deep integrations only! Create a new setting*

> Body parameter

```json
{
  "key": "string",
  "value": "string",
  "type": "kiosk",
  "description": "string"
}
```

<h4 id="create-setting-parameters">Parameters</h4>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|[SettingReq](#schemasettingreq)|true|none|

> Example responses

> 201 Response

```json
{
  "payload": {
    "uuid": "00f41001-6bc0-4e7b-b1ee-b116bab89be9",
    "key": "app.webUrl",
    "value": "https://vmos2-staging-kiosk.vitamojo.com",
    "type": "all",
    "description": "App web url"
  }
}
```

<h4 id="create-setting-responses">Responses</h4>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|201|[Created](https://tools.ietf.org/html/rfc7231#section-6.3.2)|Setting created successfully|[Setting](#schemasetting)|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Body is not valid|None|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Not authenticated to perform this action|None|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
bearer ( Scopes: SUPER_ADMIN ), bearer
</aside>

### Get Setting

<a id="opIdGet Setting"></a>

> Code samples

```shell
# You can also use wget
curl -X GET /v1/settings/{settingUUID} \
  -H 'Accept: application/json; charset=utf-8' \
  -H 'Authorization: API_KEY'

```

```javascript
var headers = {
  'Accept':'application/json; charset=utf-8',
  'Authorization':'API_KEY'

};

$.ajax({
  url: '/v1/settings/{settingUUID}',
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

fetch('/v1/settings/{settingUUID}',
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

r = requests.get('/v1/settings/{settingUUID}', params={

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

result = RestClient.get '/v1/settings/{settingUUID}',
  params: {
  }, headers: headers

p JSON.parse(result)

```

`GET /v1/settings/{settingUUID}`

*Deep integrations only! Get one setting by UUID*

<h4 id="get-setting-parameters">Parameters</h4>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|settingUUID|path|string|true|Setting UUID|

> Example responses

> 200 Response

```json
{
  "payload": {
    "uuid": "00f41001-6bc0-4e7b-b1ee-b116bab89be9",
    "key": "app.webUrl",
    "value": "https://vmos2-staging-kiosk.vitamojo.com",
    "type": "all",
    "description": "App web url"
  }
}
```

<h4 id="get-setting-responses">Responses</h4>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|none|[Setting](#schemasetting)|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Setting not found|None|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Not authenticated to perform this action|None|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
bearer ( Scopes: SUPER_ADMIN ), bearer
</aside>

### Update Setting

<a id="opIdUpdate Setting"></a>

> Code samples

```shell
# You can also use wget
curl -X PUT /v1/settings/{settingUUID} \
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
  url: '/v1/settings/{settingUUID}',
  method: 'put',

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
  'Authorization':'API_KEY'

};

fetch('/v1/settings/{settingUUID}',
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

r = requests.put('/v1/settings/{settingUUID}', params={

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

result = RestClient.put '/v1/settings/{settingUUID}',
  params: {
  }, headers: headers

p JSON.parse(result)

```

`PUT /v1/settings/{settingUUID}`

*Deep integrations only! Update a setting by UUID*

> Body parameter

```json
{}
```

<h4 id="update-setting-parameters">Parameters</h4>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|object|true|none|
|settingUUID|path|string|true|Setting UUID|

> Example responses

> 200 Response

```json
{
  "payload": {
    "uuid": "00f41001-6bc0-4e7b-b1ee-b116bab89be9",
    "key": "app.webUrl",
    "value": "https://vmos2-staging-kiosk.vitamojo.com",
    "type": "all",
    "description": "App web url"
  }
}
```

<h4 id="update-setting-responses">Responses</h4>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|none|[Setting](#schemasetting)|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Setting not found or body is not valid|None|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Not authenticated to perform this action|None|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
bearer ( Scopes: SUPER_ADMIN ), bearer
</aside>

### Delete Setting

<a id="opIdDelete Setting"></a>

> Code samples

```shell
# You can also use wget
curl -X DELETE /v1/settings/{settingUUID} \
  -H 'Accept: application/json; charset=utf-8' \
  -H 'Authorization: API_KEY'

```

```javascript
var headers = {
  'Accept':'application/json; charset=utf-8',
  'Authorization':'API_KEY'

};

$.ajax({
  url: '/v1/settings/{settingUUID}',
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

fetch('/v1/settings/{settingUUID}',
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

r = requests.delete('/v1/settings/{settingUUID}', params={

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

result = RestClient.delete '/v1/settings/{settingUUID}',
  params: {
  }, headers: headers

p JSON.parse(result)

```

`DELETE /v1/settings/{settingUUID}`

*Deep integrations only! Delete a setting by UUID*

<h4 id="delete-setting-parameters">Parameters</h4>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|settingUUID|path|string|true|Setting UUID|

> Example responses

> 200 Response

```json
{}
```

<h4 id="delete-setting-responses">Responses</h4>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|none|Inline|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Setting not found|None|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Not authenticated to perform this action|None|

<h4 id="delete-setting-responseschema">Response Schema</h4>

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
bearer ( Scopes: SUPER_ADMIN ), bearer
</aside>

<h2 id="tenant-service-stores">Stores</h2>

### Get Stores

<a id="opIdGet Stores"></a>

> Code samples

```shell
# You can also use wget
curl -X GET /v1/stores \
  -H 'Accept: application/json; charset=utf-8' \
  -H 'Authorization: API_KEY'

```

```javascript
var headers = {
  'Accept':'application/json; charset=utf-8',
  'Authorization':'API_KEY'

};

$.ajax({
  url: '/v1/stores',
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

fetch('/v1/stores',
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

r = requests.get('/v1/stores', params={

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

result = RestClient.get '/v1/stores',
  params: {
  }, headers: headers

p JSON.parse(result)

```

`GET /v1/stores`

*Deep integrations only! Get all stores*

> Example responses

> 200 Response

```json
{
  "payload": [
    {
      "uuid": "876b34ad-45654-4ds7-cdd8-bfc47686d999",
      "name": "St. Paul's",
      "status": true,
      "ordersPerSlot": 10,
      "slotsInterval": 5,
      "address": "22 Carter Lane, London EC4V 5AD",
      "url": "vitamojo.com",
      "vatNumber": "GB 123456789",
      "email": "carterlane@vitamojo.com",
      "lat": "51.52",
      "long": "-0.08",
      "sortOrder": 1,
      "tenant": {
        "name": "Vitamojo",
        "uuid": "f006b92c-20a7-4192-a16a-29fea272191a"
      }
    },
    {
      "uuid": "27a0e850-b2de-41fc-b37a-726de0d7827b",
      "name": "Chilango",
      "status": true,
      "ordersPerSlot": 10,
      "slotsInterval": 5,
      "address": "22 Carter Lane, London EC4V 5AD",
      "url": "https://vmos2.vmos-qa.com",
      "vatNumber": "GB 123456789",
      "email": "carterlane@vitamojo.com",
      "lat": "51.52",
      "long": "-0.08",
      "sortOrder": null,
      "tenant": {
        "name": "Vitamojo",
        "uuid": "f006b92c-20a7-4192-a16a-29fea272191a"
      }
    },
    {
      "uuid": "fe45bb11-3c1d-43a6-99f4-aaef947662d2",
      "name": "Olive&Squash",
      "status": true,
      "ordersPerSlot": 10,
      "slotsInterval": 5,
      "address": "22 Carter Lane, London EC4V 5AD",
      "url": "https://vmos2.vmos-qa.com",
      "vatNumber": "GB 123456789",
      "email": "carterlane@vitamojo.com",
      "lat": "51.52",
      "long": "-0.08",
      "sortOrder": null,
      "tenant": {
        "name": "Vitamojo",
        "uuid": "f006b92c-20a7-4192-a16a-29fea272191a"
      }
    },
    {
      "uuid": "10f14f8a-ba1b-4f1d-bbad-02a5da10e593",
      "name": "YO! Sushi",
      "status": true,
      "ordersPerSlot": 10,
      "slotsInterval": 5,
      "address": "22 Carter Lane, London EC4V 5AD",
      "url": "https://vmos2.vmos-qa.com",
      "vatNumber": "GB 123456789",
      "email": "carterlane@vitamojo.com",
      "lat": "51.52",
      "long": "-0.08",
      "sortOrder": null,
      "tenant": {
        "name": "Vitamojo",
        "uuid": "f006b92c-20a7-4192-a16a-29fea272191a"
      }
    },
    {
      "uuid": "1d5d1a18-af02-4d3f-beae-26ba392bf9a8",
      "name": "KnightFrank",
      "status": true,
      "ordersPerSlot": 10,
      "slotsInterval": 5,
      "address": "22 Carter Lane, London EC4V 5AD",
      "url": "https://vmos2.vmos-qa.com",
      "vatNumber": "GB 123456789",
      "email": "carterlane@vitamojo.com",
      "lat": "51.52",
      "long": "-0.08",
      "sortOrder": null,
      "tenant": {
        "name": "Vitamojo",
        "uuid": "f006b92c-20a7-4192-a16a-29fea272191a"
      }
    }
  ]
}
```

<h4 id="get-stores-responses">Responses</h4>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|none|Inline|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Not authenticated to perform this action|None|

<h4 id="get-stores-responseschema">Response Schema</h4>

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
bearer
</aside>

### Create Store

<a id="opIdCreate Store"></a>

> Code samples

```shell
# You can also use wget
curl -X POST /v1/stores \
  -H 'Content-Type: application/json; charset=utf-8' \
  -H 'Accept: application/json; charset=utf-8' \
  -H 'tenant: string' \
  -H 'Authorization: API_KEY'

```

```javascript
var headers = {
  'Content-Type':'application/json; charset=utf-8',
  'Accept':'application/json; charset=utf-8',
  'tenant':'string',
  'Authorization':'API_KEY'

};

$.ajax({
  url: '/v1/stores',
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
  "name": "string",
  "status": true,
  "ordersPerSlot": 0,
  "slotsInterval": 0,
  "address": "string",
  "url": "string",
  "vatNumber": "string",
  "email": "string",
  "lat": "string",
  "long": "string",
  "sortOrder": 0,
  "tenant": {
    "uuid": "string",
    "name": "string"
  }
}';
const headers = {
  'Content-Type':'application/json; charset=utf-8',
  'Accept':'application/json; charset=utf-8',
  'tenant':'string',
  'Authorization':'API_KEY'

};

fetch('/v1/stores',
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
  'tenant': 'string',
  'Authorization': 'API_KEY'
}

r = requests.post('/v1/stores', params={

}, headers = headers)

print r.json()

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Content-Type' => 'application/json; charset=utf-8',
  'Accept' => 'application/json; charset=utf-8',
  'tenant' => 'string',
  'Authorization' => 'API_KEY'
}

result = RestClient.post '/v1/stores',
  params: {
  }, headers: headers

p JSON.parse(result)

```

`POST /v1/stores`

*Deep integrations only! Create store for provided tenantUUID*

> Body parameter

```json
{
  "uuid": "string",
  "name": "string",
  "status": true,
  "ordersPerSlot": 0,
  "slotsInterval": 0,
  "address": "string",
  "url": "string",
  "vatNumber": "string",
  "email": "string",
  "lat": "string",
  "long": "string",
  "sortOrder": 0,
  "tenant": {
    "uuid": "string",
    "name": "string"
  }
}
```

<h4 id="create-store-parameters">Parameters</h4>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|tenant|header|string|true|External tenant UUID|
|body|body|[UpdateOrCreateStoreRequest](#schemaupdateorcreatestorerequest)|true|none|

> Example responses

> 201 Response

```json
{
  "payload": {
    "uuid": "876b34ad-45654-4ds7-cdd8-bfc47686d999",
    "name": "St. Paul's",
    "status": true,
    "ordersPerSlot": 10,
    "slotsInterval": 5,
    "address": "22 Carter Lane, London EC4V 5AD",
    "url": "vitamojo.com",
    "vatNumber": "GB 123456789",
    "email": "carterlane@vitamojo.com",
    "lat": "51.52",
    "long": "-0.08",
    "sortOrder": 1,
    "tenant": {
      "name": "vitamojo",
      "uuid": "566b34ad-45654-4ds7-cdd8-bfc47686d999"
    }
  }
}
```

<h4 id="create-store-responses">Responses</h4>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|201|[Created](https://tools.ietf.org/html/rfc7231#section-6.3.2)|none|[UpdateOrCreateStoreResponse](#schemaupdateorcreatestoreresponse)|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Body did not past validation|None|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Not authenticated to perform this action|None|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
bearer
</aside>

### Get Stores for Tenant

<a id="opIdGet Stores for Tenant"></a>

> Code samples

```shell
# You can also use wget
curl -X GET /v1/stores/tenant \
  -H 'tenant: string' \
  -H 'Authorization: API_KEY'

```

```javascript
var headers = {
  'tenant':'string',
  'Authorization':'API_KEY'

};

$.ajax({
  url: '/v1/stores/tenant',
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
  'tenant':'string',
  'Authorization':'API_KEY'

};

fetch('/v1/stores/tenant',
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
  'tenant': 'string',
  'Authorization': 'API_KEY'
}

r = requests.get('/v1/stores/tenant', params={

}, headers = headers)

print r.json()

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'tenant' => 'string',
  'Authorization' => 'API_KEY'
}

result = RestClient.get '/v1/stores/tenant',
  params: {
  }, headers: headers

p JSON.parse(result)

```

`GET /v1/stores/tenant`

*Deep integrations only! Get all stores by tenantUUID*

<h4 id="get-stores-for-tenant-parameters">Parameters</h4>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|tenant|header|string|true|Tenant UUID|

<h4 id="get-stores-for-tenant-responses">Responses</h4>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|none|None|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Not authenticated to perform this action|None|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
bearer
</aside>

### Get Store

<a id="opIdGet Store"></a>

> Code samples

```shell
# You can also use wget
curl -X GET /v1/stores/{storeUUID} \
  -H 'Accept: application/json; charset=utf-8' \
  -H 'Authorization: API_KEY'

```

```javascript
var headers = {
  'Accept':'application/json; charset=utf-8',
  'Authorization':'API_KEY'

};

$.ajax({
  url: '/v1/stores/{storeUUID}',
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

fetch('/v1/stores/{storeUUID}',
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

r = requests.get('/v1/stores/{storeUUID}', params={

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

result = RestClient.get '/v1/stores/{storeUUID}',
  params: {
  }, headers: headers

p JSON.parse(result)

```

`GET /v1/stores/{storeUUID}`

*Deep integrations only! Get store by UUID*

<h4 id="get-store-parameters">Parameters</h4>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|storeUUID|path|string|true|Store UUID|

> Example responses

> 200 Response

```json
{
  "payload": {
    "uuid": "876b34ad-45654-4ds7-cdd8-bfc47686d999",
    "name": "St. Paul's",
    "status": true,
    "ordersPerSlot": 10,
    "slotsInterval": 5,
    "address": "22 Carter Lane, London EC4V 5AD",
    "url": "vitamojo.com",
    "vatNumber": "GB 123456789",
    "email": "carterlane@vitamojo.com",
    "lat": "51.52",
    "long": "-0.08",
    "sortOrder": 1,
    "tenant": {
      "uuid": "876b34ad-45654-4ds7-cdd8-bfc47686d999",
      "name": "St. Paul's"
    },
    "settings": {
      "hasTableService": "0",
      "hasTables": "1",
      "isRequiredTableNr": "0",
      "hidePaidOrdersOnPickup": "0",
      "printReceiptWhenOrderIsPlaced": "0",
      "notifications": {
        "options": {
          "channel": "dev_876b34ad-45654-4ds7-cdd8-bfc47686d999",
          "encrypted": false
        }
      }
    }
  }
}
```

<h4 id="get-store-responses">Responses</h4>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|none|Inline|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Store not found|None|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Not authenticated to perform this action|None|

<h4 id="get-store-responseschema">Response Schema</h4>

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
bearer
</aside>

### Update Store

<a id="opIdUpdate Store"></a>

> Code samples

```shell
# You can also use wget
curl -X PUT /v1/stores/{storeUUID} \
  -H 'Content-Type: application/json; charset=utf-8' \
  -H 'Authorization: API_KEY'

```

```javascript
var headers = {
  'Content-Type':'application/json; charset=utf-8',
  'Authorization':'API_KEY'

};

$.ajax({
  url: '/v1/stores/{storeUUID}',
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
  "status": true,
  "ordersPerSlot": 0,
  "slotsInterval": 0,
  "address": "string",
  "url": "string",
  "vatNumber": "string",
  "email": "string",
  "lat": "string",
  "long": "string",
  "sortOrder": 0,
  "tenant": {
    "uuid": "string",
    "name": "string"
  }
}';
const headers = {
  'Content-Type':'application/json; charset=utf-8',
  'Authorization':'API_KEY'

};

fetch('/v1/stores/{storeUUID}',
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
  'Authorization': 'API_KEY'
}

r = requests.put('/v1/stores/{storeUUID}', params={

}, headers = headers)

print r.json()

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Content-Type' => 'application/json; charset=utf-8',
  'Authorization' => 'API_KEY'
}

result = RestClient.put '/v1/stores/{storeUUID}',
  params: {
  }, headers: headers

p JSON.parse(result)

```

`PUT /v1/stores/{storeUUID}`

*Deep integrations only! Update store by UUIDs*

> Body parameter

```json
{
  "uuid": "string",
  "name": "string",
  "status": true,
  "ordersPerSlot": 0,
  "slotsInterval": 0,
  "address": "string",
  "url": "string",
  "vatNumber": "string",
  "email": "string",
  "lat": "string",
  "long": "string",
  "sortOrder": 0,
  "tenant": {
    "uuid": "string",
    "name": "string"
  }
}
```

<h4 id="update-store-parameters">Parameters</h4>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|[UpdateOrCreateStoreRequest](#schemaupdateorcreatestorerequest)|true|none|
|storeUUID|path|string|true|Store UUID|

<h4 id="update-store-responses">Responses</h4>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|none|None|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Body did not past validation|None|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Not authenticated to perform this action|None|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
bearer
</aside>

### Validate Store

<a id="opIdValidate Store"></a>

> Code samples

```shell
# You can also use wget
curl -X GET /v1/stores/{storeUUID}/is-valid \
  -H 'Accept: application/json; charset=utf-8'

```

```javascript
var headers = {
  'Accept':'application/json; charset=utf-8'

};

$.ajax({
  url: '/v1/stores/{storeUUID}/is-valid',
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

fetch('/v1/stores/{storeUUID}/is-valid',
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

r = requests.get('/v1/stores/{storeUUID}/is-valid', params={

}, headers = headers)

print r.json()

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json; charset=utf-8'
}

result = RestClient.get '/v1/stores/{storeUUID}/is-valid',
  params: {
  }, headers: headers

p JSON.parse(result)

```

`GET /v1/stores/{storeUUID}/is-valid`

*Deep integrations only! Validate store by uuid*

<h4 id="validate-store-parameters">Parameters</h4>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|storeUUID|path|string|true|Store UUID|

> Example responses

> 200 Response

```json
{
  "payload": {
    "isValid": true
  }
}
```

<h4 id="validate-store-responses">Responses</h4>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|none|Inline|

<h4 id="validate-store-responseschema">Response Schema</h4>

<aside class="success">
This operation does not require authentication
</aside>

### Validate Tenant Store

<a id="opIdValidate Tenant Store"></a>

> Code samples

```shell
# You can also use wget
curl -X GET /v1/stores/{storeUUID}/tenants/{tenantUUID}/is-valid \
  -H 'Accept: application/json; charset=utf-8'

```

```javascript
var headers = {
  'Accept':'application/json; charset=utf-8'

};

$.ajax({
  url: '/v1/stores/{storeUUID}/tenants/{tenantUUID}/is-valid',
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

fetch('/v1/stores/{storeUUID}/tenants/{tenantUUID}/is-valid',
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

r = requests.get('/v1/stores/{storeUUID}/tenants/{tenantUUID}/is-valid', params={

}, headers = headers)

print r.json()

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json; charset=utf-8'
}

result = RestClient.get '/v1/stores/{storeUUID}/tenants/{tenantUUID}/is-valid',
  params: {
  }, headers: headers

p JSON.parse(result)

```

`GET /v1/stores/{storeUUID}/tenants/{tenantUUID}/is-valid`

*Deep integrations only! Validate store by uuid and tenant uuid*

<h4 id="validate-tenant-store-parameters">Parameters</h4>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|tenantUUID|path|string|true|Tenant UUID|
|storeUUID|path|string|true|Store UUID|

> Example responses

> 200 Response

```json
{
  "payload": {
    "isValid": true
  }
}
```

<h4 id="validate-tenant-store-responses">Responses</h4>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|none|Inline|

<h4 id="validate-tenant-store-responseschema">Response Schema</h4>

<aside class="success">
This operation does not require authentication
</aside>

<h2 id="tenant-service-store-settings">Store Settings</h2>

### Get Store Settings

<a id="opIdGet Store Settings"></a>

> Code samples

```shell
# You can also use wget
curl -X GET /v1/stores/{storeUUID}/settings \
  -H 'Accept: application/json; charset=utf-8' \
  -H 'Authorization: API_KEY'

```

```javascript
var headers = {
  'Accept':'application/json; charset=utf-8',
  'Authorization':'API_KEY'

};

$.ajax({
  url: '/v1/stores/{storeUUID}/settings',
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

fetch('/v1/stores/{storeUUID}/settings',
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

r = requests.get('/v1/stores/{storeUUID}/settings', params={

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

result = RestClient.get '/v1/stores/{storeUUID}/settings',
  params: {
  }, headers: headers

p JSON.parse(result)

```

`GET /v1/stores/{storeUUID}/settings`

*Deep integrations only! Get all store settings*

<h4 id="get-store-settings-parameters">Parameters</h4>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|storeUUID|path|string|true|Store UUID|

> Example responses

> 200 Response

```json
{
  "payload": [
    {
      "uuid": "55be51aa-3882-4c8a-afac-b1ea3c355b1f",
      "value": "0",
      "store": {
        "uuid": "876b34ad-45654-4ds7-cdd8-bfc47686d999",
        "name": "St. Paul's",
        "tenant": {
          "uuid": "832b34ad-2608-4cc7-bee8-bfc47686d801",
          "name": "Vitamojo"
        }
      },
      "setting": {
        "uuid": "f1ecfd64-9131-421a-98bb-ae75ed6ab474",
        "key": "hasTableService"
      }
    },
    {
      "uuid": "d988956d-555c-455a-9b2e-906a591e87b4",
      "value": "1",
      "store": {
        "uuid": "876b34ad-45654-4ds7-cdd8-bfc47686d999",
        "name": "St. Paul's",
        "tenant": {
          "uuid": "832b34ad-2608-4cc7-bee8-bfc47686d801",
          "name": "Vitamojo"
        }
      },
      "setting": {
        "uuid": "e0382770-e530-4ada-8479-2763f1ac301a",
        "key": "hasTables"
      }
    }
  ]
}
```

<h4 id="get-store-settings-responses">Responses</h4>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|none|[StoreSettings](#schemastoresettings)|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Not authenticated to perform this action|None|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
bearer ( Scopes: SUPER_ADMIN ), bearer
</aside>

### Create Store Setting

<a id="opIdCreate Store Setting"></a>

> Code samples

```shell
# You can also use wget
curl -X POST /v1/stores/{storeUUID}/settings \
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
  url: '/v1/stores/{storeUUID}/settings',
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
  "storeUUID": "string",
  "settingUUID": "string",
  "value": "string"
}';
const headers = {
  'Content-Type':'application/json; charset=utf-8',
  'Accept':'application/json; charset=utf-8',
  'Authorization':'API_KEY'

};

fetch('/v1/stores/{storeUUID}/settings',
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

r = requests.post('/v1/stores/{storeUUID}/settings', params={

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

result = RestClient.post '/v1/stores/{storeUUID}/settings',
  params: {
  }, headers: headers

p JSON.parse(result)

```

`POST /v1/stores/{storeUUID}/settings`

*Deep integrations only! Create a new store setting*

> Body parameter

```json
{
  "storeUUID": "string",
  "settingUUID": "string",
  "value": "string"
}
```

<h4 id="create-store-setting-parameters">Parameters</h4>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|[StoreSettingCreateReq](#schemastoresettingcreatereq)|true|none|
|storeUUID|path|string|true|Store UUID|

> Example responses

> 201 Response

```json
{
  "payload": {
    "uuid": "55be51aa-3882-4c8a-afac-b1ea3c355b1f",
    "value": "0",
    "store": {
      "uuid": "876b34ad-45654-4ds7-cdd8-bfc47686d999",
      "name": "St. Paul's",
      "tenant": {
        "uuid": "832b34ad-2608-4cc7-bee8-bfc47686d801",
        "name": "Vitamojo"
      }
    },
    "setting": {
      "uuid": "f1ecfd64-9131-421a-98bb-ae75ed6ab474",
      "key": "hasTableService"
    }
  }
}
```

<h4 id="create-store-setting-responses">Responses</h4>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|201|[Created](https://tools.ietf.org/html/rfc7231#section-6.3.2)|Store setting created successfully|[StoreSetting](#schemastoresetting)|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Body is not valid|None|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Not authenticated to perform this action|None|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
bearer ( Scopes: SUPER_ADMIN ), bearer
</aside>

### Get Store Setting

<a id="opIdGet Store Setting"></a>

> Code samples

```shell
# You can also use wget
curl -X GET /v1/stores/{storeUUID}/settings/{storeSettingUUID} \
  -H 'Accept: application/json; charset=utf-8' \
  -H 'Authorization: API_KEY'

```

```javascript
var headers = {
  'Accept':'application/json; charset=utf-8',
  'Authorization':'API_KEY'

};

$.ajax({
  url: '/v1/stores/{storeUUID}/settings/{storeSettingUUID}',
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

fetch('/v1/stores/{storeUUID}/settings/{storeSettingUUID}',
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

r = requests.get('/v1/stores/{storeUUID}/settings/{storeSettingUUID}', params={

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

result = RestClient.get '/v1/stores/{storeUUID}/settings/{storeSettingUUID}',
  params: {
  }, headers: headers

p JSON.parse(result)

```

`GET /v1/stores/{storeUUID}/settings/{storeSettingUUID}`

*Deep integrations only! Get one store setting by UUID*

<h4 id="get-store-setting-parameters">Parameters</h4>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|storeSettingUUID|path|string|true|Store setting UUID|
|storeUUID|path|string|true|Store UUID|

> Example responses

> 200 Response

```json
{
  "payload": {
    "uuid": "55be51aa-3882-4c8a-afac-b1ea3c355b1f",
    "value": "0",
    "store": {
      "uuid": "876b34ad-45654-4ds7-cdd8-bfc47686d999",
      "name": "St. Paul's",
      "tenant": {
        "uuid": "832b34ad-2608-4cc7-bee8-bfc47686d801",
        "name": "Vitamojo"
      }
    },
    "setting": {
      "uuid": "f1ecfd64-9131-421a-98bb-ae75ed6ab474",
      "key": "hasTableService"
    }
  }
}
```

<h4 id="get-store-setting-responses">Responses</h4>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|none|[StoreSetting](#schemastoresetting)|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Store setting not found|None|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Not authenticated to perform this action|None|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
bearer ( Scopes: SUPER_ADMIN ), bearer
</aside>

### Update Store Setting

<a id="opIdUpdate Store Setting"></a>

> Code samples

```shell
# You can also use wget
curl -X PUT /v1/stores/{storeUUID}/settings/{storeSettingUUID} \
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
  url: '/v1/stores/{storeUUID}/settings/{storeSettingUUID}',
  method: 'put',

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
  'Authorization':'API_KEY'

};

fetch('/v1/stores/{storeUUID}/settings/{storeSettingUUID}',
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

r = requests.put('/v1/stores/{storeUUID}/settings/{storeSettingUUID}', params={

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

result = RestClient.put '/v1/stores/{storeUUID}/settings/{storeSettingUUID}',
  params: {
  }, headers: headers

p JSON.parse(result)

```

`PUT /v1/stores/{storeUUID}/settings/{storeSettingUUID}`

*Deep integrations only! Update a store setting by UUID*

> Body parameter

```json
{}
```

<h4 id="update-store-setting-parameters">Parameters</h4>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|object|true|none|
|storeSettingUUID|path|string|true|Store setting UUID|
|storeUUID|path|string|true|Store UUID|

> Example responses

> 200 Response

```json
{
  "payload": {
    "uuid": "55be51aa-3882-4c8a-afac-b1ea3c355b1f",
    "value": "0",
    "store": {
      "uuid": "876b34ad-45654-4ds7-cdd8-bfc47686d999",
      "name": "St. Paul's",
      "tenant": {
        "uuid": "832b34ad-2608-4cc7-bee8-bfc47686d801",
        "name": "Vitamojo"
      }
    },
    "setting": {
      "uuid": "f1ecfd64-9131-421a-98bb-ae75ed6ab474",
      "key": "hasTableService"
    }
  }
}
```

<h4 id="update-store-setting-responses">Responses</h4>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|none|[StoreSetting](#schemastoresetting)|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Store setting not found or body is not valid|None|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Not authenticated to perform this action|None|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
bearer ( Scopes: SUPER_ADMIN ), bearer
</aside>

### Delete Store Setting

<a id="opIdDelete Store Setting"></a>

> Code samples

```shell
# You can also use wget
curl -X DELETE /v1/stores/{storeUUID}/settings/{storeSettingUUID} \
  -H 'Accept: application/json; charset=utf-8' \
  -H 'Authorization: API_KEY'

```

```javascript
var headers = {
  'Accept':'application/json; charset=utf-8',
  'Authorization':'API_KEY'

};

$.ajax({
  url: '/v1/stores/{storeUUID}/settings/{storeSettingUUID}',
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

fetch('/v1/stores/{storeUUID}/settings/{storeSettingUUID}',
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

r = requests.delete('/v1/stores/{storeUUID}/settings/{storeSettingUUID}', params={

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

result = RestClient.delete '/v1/stores/{storeUUID}/settings/{storeSettingUUID}',
  params: {
  }, headers: headers

p JSON.parse(result)

```

`DELETE /v1/stores/{storeUUID}/settings/{storeSettingUUID}`

*Deep integrations only! Delete a store setting by UUID*

<h4 id="delete-store-setting-parameters">Parameters</h4>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|storeSettingUUID|path|string|true|Store setting UUID|
|storeUUID|path|string|true|Store UUID|

> Example responses

> 200 Response

```json
{}
```

<h4 id="delete-store-setting-responses">Responses</h4>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|none|Inline|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Store setting not found|None|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Not authenticated to perform this action|None|

<h4 id="delete-store-setting-responseschema">Response Schema</h4>

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
bearer ( Scopes: SUPER_ADMIN ), bearer
</aside>

<h2 id="tenant-service-tenants">Tenants</h2>

### Get Tenants

<a id="opIdGet Tenants"></a>

> Code samples

```shell
# You can also use wget
curl -X GET /v1/tenants \
  -H 'Accept: application/json; charset=utf-8' \
  -H 'Authorization: API_KEY'

```

```javascript
var headers = {
  'Accept':'application/json; charset=utf-8',
  'Authorization':'API_KEY'

};

$.ajax({
  url: '/v1/tenants',
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

fetch('/v1/tenants',
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

r = requests.get('/v1/tenants', params={

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

result = RestClient.get '/v1/tenants',
  params: {
  }, headers: headers

p JSON.parse(result)

```

`GET /v1/tenants`

*Deep integrations only! Get all tenants*

> Example responses

> 200 Response

```json
{
  "payload": [
    {
      "uuid": "string",
      "name": "string",
      "alias": "string",
      "description": "string"
    }
  ]
}
```

<h4 id="get-tenants-responses">Responses</h4>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|none|[Tenants](#schematenants)|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Not authenticated to perform this action|None|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
bearer ( Scopes: SUPER_ADMIN ), bearer
</aside>

### Create Tenant

<a id="opIdCreate Tenant"></a>

> Code samples

```shell
# You can also use wget
curl -X POST /v1/tenants \
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
  url: '/v1/tenants',
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
  'Accept':'application/json; charset=utf-8',
  'Authorization':'API_KEY'

};

fetch('/v1/tenants',
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

r = requests.post('/v1/tenants', params={

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

result = RestClient.post '/v1/tenants',
  params: {
  }, headers: headers

p JSON.parse(result)

```

`POST /v1/tenants`

*Deep integrations only! Create a new tenant*

> Body parameter

```json
"string"
```

<h4 id="create-tenant-parameters">Parameters</h4>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|string|true|none|

> Example responses

> 201 Response

```json
{
  "payload": {
    "uuid": "832b34ad-2608-4cc7-bee8-bfc47686d801",
    "name": "Vitamojo",
    "alias": "vitamojo",
    "description": "Vitamojo"
  }
}
```

<h4 id="create-tenant-responses">Responses</h4>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|201|[Created](https://tools.ietf.org/html/rfc7231#section-6.3.2)|Tenant created successfully|[Tenant](#schematenant)|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Body is not valid|None|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Not authenticated to perform this action|None|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
bearer ( Scopes: SUPER_ADMIN ), bearer
</aside>

### Get Tenant

<a id="opIdGet Tenant"></a>

> Code samples

```shell
# You can also use wget
curl -X GET /v1/tenants/{tenantUUID} \
  -H 'Authorization: API_KEY'

```

```javascript
var headers = {
  'Authorization':'API_KEY'

};

$.ajax({
  url: '/v1/tenants/{tenantUUID}',
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
  'Authorization':'API_KEY'

};

fetch('/v1/tenants/{tenantUUID}',
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
  'Authorization': 'API_KEY'
}

r = requests.get('/v1/tenants/{tenantUUID}', params={

}, headers = headers)

print r.json()

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Authorization' => 'API_KEY'
}

result = RestClient.get '/v1/tenants/{tenantUUID}',
  params: {
  }, headers: headers

p JSON.parse(result)

```

`GET /v1/tenants/{tenantUUID}`

*Deep integrations only! Get tenant by UUID*

<h4 id="get-tenant-parameters">Parameters</h4>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|tenantUUID|path|string|true|Tenant UUID|

<h4 id="get-tenant-responses">Responses</h4>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|none|None|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Tenant not found|None|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
bearer ( Scopes: SUPER_ADMIN )
</aside>

### Update Tenant

<a id="opIdUpdate Tenant"></a>

> Code samples

```shell
# You can also use wget
curl -X PUT /v1/tenants/{tenantUUID} \
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
  url: '/v1/tenants/{tenantUUID}',
  method: 'put',

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
  'Accept':'application/json; charset=utf-8',
  'Authorization':'API_KEY'

};

fetch('/v1/tenants/{tenantUUID}',
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

r = requests.put('/v1/tenants/{tenantUUID}', params={

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

result = RestClient.put '/v1/tenants/{tenantUUID}',
  params: {
  }, headers: headers

p JSON.parse(result)

```

`PUT /v1/tenants/{tenantUUID}`

*Deep integrations only! Update a tenant by UUID*

> Body parameter

```json
"string"
```

<h4 id="update-tenant-parameters">Parameters</h4>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|string|true|none|
|tenantUUID|path|string|true|Tenant UUID|

> Example responses

> 200 Response

```json
{
  "payload": {
    "uuid": "832b34ad-2608-4cc7-bee8-bfc47686d801",
    "name": "Vitamojo",
    "alias": "vitamojo",
    "description": "Vitamojo"
  }
}
```

<h4 id="update-tenant-responses">Responses</h4>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|none|[Tenant](#schematenant)|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Tenant not found or body is not valid|None|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Not authenticated to perform this action|None|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
bearer ( Scopes: SUPER_ADMIN ), bearer
</aside>

### Validate Tenant

<a id="opIdValidate Tenant"></a>

> Code samples

```shell
# You can also use wget
curl -X GET /v1/tenants/{tenantUUID}/is-valid \
  -H 'Accept: application/json; charset=utf-8' \
  -H 'Authorization: API_KEY'

```

```javascript
var headers = {
  'Accept':'application/json; charset=utf-8',
  'Authorization':'API_KEY'

};

$.ajax({
  url: '/v1/tenants/{tenantUUID}/is-valid',
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

fetch('/v1/tenants/{tenantUUID}/is-valid',
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

r = requests.get('/v1/tenants/{tenantUUID}/is-valid', params={

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

result = RestClient.get '/v1/tenants/{tenantUUID}/is-valid',
  params: {
  }, headers: headers

p JSON.parse(result)

```

`GET /v1/tenants/{tenantUUID}/is-valid`

*Deep integrations only! Validate tenant by uuid*

<h4 id="validate-tenant-parameters">Parameters</h4>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|tenantUUID|path|string|true|Tenant UUID|

> Example responses

> 200 Response

```json
{
  "payload": {
    "isValid": true
  }
}
```

<h4 id="validate-tenant-responses">Responses</h4>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|none|Inline|

<h4 id="validate-tenant-responseschema">Response Schema</h4>

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
bearer ( Scopes: SUPER_ADMIN )
</aside>

<h2 id="tenant-service-tenant-settings">Tenant Settings</h2>

### Get Tenant Settings

<a id="opIdGet Tenant Settings"></a>

> Code samples

```shell
# You can also use wget
curl -X GET /v1/tenants/{tenantUUID}/settings \
  -H 'Accept: application/json; charset=utf-8' \
  -H 'Authorization: API_KEY'

```

```javascript
var headers = {
  'Accept':'application/json; charset=utf-8',
  'Authorization':'API_KEY'

};

$.ajax({
  url: '/v1/tenants/{tenantUUID}/settings',
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

fetch('/v1/tenants/{tenantUUID}/settings',
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

r = requests.get('/v1/tenants/{tenantUUID}/settings', params={

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

result = RestClient.get '/v1/tenants/{tenantUUID}/settings',
  params: {
  }, headers: headers

p JSON.parse(result)

```

`GET /v1/tenants/{tenantUUID}/settings`

*Deep integrations only! Get all tenant settings*

<h4 id="get-tenant-settings-parameters">Parameters</h4>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|tenantUUID|path|string|true|Tenant UUID|

> Example responses

> 200 Response

```json
{
  "payload": [
    {
      "uuid": "b955f535-9697-43db-9a3c-2c9b1b4a3a76",
      "value": "https://vmos2-staging-kiosk.vitamojo.com",
      "tenant": {
        "uuid": "832b34ad-2608-4cc7-bee8-bfc47686d801",
        "name": "Vitamojo"
      },
      "setting": {
        "uuid": "4e582ae2-080c-41f3-90ce-098aa74d5e97",
        "key": "app.webUrl"
      }
    },
    {
      "uuid": "5368d4b3-11a5-4c0c-8b5f-8cc2fb2c464c",
      "value": "https://vmos2.vmos-qa.com",
      "tenant": {
        "uuid": "832b34ad-2608-4cc7-bee8-bfc47686d801",
        "name": "Vitamojo"
      },
      "setting": {
        "uuid": "02c19fdc-2ee6-46b0-9bcf-e00b4516015f",
        "key": "app.managementUrl"
      }
    }
  ]
}
```

<h4 id="get-tenant-settings-responses">Responses</h4>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|none|[TenantSettings](#schematenantsettings)|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Not authenticated to perform this action|None|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
bearer ( Scopes: SUPER_ADMIN ), bearer
</aside>

### Create Tenant Setting

<a id="opIdCreate Tenant Setting"></a>

> Code samples

```shell
# You can also use wget
curl -X POST /v1/tenants/{tenantUUID}/settings \
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
  url: '/v1/tenants/{tenantUUID}/settings',
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
  'Authorization':'API_KEY'

};

fetch('/v1/tenants/{tenantUUID}/settings',
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

r = requests.post('/v1/tenants/{tenantUUID}/settings', params={

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

result = RestClient.post '/v1/tenants/{tenantUUID}/settings',
  params: {
  }, headers: headers

p JSON.parse(result)

```

`POST /v1/tenants/{tenantUUID}/settings`

*Deep integrations only! Create a new tenant setting*

> Body parameter

```json
{}
```

<h4 id="create-tenant-setting-parameters">Parameters</h4>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|object|true|none|
|tenantUUID|path|string|true|Tenant UUID|

> Example responses

> 201 Response

```json
{
  "payload": {
    "uuid": "b955f535-9697-43db-9a3c-2c9b1b4a3a76",
    "value": "https://vmos2-staging-kiosk.vitamojo.com",
    "tenant": {
      "uuid": "832b34ad-2608-4cc7-bee8-bfc47686d801",
      "name": "Vitamojo"
    },
    "setting": {
      "uuid": "4e582ae2-080c-41f3-90ce-098aa74d5e97",
      "key": "app.webUrl"
    }
  }
}
```

<h4 id="create-tenant-setting-responses">Responses</h4>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|201|[Created](https://tools.ietf.org/html/rfc7231#section-6.3.2)|Tenant setting created successfully|[TenantSetting](#schematenantsetting)|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Body is not valid|None|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Not authenticated to perform this action|None|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
bearer ( Scopes: SUPER_ADMIN ), bearer
</aside>

### Get Tenant Setting

<a id="opIdGet Tenant Setting"></a>

> Code samples

```shell
# You can also use wget
curl -X GET /v1/tenants/{tenantUUID}/settings/{tenantSettingUUID} \
  -H 'Accept: application/json; charset=utf-8' \
  -H 'Authorization: API_KEY'

```

```javascript
var headers = {
  'Accept':'application/json; charset=utf-8',
  'Authorization':'API_KEY'

};

$.ajax({
  url: '/v1/tenants/{tenantUUID}/settings/{tenantSettingUUID}',
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

fetch('/v1/tenants/{tenantUUID}/settings/{tenantSettingUUID}',
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

r = requests.get('/v1/tenants/{tenantUUID}/settings/{tenantSettingUUID}', params={

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

result = RestClient.get '/v1/tenants/{tenantUUID}/settings/{tenantSettingUUID}',
  params: {
  }, headers: headers

p JSON.parse(result)

```

`GET /v1/tenants/{tenantUUID}/settings/{tenantSettingUUID}`

*Deep integrations only! Get one tenant setting by UUID*

<h4 id="get-tenant-setting-parameters">Parameters</h4>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|tenantSettingUUID|path|string|true|Tenant setting UUID|
|tenantUUID|path|string|true|Tenant UUID|

> Example responses

> 200 Response

```json
{
  "payload": {
    "uuid": "b955f535-9697-43db-9a3c-2c9b1b4a3a76",
    "value": "https://vmos2-staging-kiosk.vitamojo.com",
    "tenant": {
      "uuid": "832b34ad-2608-4cc7-bee8-bfc47686d801",
      "name": "Vitamojo"
    },
    "setting": {
      "uuid": "4e582ae2-080c-41f3-90ce-098aa74d5e97",
      "key": "app.webUrl"
    }
  }
}
```

<h4 id="get-tenant-setting-responses">Responses</h4>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|none|[TenantSetting](#schematenantsetting)|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Tenant setting not found|None|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Not authenticated to perform this action|None|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
bearer ( Scopes: SUPER_ADMIN ), bearer
</aside>

### Update Tenant Setting

<a id="opIdUpdate Tenant Setting"></a>

> Code samples

```shell
# You can also use wget
curl -X PUT /v1/tenants/{tenantUUID}/settings/{tenantSettingUUID} \
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
  url: '/v1/tenants/{tenantUUID}/settings/{tenantSettingUUID}',
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
  "value": "string"
}';
const headers = {
  'Content-Type':'application/json; charset=utf-8',
  'Accept':'application/json; charset=utf-8',
  'Authorization':'API_KEY'

};

fetch('/v1/tenants/{tenantUUID}/settings/{tenantSettingUUID}',
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

r = requests.put('/v1/tenants/{tenantUUID}/settings/{tenantSettingUUID}', params={

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

result = RestClient.put '/v1/tenants/{tenantUUID}/settings/{tenantSettingUUID}',
  params: {
  }, headers: headers

p JSON.parse(result)

```

`PUT /v1/tenants/{tenantUUID}/settings/{tenantSettingUUID}`

*Deep integrations only! Update a tenant setting by UUID*

> Body parameter

```json
{
  "value": "string"
}
```

<h4 id="update-tenant-setting-parameters">Parameters</h4>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|[TenantSettingUpdateReq](#schematenantsettingupdatereq)|true|none|
|tenantSettingUUID|path|string|true|Tenant setting UUID|
|tenantUUID|path|string|true|Tenant UUID|

> Example responses

> 200 Response

```json
{
  "payload": {
    "uuid": "b955f535-9697-43db-9a3c-2c9b1b4a3a76",
    "value": "https://vmos2-staging-kiosk.vitamojo.com",
    "tenant": {
      "uuid": "832b34ad-2608-4cc7-bee8-bfc47686d801",
      "name": "Vitamojo"
    },
    "setting": {
      "uuid": "4e582ae2-080c-41f3-90ce-098aa74d5e97",
      "key": "app.webUrl"
    }
  }
}
```

<h4 id="update-tenant-setting-responses">Responses</h4>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|none|[TenantSetting](#schematenantsetting)|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Tenant setting not found or body is not valid|None|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Not authenticated to perform this action|None|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
bearer ( Scopes: SUPER_ADMIN ), bearer
</aside>

### Delete Tenant Setting

<a id="opIdDelete Tenant Setting"></a>

> Code samples

```shell
# You can also use wget
curl -X DELETE /v1/tenants/{tenantUUID}/settings/{tenantSettingUUID} \
  -H 'Accept: application/json; charset=utf-8' \
  -H 'Authorization: API_KEY'

```

```javascript
var headers = {
  'Accept':'application/json; charset=utf-8',
  'Authorization':'API_KEY'

};

$.ajax({
  url: '/v1/tenants/{tenantUUID}/settings/{tenantSettingUUID}',
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

fetch('/v1/tenants/{tenantUUID}/settings/{tenantSettingUUID}',
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

r = requests.delete('/v1/tenants/{tenantUUID}/settings/{tenantSettingUUID}', params={

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

result = RestClient.delete '/v1/tenants/{tenantUUID}/settings/{tenantSettingUUID}',
  params: {
  }, headers: headers

p JSON.parse(result)

```

`DELETE /v1/tenants/{tenantUUID}/settings/{tenantSettingUUID}`

*Deep integrations only! Delete a tenant setting by UUID*

<h4 id="delete-tenant-setting-parameters">Parameters</h4>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|tenantSettingUUID|path|string|true|Tenant setting UUID|
|tenantUUID|path|string|true|Tenant UUID|

> Example responses

> 200 Response

```json
{}
```

<h4 id="delete-tenant-setting-responses">Responses</h4>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|none|Inline|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Tenant setting not found|None|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Not authenticated to perform this action|None|

<h4 id="delete-tenant-setting-responseschema">Response Schema</h4>

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
bearer ( Scopes: SUPER_ADMIN ), bearer
</aside>

<h2 id="tenant-service-timeslots">Timeslots</h2>

### Get timeslots

<a id="opIdGet timeslots"></a>

> Code samples

```shell
# You can also use wget
curl -X GET /v1/timeslots \
  -H 'Accept: application/json; charset=utf-8' \
  -H 'store: string' \
  -H 'Authorization: API_KEY'

```

```javascript
var headers = {
  'Accept':'application/json; charset=utf-8',
  'store':'string',
  'Authorization':'API_KEY'

};

$.ajax({
  url: '/v1/timeslots',
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
  'store':'string',
  'Authorization':'API_KEY'

};

fetch('/v1/timeslots',
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
  'store': 'string',
  'Authorization': 'API_KEY'
}

r = requests.get('/v1/timeslots', params={

}, headers = headers)

print r.json()

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json; charset=utf-8',
  'store' => 'string',
  'Authorization' => 'API_KEY'
}

result = RestClient.get '/v1/timeslots',
  params: {
  }, headers: headers

p JSON.parse(result)

```

`GET /v1/timeslots`

*Deep integrations only! Get store timeslots*

<h4 id="get-timeslots-parameters">Parameters</h4>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|store|header|string|true|Store UUID|

> Example responses

> 200 Response

```json
{
  "payload": [
    {
      "uuid": "360fdc2e-44f4-41ff-b82e-d668bd807082",
      "slot": "09:30",
      "available": true,
      "weekday": 1,
      "isExpired": true
    },
    {
      "uuid": "d93a3f4b-71c0-4a03-a7a9-ef3942ca2812",
      "slot": "09:35",
      "available": true,
      "weekday": 1,
      "isExpired": true
    },
    {
      "uuid": "5536a5b0-0869-404c-89c8-d6266f329161",
      "slot": "09:40",
      "available": true,
      "weekday": 1,
      "isExpired": true
    },
    {
      "uuid": "d8995b6f-d4b7-410d-9339-74001bb3e9ed",
      "slot": "09:45",
      "available": true,
      "weekday": 1,
      "isExpired": true
    },
    {
      "uuid": "2ce83247-2a10-43bf-8761-58b8bae755cf",
      "slot": "09:50",
      "available": true,
      "weekday": 1,
      "isExpired": false
    },
    {
      "uuid": "81d59384-c37e-4018-bbd0-1fe483e0c670",
      "slot": "09:55",
      "available": true,
      "weekday": 1,
      "isExpired": false
    },
    {
      "uuid": "219677e6-29fb-44bc-8312-4fc2bc133770",
      "slot": "10:00",
      "available": true,
      "weekday": 1,
      "isExpired": false
    },
    {
      "uuid": "18c9730b-0211-462d-9f5c-f13d9f173012",
      "slot": "10:05",
      "available": true,
      "weekday": 1,
      "isExpired": false
    },
    {
      "uuid": "665ce57e-0dae-4861-83bb-1e0d2eb0820e",
      "slot": "10:10",
      "available": true,
      "weekday": 1,
      "isExpired": false
    },
    {
      "uuid": "b7571d18-3c09-45b8-a3bf-3e4d6a004e56",
      "slot": "10:15",
      "available": true,
      "weekday": 1,
      "isExpired": false
    },
    {
      "uuid": "8e4c774c-e0c7-4484-829e-3c0a05e34c57",
      "slot": "10:20",
      "available": true,
      "weekday": 1,
      "isExpired": false
    },
    {
      "uuid": "bd5535e7-2516-4630-b4ca-46a00db6ac1f",
      "slot": "10:25",
      "available": true,
      "weekday": 1,
      "isExpired": false
    },
    {
      "uuid": "d01954fa-d59b-40df-976a-46dbdc92e393",
      "slot": "10:30",
      "available": true,
      "weekday": 1,
      "isExpired": false
    }
  ]
}
```

> 400 Response

```json
{
  "statusCode": 400,
  "timestamp": "2019-05-07T12:15:24.435Z",
  "path": "/tenant/v1/timeslots",
  "message": "Store not found by UUID",
  "stack": null
}
```

<h4 id="get-timeslots-responses">Responses</h4>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|none|[Timeslots](#schematimeslots)|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Store not found|Inline|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Not authenticated to perform this action|None|

<h4 id="get-timeslots-responseschema">Response Schema</h4>

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
bearer ( Scopes: SUPER_ADMIN ), bearer
</aside>

<h2 id="tenant-service-hosts">Hosts</h2>

### Get Hosts

<a id="opIdGet Hosts"></a>

> Code samples

```shell
# You can also use wget
curl -X GET /v1/tenantHosts \
  -H 'Accept: application/json; charset=utf-8' \
  -H 'Authorization: API_KEY'

```

```javascript
var headers = {
  'Accept':'application/json; charset=utf-8',
  'Authorization':'API_KEY'

};

$.ajax({
  url: '/v1/tenantHosts',
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

fetch('/v1/tenantHosts',
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

r = requests.get('/v1/tenantHosts', params={

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

result = RestClient.get '/v1/tenantHosts',
  params: {
  }, headers: headers

p JSON.parse(result)

```

`GET /v1/tenantHosts`

*Deep integrations only! Get all hosts*

> Example responses

> 200 Response

```json
{
  "payload": [
    {
      "uuid": "4961b883-333b-432e-9163-5309421c227c",
      "value": "vmos2.vmos-qa.com",
      "tenant": {
        "uuid": "832b34ad-2608-4cc7-bee8-bfc47686d801",
        "name": "Vitamojo"
      }
    },
    {
      "uuid": "0f66c370-8249-4046-a90e-5024cd1c9a90",
      "value": "vitamojo.com",
      "tenant": {
        "uuid": "832b34ad-2608-4cc7-bee8-bfc47686d801",
        "name": "Vitamojo"
      }
    },
    {
      "uuid": "801f67b0-c03a-4b2a-aaa5-dab9b75aefc5",
      "value": "vmos.kfc.commmm",
      "tenant": {
        "uuid": "9b60b9ab-c2f1-4c58-ac82-5f4fad9354d1",
        "name": "KFC"
      }
    }
  ]
}
```

<h4 id="get-hosts-responses">Responses</h4>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|none|[Hosts](#schemahosts)|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Not authenticated to perform this action|None|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
bearer ( Scopes: SUPER_ADMIN ), bearer
</aside>

### Delete Hosts

<a id="opIdDelete Hosts"></a>

> Code samples

```shell
# You can also use wget
curl -X DELETE /v1/tenantHosts?hostsUUIDs=string \
  -H 'Authorization: API_KEY'

```

```javascript
var headers = {
  'Authorization':'API_KEY'

};

$.ajax({
  url: '/v1/tenantHosts',
  method: 'delete',
  data: '?hostsUUIDs=string',
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

fetch('/v1/tenantHosts?hostsUUIDs=string',
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
  'Authorization': 'API_KEY'
}

r = requests.delete('/v1/tenantHosts', params={
  'hostsUUIDs': [
  "string"
]
}, headers = headers)

print r.json()

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Authorization' => 'API_KEY'
}

result = RestClient.delete '/v1/tenantHosts',
  params: {
  'hostsUUIDs' => 'array[string]'
}, headers: headers

p JSON.parse(result)

```

`DELETE /v1/tenantHosts`

*Deep integrations only! Delete many hosts*

<h4 id="delete-hosts-parameters">Parameters</h4>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|hostsUUIDs|query|array[string]|true|none|

<h4 id="delete-hosts-responses">Responses</h4>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Not authenticated to perform this action|None|
|body|Unknown|none|None|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
bearer ( Scopes: SUPER_ADMIN ), bearer
</aside>

### Add Host

<a id="opIdAdd Host"></a>

> Code samples

```shell
# You can also use wget
curl -X POST /v1/tenantHosts \
  -H 'Content-Type: application/json; charset=utf-8' \
  -H 'Accept: application/json; charset=utf-8' \
  -H 'tenant: string' \
  -H 'Authorization: API_KEY'

```

```javascript
var headers = {
  'Content-Type':'application/json; charset=utf-8',
  'Accept':'application/json; charset=utf-8',
  'tenant':'string',
  'Authorization':'API_KEY'

};

$.ajax({
  url: '/v1/tenantHosts',
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
  "value": "string"
}';
const headers = {
  'Content-Type':'application/json; charset=utf-8',
  'Accept':'application/json; charset=utf-8',
  'tenant':'string',
  'Authorization':'API_KEY'

};

fetch('/v1/tenantHosts',
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
  'tenant': 'string',
  'Authorization': 'API_KEY'
}

r = requests.post('/v1/tenantHosts', params={

}, headers = headers)

print r.json()

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Content-Type' => 'application/json; charset=utf-8',
  'Accept' => 'application/json; charset=utf-8',
  'tenant' => 'string',
  'Authorization' => 'API_KEY'
}

result = RestClient.post '/v1/tenantHosts',
  params: {
  }, headers: headers

p JSON.parse(result)

```

`POST /v1/tenantHosts`

*Deep integrations only! Add host for provided tenantUUID*

> Body parameter

```json
{
  "value": "string"
}
```

<h4 id="add-host-parameters">Parameters</h4>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|tenant|header|string|true|External tenant UUID|
|body|body|[HostDto](#schemahostdto)|true|none|

> Example responses

> 201 Response

```json
{
  "payload": {
    "uuid": "0f66c370-8249-4046-a90e-5024cd1c9a90",
    "value": "vitamojo.com"
  }
}
```

<h4 id="add-host-responses">Responses</h4>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|201|[Created](https://tools.ietf.org/html/rfc7231#section-6.3.2)|none|[Host](#schemahost)|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Body did not past validation|None|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Not authenticated to perform this action|None|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
bearer ( Scopes: SUPER_ADMIN ), bearer
</aside>

### Get Host

<a id="opIdGet Host"></a>

> Code samples

```shell
# You can also use wget
curl -X GET /v1/tenantHosts/{hostUUID} \
  -H 'Accept: application/json; charset=utf-8' \
  -H 'Authorization: API_KEY'

```

```javascript
var headers = {
  'Accept':'application/json; charset=utf-8',
  'Authorization':'API_KEY'

};

$.ajax({
  url: '/v1/tenantHosts/{hostUUID}',
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

fetch('/v1/tenantHosts/{hostUUID}',
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

r = requests.get('/v1/tenantHosts/{hostUUID}', params={

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

result = RestClient.get '/v1/tenantHosts/{hostUUID}',
  params: {
  }, headers: headers

p JSON.parse(result)

```

`GET /v1/tenantHosts/{hostUUID}`

*Deep integrations only! Get Host by UUID*

<h4 id="get-host-parameters">Parameters</h4>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|hostUUID|path|string|true|Host UUID|

> Example responses

> 200 Response

```json
{
  "payload": {
    "uuid": "0f66c370-8249-4046-a90e-5024cd1c9a90",
    "value": "vitamojo.com"
  }
}
```

<h4 id="get-host-responses">Responses</h4>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|none|[Host](#schemahost)|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Not authenticated to perform this action|None|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
bearer ( Scopes: SUPER_ADMIN ), bearer
</aside>

### Update Host

<a id="opIdUpdate Host"></a>

> Code samples

```shell
# You can also use wget
curl -X PUT /v1/tenantHosts/{hostUUID} \
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
  url: '/v1/tenantHosts/{hostUUID}',
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
  "value": "string"
}';
const headers = {
  'Content-Type':'application/json; charset=utf-8',
  'Accept':'application/json; charset=utf-8',
  'Authorization':'API_KEY'

};

fetch('/v1/tenantHosts/{hostUUID}',
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

r = requests.put('/v1/tenantHosts/{hostUUID}', params={

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

result = RestClient.put '/v1/tenantHosts/{hostUUID}',
  params: {
  }, headers: headers

p JSON.parse(result)

```

`PUT /v1/tenantHosts/{hostUUID}`

*Deep integrations only! Update host value*

> Body parameter

```json
{
  "value": "string"
}
```

<h4 id="update-host-parameters">Parameters</h4>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|[HostDto](#schemahostdto)|true|none|
|hostUUID|path|string|true|Host UUID|

> Example responses

> 200 Response

```json
{
  "payload": {
    "uuid": "0f66c370-8249-4046-a90e-5024cd1c9a90",
    "value": "vitamojo.com"
  }
}
```

<h4 id="update-host-responses">Responses</h4>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|none|[Host](#schemahost)|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Body did not past validation|None|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Not authenticated to perform this action|None|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
bearer ( Scopes: SUPER_ADMIN ), bearer
</aside>

### Delete Host

<a id="opIdDelete Host"></a>

> Code samples

```shell
# You can also use wget
curl -X DELETE /v1/tenantHosts/{hostUUID} \
  -H 'Accept: application/json; charset=utf-8' \
  -H 'Authorization: API_KEY'

```

```javascript
var headers = {
  'Accept':'application/json; charset=utf-8',
  'Authorization':'API_KEY'

};

$.ajax({
  url: '/v1/tenantHosts/{hostUUID}',
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

fetch('/v1/tenantHosts/{hostUUID}',
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

r = requests.delete('/v1/tenantHosts/{hostUUID}', params={

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

result = RestClient.delete '/v1/tenantHosts/{hostUUID}',
  params: {
  }, headers: headers

p JSON.parse(result)

```

`DELETE /v1/tenantHosts/{hostUUID}`

*Deep integrations only! Delete Host by UUID*

<h4 id="delete-host-parameters">Parameters</h4>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|hostUUID|path|string|true|Host UUID|

> Example responses

> 200 Response

```json
{
  "payload": {
    "uuid": "0f66c370-8249-4046-a90e-5024cd1c9a90",
    "value": "vitamojo.com"
  }
}
```

<h4 id="delete-host-responses">Responses</h4>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|none|[Host](#schemahost)|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Not authenticated to perform this action|None|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
bearer ( Scopes: SUPER_ADMIN ), bearer
</aside>

<h2 id="tenant-service-themes">Themes</h2>

### Get Themes

<a id="opIdGet Themes"></a>

> Code samples

```shell
# You can also use wget
curl -X GET /v1/themes \
  -H 'Accept: application/json; charset=utf-8' \
  -H 'Authorization: API_KEY'

```

```javascript
var headers = {
  'Accept':'application/json; charset=utf-8',
  'Authorization':'API_KEY'

};

$.ajax({
  url: '/v1/themes',
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

fetch('/v1/themes',
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

r = requests.get('/v1/themes', params={

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

result = RestClient.get '/v1/themes',
  params: {
  }, headers: headers

p JSON.parse(result)

```

`GET /v1/themes`

*Deep integrations only! Get all themes*

> Example responses

> 200 Response

```json
{
  "payload": [
    {
      "name": "test name 1",
      "payload": "{}",
      "uuid": "2dfe627c-7095-41c3-8fe1-a1763b76a34e",
      "tenants": [
        "361b56c6-4549-4233-aec0-f18903b9836f"
      ],
      "stores": [
        "e3bc0ec1-79ba-4ec1-a9ae-b2a189011c90"
      ]
    },
    {
      "name": "test name 2",
      "payload": "{}",
      "uuid": "f71f4a4e-b2d6-4dc9-b05a-7fff1bae95c3",
      "tenants": [
        "41f45187-f1be-4ead-9f5c-55856190af25"
      ],
      "stores": [
        "c9b2a94b-0c21-4154-8fbf-ecd8f4d804d1"
      ]
    }
  ]
}
```

<h4 id="get-themes-responses">Responses</h4>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|none|[Themes](#schemathemes)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
bearer ( Scopes: SUPER_ADMIN )
</aside>

### Create Theme

<a id="opIdCreate Theme"></a>

> Code samples

```shell
# You can also use wget
curl -X POST /v1/themes \
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
  url: '/v1/themes',
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
  "payload": "string",
  "stores": [
    "string"
  ],
  "tenants": [
    "string"
  ]
}';
const headers = {
  'Content-Type':'application/json; charset=utf-8',
  'Accept':'application/json; charset=utf-8',
  'Authorization':'API_KEY'

};

fetch('/v1/themes',
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

r = requests.post('/v1/themes', params={

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

result = RestClient.post '/v1/themes',
  params: {
  }, headers: headers

p JSON.parse(result)

```

`POST /v1/themes`

*Deep integrations only! Create a new theme*

> Body parameter

```json
{
  "name": "string",
  "payload": "string",
  "stores": [
    "string"
  ],
  "tenants": [
    "string"
  ]
}
```

<h4 id="create-theme-parameters">Parameters</h4>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|[ThemeReq](#schemathemereq)|true|none|

> Example responses

> 201 Response

```json
{
  "payload": {
    "name": "theme 1",
    "payload": "{}",
    "uuid": "6423c718-aa2c-429d-9abc-20bf7290aa5a",
    "tenants": [
      "203e1804-cbcc-4f73-8073-1bb13d3b4026"
    ],
    "stores": [
      "5d94d0b9-42cf-442f-89ee-e1722356a245"
    ]
  }
}
```

<h4 id="create-theme-responses">Responses</h4>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|201|[Created](https://tools.ietf.org/html/rfc7231#section-6.3.2)|Theme created successfully|[Theme](#schematheme)|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Body is not valid|None|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Not authenticated to perform this action|None|
|403|[Forbidden](https://tools.ietf.org/html/rfc7231#section-6.5.3)|Not authorized to perform this action|None|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
bearer ( Scopes: SUPER_ADMIN ), bearer
</aside>

### Get Theme

<a id="opIdGet Theme"></a>

> Code samples

```shell
# You can also use wget
curl -X GET /v1/themes/{uuid} \
  -H 'Accept: application/json; charset=utf-8' \
  -H 'Authorization: API_KEY'

```

```javascript
var headers = {
  'Accept':'application/json; charset=utf-8',
  'Authorization':'API_KEY'

};

$.ajax({
  url: '/v1/themes/{uuid}',
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

fetch('/v1/themes/{uuid}',
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

r = requests.get('/v1/themes/{uuid}', params={

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

result = RestClient.get '/v1/themes/{uuid}',
  params: {
  }, headers: headers

p JSON.parse(result)

```

`GET /v1/themes/{uuid}`

*Deep integrations only! Get theme by UUID*

<h4 id="get-theme-parameters">Parameters</h4>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|uuid|path|string|true|Theme uuid|

> Example responses

> 200 Response

```json
{
  "payload": {
    "name": "theme 1",
    "payload": "{}",
    "uuid": "6423c718-aa2c-429d-9abc-20bf7290aa5a",
    "tenants": [
      "203e1804-cbcc-4f73-8073-1bb13d3b4026"
    ],
    "stores": [
      "5d94d0b9-42cf-442f-89ee-e1722356a245"
    ]
  }
}
```

<h4 id="get-theme-responses">Responses</h4>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|none|[Theme](#schematheme)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
bearer ( Scopes: SUPER_ADMIN )
</aside>

### Update Theme

<a id="opIdUpdate Theme"></a>

> Code samples

```shell
# You can also use wget
curl -X PUT /v1/themes/{uuid} \
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
  url: '/v1/themes/{uuid}',
  method: 'put',

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
  'Authorization':'API_KEY'

};

fetch('/v1/themes/{uuid}',
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

r = requests.put('/v1/themes/{uuid}', params={

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

result = RestClient.put '/v1/themes/{uuid}',
  params: {
  }, headers: headers

p JSON.parse(result)

```

`PUT /v1/themes/{uuid}`

*Deep integrations only! Update a theme by UUID*

> Body parameter

```json
{}
```

<h4 id="update-theme-parameters">Parameters</h4>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|object|true|none|
|uuid|path|string|true|Theme uuid|

> Example responses

> 200 Response

```json
{
  "payload": {
    "name": "theme 1",
    "payload": "{}",
    "uuid": "6423c718-aa2c-429d-9abc-20bf7290aa5a",
    "tenants": [
      "203e1804-cbcc-4f73-8073-1bb13d3b4026"
    ],
    "stores": [
      "5d94d0b9-42cf-442f-89ee-e1722356a245"
    ]
  }
}
```

<h4 id="update-theme-responses">Responses</h4>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|none|[Theme](#schematheme)|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Body is not valid|None|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Not authenticated to perform this action|None|
|403|[Forbidden](https://tools.ietf.org/html/rfc7231#section-6.5.3)|Not authorized to perform this action|None|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
bearer ( Scopes: SUPER_ADMIN ), bearer
</aside>

### Delete Theme

<a id="opIdDelete Theme"></a>

> Code samples

```shell
# You can also use wget
curl -X DELETE /v1/themes/{uuid} \
  -H 'Authorization: API_KEY'

```

```javascript
var headers = {
  'Authorization':'API_KEY'

};

$.ajax({
  url: '/v1/themes/{uuid}',
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
  'Authorization':'API_KEY'

};

fetch('/v1/themes/{uuid}',
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
  'Authorization': 'API_KEY'
}

r = requests.delete('/v1/themes/{uuid}', params={

}, headers = headers)

print r.json()

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Authorization' => 'API_KEY'
}

result = RestClient.delete '/v1/themes/{uuid}',
  params: {
  }, headers: headers

p JSON.parse(result)

```

`DELETE /v1/themes/{uuid}`

*Deep integrations only! Delete a theme by UUID*

<h4 id="delete-theme-parameters">Parameters</h4>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|uuid|path|string|true|Theme uuid|

<h4 id="delete-theme-responses">Responses</h4>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Success|None|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Not authenticated to perform this action|None|
|403|[Forbidden](https://tools.ietf.org/html/rfc7231#section-6.5.3)|Not authorized to perform this action|None|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
bearer ( Scopes: SUPER_ADMIN ), bearer
</aside>

<h2 id="tenant-service-i18ns">I18ns</h2>

### Get Transaltions

<a id="opIdGet Transaltions"></a>

> Code samples

```shell
# You can also use wget
curl -X GET /v1/translations \
  -H 'Accept: application/json; charset=utf-8' \
  -H 'tenant: string' \
  -H 'x-requested-from: string'

```

```javascript
var headers = {
  'Accept':'application/json; charset=utf-8',
  'tenant':'string',
  'x-requested-from':'string'

};

$.ajax({
  url: '/v1/translations',
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
  'tenant':'string',
  'x-requested-from':'string'

};

fetch('/v1/translations',
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
  'tenant': 'string',
  'x-requested-from': 'string'
}

r = requests.get('/v1/translations', params={

}, headers = headers)

print r.json()

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json; charset=utf-8',
  'tenant' => 'string',
  'x-requested-from' => 'string'
}

result = RestClient.get '/v1/translations',
  params: {
  }, headers: headers

p JSON.parse(result)

```

`GET /v1/translations`

*Deep integrations only! Get all internationalisation data for tenant.*

<h4 id="get-transaltions-parameters">Parameters</h4>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|tenant|header|string|false|Tenant UUID|
|x-requested-from|header|string|false|Identifies the app making the request (kiosk, pos, preorder)|

> Example responses

> 200 Response

```json
{
  "payload": [
    {
      "uuid": "c4e07fcc-7e8c-42fe-9508-1ea64990b54c",
      "payload": "{}",
      "type": "kiosk",
      "tenant": {
        "name": "Vitamojo",
        "uuid": "832b34ad-2608-4cc7-bee8-bfc47686d801"
      }
    },
    {
      "uuid": "3b72c617-40cd-429d-9e9b-ec5e1798a6ad",
      "payload": "{}",
      "type": "collection-screen",
      "tenant": {
        "name": "Vitamojo",
        "uuid": "832b34ad-2608-4cc7-bee8-bfc47686d801"
      }
    }
  ]
}
```

<h4 id="get-transaltions-responses">Responses</h4>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|none|[I18ns](#schemai18ns)|

<aside class="success">
This operation does not require authentication
</aside>

### Create Translation

<a id="opIdCreate Translation"></a>

> Code samples

```shell
# You can also use wget
curl -X POST /v1/translations \
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
  url: '/v1/translations',
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
  "type": "string",
  "payload": "string",
  "tenant": "string"
}';
const headers = {
  'Content-Type':'application/json; charset=utf-8',
  'Accept':'application/json; charset=utf-8',
  'Authorization':'API_KEY'

};

fetch('/v1/translations',
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

r = requests.post('/v1/translations', params={

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

result = RestClient.post '/v1/translations',
  params: {
  }, headers: headers

p JSON.parse(result)

```

`POST /v1/translations`

*Deep integrations only! Create a new i18n*

> Body parameter

```json
{
  "type": "string",
  "payload": "string",
  "tenant": "string"
}
```

<h4 id="create-translation-parameters">Parameters</h4>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|[I18nsCreateReq](#schemai18nscreatereq)|true|none|

> Example responses

> 201 Response

```json
{
  "payload": {
    "uuid": "c4e07fcc-7e8c-42fe-9508-1ea64990b54c",
    "payload": "{}",
    "type": "kiosk",
    "tenant": {
      "name": "Vitamojo",
      "uuid": "832b34ad-2608-4cc7-bee8-bfc47686d801"
    }
  }
}
```

<h4 id="create-translation-responses">Responses</h4>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|201|[Created](https://tools.ietf.org/html/rfc7231#section-6.3.2)|I18n created successfully|[I18n](#schemai18n)|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Body is not valid|None|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Not authenticated to perform this action|None|
|403|[Forbidden](https://tools.ietf.org/html/rfc7231#section-6.5.3)|Not authorized to perform this action|None|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
bearer ( Scopes: SUPER_ADMIN ), bearer
</aside>

### Get Translation

<a id="opIdGet Translation"></a>

> Code samples

```shell
# You can also use wget
curl -X GET /v1/translations/{uuid} \
  -H 'Accept: application/json; charset=utf-8' \
  -H 'Authorization: API_KEY'

```

```javascript
var headers = {
  'Accept':'application/json; charset=utf-8',
  'Authorization':'API_KEY'

};

$.ajax({
  url: '/v1/translations/{uuid}',
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

fetch('/v1/translations/{uuid}',
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

r = requests.get('/v1/translations/{uuid}', params={

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

result = RestClient.get '/v1/translations/{uuid}',
  params: {
  }, headers: headers

p JSON.parse(result)

```

`GET /v1/translations/{uuid}`

*Deep integrations only! Get i18n by UUID*

<h4 id="get-translation-parameters">Parameters</h4>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|uuid|path|string|true|I18n uuid|

> Example responses

> 200 Response

```json
{
  "payload": {
    "uuid": "c4e07fcc-7e8c-42fe-9508-1ea64990b54c",
    "payload": "{}",
    "type": "kiosk",
    "tenant": {
      "name": "Vitamojo",
      "uuid": "832b34ad-2608-4cc7-bee8-bfc47686d801"
    }
  }
}
```

<h4 id="get-translation-responses">Responses</h4>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|none|[I18n](#schemai18n)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
bearer ( Scopes: SUPER_ADMIN )
</aside>

### Update Translation

<a id="opIdUpdate Translation"></a>

> Code samples

```shell
# You can also use wget
curl -X PUT /v1/translations/{uuid} \
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
  url: '/v1/translations/{uuid}',
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
  "type": "string",
  "payload": "string",
  "tenant": "string"
}';
const headers = {
  'Content-Type':'application/json; charset=utf-8',
  'Accept':'application/json; charset=utf-8',
  'Authorization':'API_KEY'

};

fetch('/v1/translations/{uuid}',
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

r = requests.put('/v1/translations/{uuid}', params={

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

result = RestClient.put '/v1/translations/{uuid}',
  params: {
  }, headers: headers

p JSON.parse(result)

```

`PUT /v1/translations/{uuid}`

*Deep integrations only! Update a i18n by UUID*

> Body parameter

```json
{
  "type": "string",
  "payload": "string",
  "tenant": "string"
}
```

<h4 id="update-translation-parameters">Parameters</h4>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|[I18nsCreateReq](#schemai18nscreatereq)|true|none|
|uuid|path|string|true|I18n uuid|

> Example responses

> 200 Response

```json
{
  "payload": {
    "uuid": "c4e07fcc-7e8c-42fe-9508-1ea64990b54c",
    "payload": "{}",
    "type": "kiosk",
    "tenant": {
      "name": "Vitamojo",
      "uuid": "832b34ad-2608-4cc7-bee8-bfc47686d801"
    }
  }
}
```

<h4 id="update-translation-responses">Responses</h4>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|none|[I18n](#schemai18n)|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Body is not valid|None|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Not authenticated to perform this action|None|
|403|[Forbidden](https://tools.ietf.org/html/rfc7231#section-6.5.3)|Not authorized to perform this action|None|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
bearer ( Scopes: SUPER_ADMIN ), bearer
</aside>

### Delete Translation

<a id="opIdDelete Translation"></a>

> Code samples

```shell
# You can also use wget
curl -X DELETE /v1/translations/{uuid} \
  -H 'Authorization: API_KEY'

```

```javascript
var headers = {
  'Authorization':'API_KEY'

};

$.ajax({
  url: '/v1/translations/{uuid}',
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
  'Authorization':'API_KEY'

};

fetch('/v1/translations/{uuid}',
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
  'Authorization': 'API_KEY'
}

r = requests.delete('/v1/translations/{uuid}', params={

}, headers = headers)

print r.json()

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Authorization' => 'API_KEY'
}

result = RestClient.delete '/v1/translations/{uuid}',
  params: {
  }, headers: headers

p JSON.parse(result)

```

`DELETE /v1/translations/{uuid}`

*Delete a i18n by UUID*

<h4 id="delete-translation-parameters">Parameters</h4>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|uuid|path|string|true|I18n uuid|

<h4 id="delete-translation-responses">Responses</h4>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Success|None|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Not authenticated to perform this action|None|
|403|[Forbidden](https://tools.ietf.org/html/rfc7231#section-6.5.3)|Not authorized to perform this action|None|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
bearer ( Scopes: SUPER_ADMIN ), bearer
</aside>

## Schemas

<h3 id="tocSbootstrap">Bootstrap</h3>

<a id="schemabootstrap"></a>

```json
{
  "payload": {
    "tenant": {
      "uuid": "string",
      "name": "string",
      "alias": "string",
      "description": "string",
      "settings": {},
      "theme": {},
      "i18n": {}
    },
    "stores": [
      {
        "uuid": "string",
        "sortOrder": 0,
        "name": "string",
        "address": "string",
        "email": "string",
        "status": true,
        "ordersPerSlot": 0,
        "slotsInterval": 0,
        "url": "string",
        "vatNumber": "string",
        "lat": "string",
        "long": "string",
        "theme": {
          "uuid": "string",
          "payload": {}
        },
        "settings": {}
      }
    ],
    "features": {}
  }
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|payload|object|true|none|none|
|» tenant|object|true|none|none|
|»» uuid|string|true|none|none|
|»» name|string|true|none|none|
|»» alias|string|true|none|none|
|»» description|string|false|none|none|
|»» settings|object|true|none|none|
|»» theme|object|false|none|none|
|»» i18n|object|false|none|none|
|» stores|[object]|true|none|none|
|»» uuid|string|true|none|none|
|»» sortOrder|integer|true|none|none|
|»» name|string|true|none|none|
|»» address|string|true|none|none|
|»» email|string|true|none|none|
|»» status|boolean|true|none|none|
|»» ordersPerSlot|integer|true|none|none|
|»» slotsInterval|integer|true|none|none|
|»» url|string|true|none|none|
|»» vatNumber|string|true|none|none|
|»» lat|string|true|none|none|
|»» long|string|true|none|none|
|»» theme|object|true|none|none|
|»»» uuid|string|true|none|none|
|»»» payload|object|true|none|none|
|»» settings|object|true|none|none|
|» features|object|true|none|none|

<h3 id="tocSsetting">Setting</h3>

<a id="schemasetting"></a>

```json
{
  "payload": {
    "uuid": "string",
    "key": "string",
    "value": "string",
    "type": "kiosk",
    "description": "string"
  }
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|payload|object|true|none|none|
|» uuid|string|true|none|none|
|» key|string|true|none|none|
|» value|string|true|none|none|
|» type|string|true|none|none|
|» description|string|true|none|none|

#### Enumerated Values

|Property|Value|
|---|---|
|type|kiosk|
|type|pos|
|type|online|
|type|collection-screen|
|type|all|

<h3 id="tocSsettingreq">SettingReq</h3>

<a id="schemasettingreq"></a>

```json
{
  "key": "string",
  "value": "string",
  "type": "kiosk",
  "description": "string"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|key|string|true|none|none|
|value|string|true|none|none|
|type|string|true|none|none|
|description|string|false|none|none|

#### Enumerated Values

|Property|Value|
|---|---|
|type|kiosk|
|type|pos|
|type|online|
|type|collection-screen|
|type|all|

<h3 id="tocSsettings">Settings</h3>

<a id="schemasettings"></a>

```json
{
  "payload": [
    {
      "uuid": "string",
      "key": "string",
      "value": "string",
      "type": "kiosk",
      "description": "string"
    }
  ]
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|payload|[object]|true|none|none|
|» uuid|string|true|none|none|
|» key|string|true|none|none|
|» value|string|true|none|none|
|» type|string|true|none|none|
|» description|string|true|none|none|

#### Enumerated Values

|Property|Value|
|---|---|
|type|kiosk|
|type|pos|
|type|online|
|type|collection-screen|
|type|all|

<h3 id="tocStenant">Tenant</h3>

<a id="schematenant"></a>

```json
{
  "payload": {
    "uuid": "string",
    "name": "string",
    "alias": "string",
    "description": "string"
  }
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|payload|object|true|none|none|
|» uuid|string|true|none|none|
|» name|string|true|none|none|
|» alias|string|true|none|none|
|» description|string|false|none|none|

<h3 id="tocStenants">Tenants</h3>

<a id="schematenants"></a>

```json
{
  "payload": [
    {
      "uuid": "string",
      "name": "string",
      "alias": "string",
      "description": "string"
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
|» alias|string|true|none|none|
|» description|string|false|none|none|

<h3 id="tocStimeslots">Timeslots</h3>

<a id="schematimeslots"></a>

```json
{
  "payload": [
    {
      "uuid": "string",
      "slot": "string",
      "available": true,
      "weekday": 1,
      "isExpired": true
    }
  ]
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|payload|[object]|true|none|none|
|» uuid|string|true|none|none|
|» slot|string|true|none|none|
|» available|boolean|true|none|none|
|» weekday|integer|true|none|none|
|» isExpired|boolean|true|none|none|

<h3 id="tocShostdto">HostDto</h3>

<a id="schemahostdto"></a>

```json
{
  "value": "string"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|value|string|true|none|none|

<h3 id="tocShost">Host</h3>

<a id="schemahost"></a>

```json
{
  "payload": {
    "uuid": "string",
    "value": "string"
  }
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|payload|object|true|none|none|
|» uuid|string|true|none|none|
|» value|string|true|none|none|

<h3 id="tocShosts">Hosts</h3>

<a id="schemahosts"></a>

```json
{
  "payload": [
    {
      "value": "string",
      "uuid": "string",
      "tenant": {
        "name": "string",
        "uuid": "string"
      }
    }
  ]
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|payload|[object]|true|none|none|
|» value|string|true|none|none|
|» uuid|string|true|none|none|
|» tenant|object|false|none|none|
|»» name|string|true|none|none|
|»» uuid|string|true|none|none|

<h3 id="tocSstores">Stores</h3>

<a id="schemastores"></a>

```json
{
  "payload": [
    {
      "uuid": "string",
      "name": "string",
      "status": true,
      "ordersPerSlot": 0,
      "slotsInterval": 0,
      "address": "string",
      "url": "string",
      "vatNumber": "string",
      "email": "string",
      "lat": "string",
      "long": "string",
      "sortOrder": 0,
      "tenant": {
        "name": "string",
        "uuid": "string"
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
|» name|string|true|none|none|
|» status|boolean|true|none|none|
|» ordersPerSlot|integer|true|none|none|
|» slotsInterval|integer|true|none|none|
|» address|string|true|none|none|
|» url|string|true|none|none|
|» vatNumber|string|true|none|none|
|» email|string|true|none|none|
|» lat|string|true|none|none|
|» long|string|true|none|none|
|» sortOrder|integer|true|none|none|
|» tenant|object|false|none|none|
|»» name|string|true|none|none|
|»» uuid|string|true|none|none|

<h3 id="tocSupdateorcreatestoreresponse">UpdateOrCreateStoreResponse</h3>

<a id="schemaupdateorcreatestoreresponse"></a>

```json
{
  "payload": {
    "uuid": "string",
    "name": "string",
    "status": true,
    "ordersPerSlot": 0,
    "slotsInterval": 0,
    "address": "string",
    "url": "string",
    "vatNumber": "string",
    "email": "string",
    "lat": "string",
    "long": "string",
    "sortOrder": 0,
    "tenant": {
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
|» name|string|true|none|none|
|» status|boolean|true|none|none|
|» ordersPerSlot|integer|true|none|none|
|» slotsInterval|integer|true|none|none|
|» address|string|true|none|none|
|» url|string|true|none|none|
|» vatNumber|string|true|none|none|
|» email|string|true|none|none|
|» lat|string|true|none|none|
|» long|string|true|none|none|
|» sortOrder|integer|true|none|none|
|» tenant|object|false|none|none|
|»» uuid|string|true|none|none|
|»» name|string|true|none|none|

<h3 id="tocSupdateorcreatestorerequest">UpdateOrCreateStoreRequest</h3>

<a id="schemaupdateorcreatestorerequest"></a>

```json
{
  "uuid": "string",
  "name": "string",
  "status": true,
  "ordersPerSlot": 0,
  "slotsInterval": 0,
  "address": "string",
  "url": "string",
  "vatNumber": "string",
  "email": "string",
  "lat": "string",
  "long": "string",
  "sortOrder": 0,
  "tenant": {
    "uuid": "string",
    "name": "string"
  }
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|uuid|string|true|none|none|
|name|string|true|none|none|
|status|boolean|true|none|none|
|ordersPerSlot|integer|true|none|none|
|slotsInterval|integer|true|none|none|
|address|string|true|none|none|
|url|string|true|none|none|
|vatNumber|string|true|none|none|
|email|string|true|none|none|
|lat|string|true|none|none|
|long|string|true|none|none|
|sortOrder|integer|true|none|none|
|tenant|object|false|none|none|
|» uuid|string|true|none|none|
|» name|string|true|none|none|

<h3 id="tocStheme">Theme</h3>

<a id="schematheme"></a>

```json
{
  "payload": {
    "name": "string",
    "payload": "string",
    "uuid": "string",
    "tenants": [
      "string"
    ],
    "stores": [
      "string"
    ]
  }
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|payload|object|true|none|none|
|» name|string|true|none|none|
|» payload|string|true|none|none|
|» uuid|string|true|none|none|
|» tenants|[string]|true|none|none|
|» stores|[string]|true|none|none|

<h3 id="tocSthemes">Themes</h3>

<a id="schemathemes"></a>

```json
{
  "payload": [
    {
      "name": "string",
      "payload": "string",
      "uuid": "string",
      "tenants": [
        "string"
      ],
      "stores": [
        "string"
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
|» payload|string|true|none|none|
|» uuid|string|true|none|none|
|» tenants|[string]|true|none|none|
|» stores|[string]|true|none|none|

<h3 id="tocSthemereq">ThemeReq</h3>

<a id="schemathemereq"></a>

```json
{
  "name": "string",
  "payload": "string",
  "stores": [
    "string"
  ],
  "tenants": [
    "string"
  ]
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|name|string|false|none|none|
|payload|string|true|none|none|
|stores|[string]|false|none|none|
|tenants|[string]|false|none|none|

<h3 id="tocSi18n">I18n</h3>

<a id="schemai18n"></a>

```json
{
  "payload": {
    "uuid": "string",
    "payload": "string",
    "type": "string",
    "tenant": {
      "name": "string",
      "uuid": "string"
    }
  }
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|payload|object|true|none|none|
|» uuid|string|true|none|none|
|» payload|string|true|none|none|
|» type|string|true|none|none|
|» tenant|object|true|none|none|
|»» name|string|true|none|none|
|»» uuid|string|true|none|none|

<h3 id="tocSi18ns">I18ns</h3>

<a id="schemai18ns"></a>

```json
{
  "payload": [
    {
      "uuid": "string",
      "payload": "string",
      "type": "string",
      "tenant": {
        "name": "string",
        "uuid": "string"
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
|» payload|string|true|none|none|
|» type|string|true|none|none|
|» tenant|object|true|none|none|
|»» name|string|true|none|none|
|»» uuid|string|true|none|none|

<h3 id="tocSi18nscreatereq">I18nsCreateReq</h3>

<a id="schemai18nscreatereq"></a>

```json
{
  "type": "string",
  "payload": "string",
  "tenant": "string"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|type|string|true|none|none|
|payload|string|true|none|none|
|tenant|string|true|none|none|

<h3 id="tocSstoresetting">StoreSetting</h3>

<a id="schemastoresetting"></a>

```json
{
  "payload": {
    "uuid": "string",
    "value": "string",
    "store": {
      "uuid": "string",
      "name": "string",
      "tenant": {
        "uuid": "string",
        "name": "string"
      }
    },
    "setting": {
      "uuid": "string",
      "key": "string"
    }
  }
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|payload|object|true|none|none|
|» uuid|string|true|none|none|
|» value|string|true|none|none|
|» store|object|true|none|none|
|»» uuid|string|true|none|none|
|»» name|string|true|none|none|
|»» tenant|object|true|none|none|
|»»» uuid|string|true|none|none|
|»»» name|string|true|none|none|
|»» setting|object|true|none|none|
|»»» uuid|string|true|none|none|
|»»» key|string|true|none|none|

<h3 id="tocSstoresettings">StoreSettings</h3>

<a id="schemastoresettings"></a>

```json
{
  "payload": [
    {
      "uuid": "string",
      "value": "string",
      "store": {
        "uuid": "string",
        "name": "string",
        "tenant": {
          "uuid": "string",
          "name": "string"
        }
      },
      "setting": {
        "uuid": "string",
        "key": "string"
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
|» value|string|true|none|none|
|» store|object|true|none|none|
|»» uuid|string|true|none|none|
|»» name|string|true|none|none|
|»» tenant|object|true|none|none|
|»»» uuid|string|true|none|none|
|»»» name|string|true|none|none|
|»» setting|object|true|none|none|
|»»» uuid|string|true|none|none|
|»»» key|string|true|none|none|

<h3 id="tocSstoresettingcreatereq">StoreSettingCreateReq</h3>

<a id="schemastoresettingcreatereq"></a>

```json
{
  "storeUUID": "string",
  "settingUUID": "string",
  "value": "string"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|storeUUID|string|true|none|none|
|settingUUID|string|true|none|none|
|value|string|true|none|none|

<h3 id="tocStenantsetting">TenantSetting</h3>

<a id="schematenantsetting"></a>

```json
{
  "payload": {
    "uuid": "string",
    "value": "string",
    "tenant": {
      "uuid": "string",
      "name": "string"
    },
    "setting": {
      "uuid": "string",
      "key": "string"
    }
  }
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|payload|object|true|none|none|
|» uuid|string|true|none|none|
|» value|string|true|none|none|
|» tenant|object|true|none|none|
|»» uuid|string|true|none|none|
|»» name|string|true|none|none|
|» setting|object|true|none|none|
|»» uuid|string|true|none|none|
|»» key|string|true|none|none|

<h3 id="tocStenantsettings">TenantSettings</h3>

<a id="schematenantsettings"></a>

```json
{
  "payload": [
    {
      "uuid": "string",
      "value": "string",
      "tenant": {
        "uuid": "string",
        "name": "string"
      },
      "setting": {
        "uuid": "string",
        "key": "string"
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
|» value|string|true|none|none|
|» tenant|object|true|none|none|
|»» uuid|string|true|none|none|
|»» name|string|true|none|none|
|» setting|object|true|none|none|
|»» uuid|string|true|none|none|
|»» key|string|true|none|none|

<h3 id="tocStenantsettingupdatereq">TenantSettingUpdateReq</h3>

<a id="schematenantsettingupdatereq"></a>

```json
{
  "value": "string"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|value|string|true|none|none|

