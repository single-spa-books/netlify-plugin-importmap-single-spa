# Netlify Build Plugin - Send Netlify url to import-map-deployer

## ☁️ Installation

```sh
npm install netlify-plugin-importmap-single-spa
```

## Variables

- IMPORTMAP_URL - URL of your import-map-deployer
- IMPORTMAP_AUTH - Parameter `authorization`
- IMPORTMAP_FILE_URL
- IMPORTMAP_FILE
- IMPORTMAP_SERVICE

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
