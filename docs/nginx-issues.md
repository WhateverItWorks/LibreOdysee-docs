[Caddy](https://caddyserver.com/) is the recommended reverse proxy for ease of use, performance, and compatibility. However, it is possible to use NGINX but you may need to make changes to your configuration.

## Trailing slash
A trailing slash in the URL in `proxy_pass` will cause issues with certain URLs. See this [issue comment](https://codeberg.org/librarian/librarian/issues/170#issuecomment-705890).

## Performance
It is highly recommended to enable HTTP/2 especially if you have stream proxy or livestreams enabled. Follow [this guide](https://www.tecmint.com/enable-http-2-in-nginx/) to enable it.