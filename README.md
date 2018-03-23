# gke-bitcoin-node

This project deploys Bitcoin to Google Kubernetes Engine (GKE). It uses the Docker image built [here](https://github.com/bonovoxly/docker-bitcoind).

# Deployment - Testnet

This deployment will create a Bitcoin Kubernetes deployment and persistent volume claim (NOTE: **300GB**).

This deployment is meant to substitute in your environment variables, to protect secrets and passwords. The following is an example:

```
BTC_RPCUSER=test BTC_RPCPASSWORD=testpassword BTC_RPCALLOWIP=10.3.0.0/14 BTC_TESTNET=1 envsubst < test-bitcoin-node.yml > test-deploy.yml
kubectl create -f test-deploy.yml
```

# Deployment - Production

This deployment will create a Bitcoin Kubernetes deployment and persistent volume claim (NOTE: **300GB**).

This deployment is meant to substitute in your environment variables, to protect secrets and passwords. The following is an example:

```
# don't use these username/passwords
BTC_RPCUSER=user BTC_RPCPASSWORD=password BTC_RPCALLOWIP=10.3.0.0/14 envsubst < bitcoin-node.yml > deploy.yml
kubectl create -f deploy.yml
```
