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

## bitcoin chainquery
https://chainquery.com/bitcoin-cli#

## bitcoin cli
https://github.com/BlockchainCommons/Learning-Bitcoin-from-the-Command-Line/blob/master/03_2_Knowing_Your_Bitcoin_Setup.md#optional-know-your-bitcoin-info

```
 bitcoin-cli -getinfo

 bitcoin-cli -netinfo 4

 bitcoin-cli -addrinfo

 bitcoin-cli -version
```