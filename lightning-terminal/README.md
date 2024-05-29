# lightning-terminal

## github
https://github.com/lightninglabs/lightning-terminal    

## sample lit.conf
https://github.com/lightninglabs/lightning-terminal/blob/master/doc/config-lnd-integrated.md  

## convert lit.conf to lit-conf-secret.yaml
```
BASE64=$(cat lit.conf | base64 -w0)

cat << EOF > lit-conf-secret.yaml
apiVersion: v1
kind: Secret
metadata:
  name: lit-conf
  namespace: bitcoin
data:
  lit.conf: $BASE64
type: Opaque
EOF
```
