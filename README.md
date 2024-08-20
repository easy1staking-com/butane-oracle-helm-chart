# butane-oracle-helm-chart

This chart requires a secret that you can create as follows:

```bash
k create secret generic butane-oracle-secrets \
    --dry-run=client \
    --from-file private.pem \
    --from-file frost.skey \
    --from-file frost.vkey -o yaml > secrets.yaml
```

And then apply the `secrets.yaml` in the relevant namespace.

## How to install

Add repository to helm repos with

`helm repo add butane-oracle https://easy1staking-com.github.io/butane-oracle-helm-chart/`

Then install with

`helm upgrade --install [-n my-namespace] butane-oracle butane-oracle [-f my-values-file.yaml]`

## FX Rate API

The `FXRATESAPI_API_KEY` env var can be populated with an api key from https://fxratesapi.com/.

The api key is not required but without it, this instance of the bot won't be able to participate in 
some price signature.
