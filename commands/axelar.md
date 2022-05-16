# Testnet

Query balance

```bash
axelard q bank balances axelar1jt9w26mpxxjsk63mvd4m2ynj0af09csl80gwzs \
    --node=http://localhost:51657
```

Register broadcaster proxy

```bash
axelard tx bank send axelar_test axelar1xrrfek3qpz4ja8ccrjklfy064asyqq9khuq8lw 2000000uaxl  \
    --node="http://localhost:51657" \
    --from="axelar_test" \
    --chain-id="axelar-testnet-casablanca-1"
```

Create Validator

```bash
axelard tx staking create-validator \
    --amount="1000000uaxl" \
    --pubkey=$(axelard tendermint show-validator) \
    --node="http://localhost:51657" \
    --from="axelar_test" \
    --chain-id="axelar-testnet-casablanca-1" \
    --commission-max-change-rate "0.05" \
    --commission-max-rate "0.10" \
    --commission-rate "0.05" \
    --min-self-delegation "1" \
    --moniker "polkachu.com" \
    --website "https://polkachu.com" \
    --identity "0A6AF02D1557E5B4" \
    --details "Polkachu is the trusted staking service provider for blockchain projects. 100% refund for downtime slash. Contact us at hello@polkachu.com" \
    --security-contact "hello@polkachu.com"
```

Health Check

```bash
axelard health-check \
    --tofnd-host="localhost" \
    --operator-addr="axelarvaloper1jt9w26mpxxjsk63mvd4m2ynj0af09csl8w7tsl" \
    --node="http://localhost:51657"
```

Delegate

```bash
axelard tx staking delegate axelarvaloper1jt9w26mpxxjsk63mvd4m2ynj0af09csl8w7tsl 200000000uaxl \
    --node="http://localhost:51657" \
    --from="axelar_test" \
    --chain-id="axelar-testnet-casablanca-1"
```
