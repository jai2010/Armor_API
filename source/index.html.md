---
title: Armor Escrow Payments API Reference

language_tabs:
  - cURL
  - ruby
  - PHP
  - Node
  
toc_footers:
  - <a href='#'>Sign Up for a Developer Key</a>
  - <a href='#'>Quick Start Guide</a>
  - <a href='#'>Release Notes</a>
  - <a href='#'>Support</a>
  
includes:
  - errors

search: true
---

# Getting Started

Welcome to Armor Escrow Payments API Documentation.

Armor Payments Escrow as a Service offers the flexibility to support a variety of payment use cases. As a licensed escrow provider through our wholly owned subsidiary, Armor Escrow Inc., Armor Payments takes on the regulatory burden, the money movement complexities, and the dispute management (for relevant order types), allowing our partners to focus on serving their payers and payees. 

See below for the supported use cases and API details.



> To authorize, use this code:

```ruby
require 'kittn'

api = Kittn::APIClient.authorize!('meowmeowmeow')
```

```python
import kittn

api = kittn.authorize('meowmeowmeow')
```

```shell
# With shell, you can just pass the correct header with each request
curl "api_endpoint_here"
  -H "Authorization: meowmeowmeow"
```

> Make sure to replace `meowmeowmeow` with your API key.

Kittn uses API keys to allow access to the API. You can register a new Kittn API key at our [developer portal](http://example.com/developers).

Kittn expects for the API key to be included in all API requests to the server in a header that looks like the following:

`Authorization: meowmeowmeow`

<aside class="notice">
You must replace <code>meowmeowmeow</code> with your personal API key.
</aside>

<div class="separator"></div>
---

# Development
## Authentication
### Authentication Keys
## Conventions
## Webhooks
## Environment
## Test Harness
## Client Libraries
## Integration Guide

# Authentication
## API Key
## Authentication

# Account
## Account Object

An Account represents a company (as compared to a User entity, which represents a person at that company).

Attributes | Type | Description
-------------- | --------------  | -------------- 
**account_id**  | *integer* | The identifier of this Account company
**company** | *string* | The name of the company this Account belongs to address
**address** | *string* | The street address of the company city
**city** | *string* | The city the street address is located in state
**state** | *string* | The state/province of the address postal_code
**postal_code** | *string* | string — The postal code of the address country
**country** | *string* | The country of the address, formatted as an ISO 3166-1 alpha-2 two-letter country code (e.g. "us", or "uk").
**phone** | *string* | The Account's phone number, formatted with international dialing code and number (e.g. "+1 5551234567") 
**created** | *string* | The date/time this Account was created, formatted as an ISO 8601 time/date stamp (e.g. "2014-07-21T22:26:52-05:00") 
**uri** | *string* | The URI used to reference this Account

## Create Account
>  POST https://api.armorpayments.com/accounts/

```shell
Sample Request

-H "x-armorpayments-apikey:MyApiKey"
-H "x-armorpayments-requesttimestamp:2014-01-01T00:00:00+00:00"
-H "x-armorpayments-signature:359d90dfa341caab566cca33de6"
-d "foo=bar&biz=baz"
	https://api.armorpayments.com/accounts/190036
```
	
```shell
Sample Response

{
	"account_id":"290465",
	"company":"ACME Inc.",
	"address":null,
	"city":null,
	"state":null,
	"postal_code":null,
	"country":null,
	"phone":null,
	"created":"2014-01-28T17:31:25+00:00",
	"uri":"\/accounts\/290465"
}
```


You can create accounts for your users.


**Parameters**

Parameters | Type | Required | Description
-------------- | --------------  | -------------- | -------------- 
**company** | *string* | *required* | The name of the company this Account belongs to address
**address** | *string* | *required* | The street address of the company city
**city** | *string* | *required* | The city the street address is located in state
**state** | *string* | *required* | The state/province of the address postal_code
**postal_code** | *string* | *required* | The postal code of the address country
**country** | *string* | *required* | The country of the address, formatted as an ISO 3166-1 alpha-2 two-letter country code (e.g. "us", or "uk").
**phone** | *string* | *required* | The Account's phone number, formatted with international dialing code and number (e.g. "+1 5551234567") 
**tax_id** | *string* | *optional* | The tax ID for the account (US-based accounts only)


**Returns**

Returns an Account entity object.

## Retrieve Account details
```curl
Sample Request

-H "x-armorpayments-apikey:MyApiKey"
-H "x-armorpayments-requesttimestamp:2014-01-01T00:00:00+00:00"
-H "x-armorpayments-signature:359d90dfa341caab566cca33de6"
-d "foo=bar&biz=baz"
	https://api.armorpayments.com/accounts/190036
```
	
```curl
Sample Response

{
	"account_id":"290465",
	"company":"ACME Inc.",
	"address":null,
	"city":null,
	"state":null,
	"postal_code":null,
	"country":null,
	"phone":null,
	"created":"2014-01-28T17:31:25+00:00",
	"uri":"\/accounts\/290465"
}
```

Retrieve details about an existing account.

>  GET https://api.armorpayments.com/accounts/{account_id}


**URI Parameters**

Parameters | Type | Required | Description
-------------- | --------------  | -------------- | -------------- 
**account_id**  | *integer* | *Required* | The identifier of this Account company


**Returns**

Returns an Account entity object.




## Update Account details
>  POST https://api.armorpayments.com/accounts/{account_id}

```curl
Sample Request

-H "x-armorpayments-apikey:MyApiKey"
-H "x-armorpayments-requesttimestamp:2014-01-01T00:00:00+00:00"
-H "x-armorpayments-signature:359d90dfa341caab566cca33de6"
-d "foo=bar&biz=baz"
	https://api.armorpayments.com/accounts/190036
```
	
```curl
Sample Response

{
	"account_id":"290465",
	"company":"ACME Inc.",
	"address":null,
	"city":null,
	"state":null,
	"postal_code":null,
	"country":null,
	"phone":null,
	"created":"2014-01-28T17:31:25+00:00",
	"uri":"\/accounts\/290465"
}
```

Update an existing user account.


**URI Parameters**

Parameters | Type | Required | Description
-------------- | --------------  | -------------- | -------------- 
**account_id**  | *integer* | *Required* | The identifier of this Account company


**Request body parameters**

Parameters | Type | Required | Description
-------------- | --------------  | -------------- | -------------- 
**company** | *string* | *required* | The name of the company this Account belongs to address
**address** | *string* | *required* | The street address of the company city
**city** | *string* | *required* | The city the street address is located in state
**state** | *string* | *required* | The state/province of the address postal_code
**postal_code** | *string* | *required* | The postal code of the address country
**country** | *string* | *required* | The country of the address, formatted as an ISO 3166-1 alpha-2 two-letter country code (e.g. "us", or "uk").
**phone** | *string* | *required* | The Account's phone number, formatted with international dialing code and number (e.g. "+1 5551234567") 
**tax_id** | *string* | *optional* | The tax ID for the account (US-based accounts only)


**Returns**

Returns an Account entity object.



    
## User
## User Terms
## Payout

# Partner
## Partner
## Partner Accounts
## Partner Users
## Partner Orders
## Partner History

# Escrow Order
## Order
## Order Documents
## Order Notes
## Order Events
## Order Ledger
## Order User Actions

# Escrow Payment
## Payment Instructions

# Shipment
## Shipment Carriers

# Dispute
## Dispute
## Dispute Documents
## Dispute Notes
## Offer
## Offer Documents
## Offer Notes




