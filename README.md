# Netlify Build Plugin - Send Netlify url to import-map-deployer

> This plugin make an HTTP Request to import-map-deployer with your build file.

## Request

```JSON
{
  "url": "${IMPORTMAP_URL}",
  "method": "PATCH",
  "headers": {
    "content-type": "application/json",
    "authorization": "${IMPORTMAP_AUTH}",
  },
  "body": {
    "service": "${IMPORTMAP_SERVICE}",
    "url": "${IMPORTMAP_FILE_URL}${IMPORTMAP_FILE}",
  }
}
```

## Installation

```sh
npm install netlify-plugin-importmap-single-spa
```

## Variables

- IMPORTMAP_URL - URL of your import-map-deployer
- IMPORTMAP_AUTH - Parameter `authorization` of your request - it's advisable to define in the Netlify UI
- IMPORTMAP_FILE_URL - Netlify URL
- IMPORTMAP_FILE - Filename regex, this file is fetched in your build folder with `RegExp(IMPORTMAP_FILE).test`
- IMPORTMAP_SERVICE - Import-map-deployer service parameter

## Usage

Add the following lines to your `netlify.toml` file:

```toml

[[plugins]]
  package = "netlify-plugin-importmap-single-spa"

[build.environment]
  IMPORTMAP_FILE = "^[0-9a-f]{7}.filename.js$"
  IMPORTMAP_SERVICE = "@single-spa-books/root-config"
  IMPORTMAP_FILE_URL = "https://single-spa-books.netlify.app/"
  IMPORTMAP_URL = "https://single-spa-books.herokuapp.com/services?skip_url_check"
  IMPORTMAP_AUTH = Basic c2sduZ2xvLX43NwYS1i7295cy

```
