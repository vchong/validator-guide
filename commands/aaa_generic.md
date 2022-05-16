# Generic

Create Validator

```bash
BINARY tx staking create-validator \
    --amount="AMOUNT" \
    --pubkey=$(BINARY tendermint show-validator) \
    --chain-id="CHAIN_ID" \
    --from="KEY" \
    --node="http://localhost:26657"
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
