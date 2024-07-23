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
