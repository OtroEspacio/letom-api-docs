---
title: Letom API Reference

language_tabs:
  - shell

toc_footers:
  - <a href='https://github.com/lord/slate' target="_blank">Documentation Powered by Slate</a>

includes:
  - errors
  - motels
  - room_types
  - reservations
  - consumers

search: false
---

# Introduction

You can use our API to access Letom API endpoints, which can get information on various motels, room types, make reservations and more.

# Authentication

> To authorize, you must send an `Authorization` header containing a valid `access_token` in your request as in the following piece of code:

```shell
# With shell, you can just pass the correct header with each request
curl "https://api-letom.herokuapp.com/v1"
  -H "Authorization: SUPER-COOL-ACCESS-TOKEN"
  -H "Accept: application/vnd.letom.v1"
```

> Make sure to replace `SUPER-COOL-ACCESS-TOKEN` with _your_ access token.

Letom uses access tokens to allow access to the API.

Letom expects for the access tokens to be included in all API requests to the server in a header that looks like the following:

`Authorization: SUPER-COOL-ACCESS-TOKEN`

<aside class="notice">
You must replace <code>SUPER-COOL-ACCESS-TOKEN</code> with _your_ access token.
</aside>

> If you do not send a valid `Authorization` header you'll get a `not_authenticated` error message:

```json
{
  "errors": "Not authenticated"
}
```

## Base URL

This is the main fragment all requests URLs are based from.

> The base URL for API version 1 is

```
https://letom-st.herokuapp.com/v1
```

### Note on Base URL

This project API is intended to have a custom subdomain `api` however, when this is deployed to Heroku in the free tier, it is not possible because the platform already provides a subdomain.
