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

## lightning network
https://terminal.lightning.engineering/  

https://1ml.com/  
https://amboss.space/  

## lightning cli
https://docs.lightning.engineering/lightning-network-tools/lnd/first-steps-with-lnd  

```
lncli getinfo

lncli unlock

lncli walletbalance

lncli newaddress p2tr

lncli listpeers

lncli connect <pubkey>@<host>:<port>

lncli connect 037f66e84e38fc2787d578599dfe1fcb7b71f9de4fb1e453c5ab85c05f5ce8c2e3@207.154.241.207:9735
```
