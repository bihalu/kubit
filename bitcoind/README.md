# bitcoin

## bitcoin core config generator
https://jlopp.github.io/bitcoin-core-config-generator/

## convert bitcoin.conf to bitcoin-conf-secret.yaml
```
BASE64=$(cat bitcoin.conf | base64 -w0)

cat << EOF > bitcoin-conf-secret.yaml
apiVersion: v1
kind: Secret
metadata:
  name: bitcoin-conf
  namespace: bitcoin
data:
  bitcoin.conf: $BASE64
type: Opaque
EOF
```