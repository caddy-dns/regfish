regfish module for Caddy
===========================

This package contains a DNS provider module for [Caddy](https://github.com/caddyserver/caddy). It can be used to manage DNS records with regfish.

## Caddy module name

```
dns.providers.regfish
```

## Config examples

To use this module for the ACME DNS challenge, [configure the ACME issuer in your Caddy JSON](https://caddyserver.com/docs/json/apps/tls/automation/policies/issuer/acme/) like so:

```json
{
	"module": "acme",
	"challenges": {
		"dns": {
			"provider": {
				"name": "regfish",
				"api_key": "REGFISH_API_KEY"
			}
		}
	}
}
```

or with the Caddyfile:

```
# globally
{
	acme_dns regfish {
		api_key {env.REGFISH_API_KEY}
	}
}
```

```
# one site
tls {
	dns regfish {
		api_key {env.REGFISH_API_KEY}
	}
}
```
