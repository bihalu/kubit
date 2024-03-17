# lnd

## github
https://github.com/lightningnetwork/lnd

## sample-lnd.conf
https://github.com/lightningnetwork/lnd/blob/master/sample-lnd.conf

## convert lnd.conf to lnd-conf-secret.yaml
```
BASE64=$(cat lnd.conf | base64 -w0)

cat << EOF > lnd-conf-secret.yaml
apiVersion: v1
kind: Secret
metadata:
  name: lnd-conf
  namespace: bitcoin
data:
  lnd.conf: $BASE64
type: Opaque
EOF
```