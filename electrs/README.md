# electrs

## electrs config
https://github.com/romanz/electrs/blob/master/doc/config.md#configuration-files-and-priorities

## convert electrs.toml to electrs-conf-secret.yaml
```
BASE64=$(cat electrs.toml | base64 -w0)

cat << EOF > electrs-conf-secret.yaml
apiVersion: v1
kind: Secret
metadata:
  name: electrs-conf
  namespace: bitcoin
data:
  config.toml: $BASE64
type: Opaque
EOF
```