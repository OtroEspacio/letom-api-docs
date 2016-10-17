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

search: false
---

# Introduction

You can use our API to access Letom API endpoints, which can get information on various motels, room types, make reservations and more.

# Authentication

> To authorize, use this code:

```shell
# With shell, you can just pass the correct header with each request
curl "https://api-letom.herokuapp.com/v1"
  -H "Authorization: meowmeowmeow"
  -H "Accept: application/vnd.letom.v1"
```

> Make sure to replace `meowmeowmeow` with your API key.

Letom uses API keys to allow access to the API.

Letom expects for the API key to be included in all API requests to the server in a header that looks like the following:

`Authorization: meowmeowmeow`

<aside class="notice">
You must replace <code>meowmeowmeow</code> with your API key.
</aside>

## Base URL

This is the main fragment all requests URLs are based from.

> The base URL for API version 1 is

```
https://api-letom.herokuapp.com/v1
```
