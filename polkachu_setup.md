# Polkachu Setup Notes

## Mainnet Bridging Tracking

| Network   | Validator key | Cosmos Orchestrator Key | Ethereum Orchestrator Key                  |
| --------- | ------------- | ----------------------- | ------------------------------------------ |
| Gravity   | Default       | Default Orchestrator    | 0x99E43230eCec926a7FFc2E4CD22153494D5a84a3 |
| Sommelier | Default       | Default Orchestrator    | 0x99E43230eCec926a7FFc2E4CD22153494D5a84a3 |
| Umee      | Default       | Umee Orchestrator / Bot | 0x99E43230eCec926a7FFc2E4CD22153494D5a84a3 |
| Injective | Default       | Injective Orchestrator  | 0xB497abA1E4Ce24B4ADc2E16Ded30387042B881B7 |
| Axelar    | Default       | Default Orchestrator    | N/A                                        |

## Relayer Setup Notes

Polkachu's Relayer Node can server any combination of the following functions:

1. Relayer
1. API
1. RPC
1. State-Sync

Multiple Relayer Nodes can resides on the same server (a so-called Hub). Polkachu currently has 3 Hubs (Juno Hub, Osmosis Hub, and Cosmos Hub). Relayer Hub RPC ports open to each other. When relaying, make sure that the Hermes service depends on the node service in their startup sequence.

Relayer Node's app.toml/config.toml settings is as follows:

```bash
# Pruning
pruning = "custom"
pruning-keep-recent = "40000"
pruning-keep-every = "2000"
pruning-interval = "19" # Or another prime number

# Snapshot
snapshot-interval = "2000"
snapshot-keep-recent = "5"

# Indexer
indexer = "kv"

# RPC
[rpc]
laddr = "tcp://0.0.0.0:26657" # Or a custom RPC port

# API
[api]
enabled = true
swagger = true # Or false if no swagger is preferred
```

## Polkachu's Testnet Setup

Legacy

| Network  | Port Prefix |
| -------- | ----------- |
| Celestia | 33          |
| Deweb    | 28          |

Canonical

| Network     | Port Prefix |
| ----------- | ----------- |
| Kyve        | 10          |
| Quicksilver | 11          |
| Defund      | 12          |
| Comdex      | 31          |
| Evmos       | 34          |
| Kichain     | 35          |
| Umee        | 36          |
