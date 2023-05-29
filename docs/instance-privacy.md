Instance privacy aims to bring transparency to the data collected by frontends and to encourage privacy-friendly practices. There is often no privacy policy and users are forced to trust that the instance operator is not collecting data. However, there is a possibility that the instance operator can put false information so we encourage looking at other factors when selecting an instance.

## Data types
- IP Address - your IP address can be used to find the city you live in but it isn't very accurate and can change depending on your internet connection.
- Request URL - this is what is in the bar on your browser, it contains information like the video you're watching or channel you're looking at.
- Device Type - this contains the browser and device you're using.
- Diagnostics - when this data is only collected when there is an error and only a short amount of time while diagnosing an issue.

## For instance operators
You are probably unintenionally collecting the data above if you are using NGINX. If you use Traefik, enable `DATA_NOT_COLLECTED`, this setting overrides any other selections, otherwise follow the steps for other web servers below.

### NGINX
Add `access_log off;` to your server block in your NGINX config. If you wish to continue collecting the data, you will need to modify the config.yml file and select the types of data you are collecting.

### Caddy
Caddy logs all data types to stderr when there is a non-400 error code. If you wish to continue collecting the data, enable all types and Diagnostics. To disable, add the following to your Caddyfile:
```
domain.tld {
  log {
    output discard
  }
  # ...
}
```

### Traefik
Traefik does not collect data by default. If you have configured it to do so, select the types of data you are collecting.