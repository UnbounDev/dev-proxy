dev-proxy
===============

Simple SSL HTTP proxy using a self-signed certificate. Intended for local development only. Based off of [local-ssl-proxy](https://github.com/cameronhunter/local-ssl-proxy).

```
Usage: local-ssl-proxy [options]

Options:

  -h, --help            output usage information
  -V, --version         output the version number
  -p --proxy [value]    Ports to proxy
  -k --key [keyPath]    Optional path to key file
  -c --cert [certPath]  Optional path to cert file
  -h --host [hostname]  Optional hostname
```

Install
-------
```sh
npm install -g dev-proxy
# will automatically generate a self-signed cert/key
```

Run
---
To start a proxying from port `9000` to `9001` run:
```sh
dev-proxy --proxy 9000:9001
```

To create multiple proxies run:
```sh
dev-proxy --proxy 8080:8443 --proxy 9080:9443
```

Start your web server on the source port (`9000` in the example) and navigate to `https://localhost:<target-port>` ([https://localhost:9001](https://localhost:9001) in the example). You'll get a warning because the certificate is self-signed, this is safe to ignore during development.
