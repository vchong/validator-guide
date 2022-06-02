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

terrad tx staking create-validator \
 --amount="9000000000ukuji" \
 --pubkey=$(kujirad tendermint show-validator) \
 --chain-id="harpoon-3" \
 --from="kujira_test" \
 --node="http://localhost:18657" \
 --commission-max-change-rate "0.05" \
 --commission-max-rate "0.10" \
 --commission-rate "0.05" \
 --min-self-delegation "1" \
 --moniker "polkachu.com" \
 --website "https://polkachu.com" \
 --identity "0A6AF02D1557E5B4" \
 --details "Polkachu is the trusted staking service provider for blockchain projects. 100% refund for downtime slash. Contact us at hello@polkachu.com" \
 --security-contact "hello@polkachu.com"

Gentx

terrad gentx polkachu_terra 1000000uluna \
 --chain-id="phoenix-1" \
 --pubkey=$(terrad tendermint show-validator) \
 --min-self-delegation="1"\
 --commission-max-change-rate "0.05" \
 --commission-max-rate "0.10" \
 --commission-rate "0" \
 --min-self-delegation "1" \
 --moniker " polkachu.com" \
 --website "https://polkachu.com" \
 --identity "0A6AF02D1557E5B4" \
 --details "Polkachu is the trusted staking service provider for blockchain projects. 100% refund for downtime slash. Contact us at hello@polkachu.com" \
 --security-contact "hello@polkachu.com"

terrad tx staking delegate terravaloper1rr2g4z2ch4cqwl8s70yj94a5l2vakg0v36nmjh 98000000uluna --from polkachu_terra --node http://localhost:17657 --chain-id phoenix-1
