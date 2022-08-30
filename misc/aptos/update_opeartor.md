# Aptos: Update Operator

In Aptos, `Owner` has the full control of a wallet and a staking pool, but is able to delegate a different wallet as `operator` and/or `voter`.

This guide assumes that

1. An `Owner` currently delegates both `operator` and `voter` roles to one wallet
2. The `Owner` will delegates both `Operator` and `Voter` roles to another wallet that will be created in the Petra Wallet.
3. Rather than creating a new validator node and a full node, we will simply update the configuration on the current two nodes.

The guide also applies to a situation in AIT3 where the genesis validators need to create a new `Operator` wallet due to a genesis mistake.

## Create a wallet in Petra

Download the wallet here https://petra.app/. If you are in AIT3, you live in the cutting edge and probably need to download the latest version from the team.

Create a new wallet. Write down the seed phrase, private key, public key and address. They will be refer to as `PRIVATE_KEY`, `PUBLIC_KEY` and `ADDRESS` in the rest of the guide.

When using `ADDRESS`, it is without `0x` prefix.

## Owner delegate to the new operator address

```shell
aptos stake set-operator \
 --operator-address `ADDRESS` \
 --profile ait3-owner
```

```shell
aptos stake set-delegated-voter \
 --voter-address `ADDRESS` \
 --profile ait3-owner
```

## Validator Node Configuration (MUST)

| File                    | Field               | New Value     |
| ----------------------- | ------------------- | ------------- |
| validator-identity.yaml | account_private_key | `PRIVATE_KEY` |

## Full Node Configuration (MUST)

| File                              | Field           | New Value |
| --------------------------------- | --------------- | --------- |
| validator-full-node-identity.yaml | account_address | `ADDRESS` |

## House Keeping (OPTIONAL)

| File              | Field                       | New Value     |
| ----------------- | --------------------------- | ------------- |
| owner.yaml        | voter_account_address       | `ADDRESS`     |
| owner.yaml        | voter_account_public_key    | `PUBLIC_KEY`  |
| owner.yaml        | operator_account_address    | `ADDRESS`     |
| owner.yaml        | operator_account_public_key | `PUBLIC_KEY`  |
| operator.yaml     | operator_account_address    | `ADDRESS`     |
| operator.yaml     | operator_account_public_key | `PUBLIC_KEY`  |
| private-keys.yaml | account_address             | `ADDRESS`     |
| private-keys.yaml | account_private_key         | `PRIVATE_KEY` |
| public-keys.yaml  | account_address             | `ADDRESS`     |
| public-keys.yaml  | account_public_key          | `PUBLIC_KEY`  |

## Restart Service

PUBLIC_KEY: 0x9f1362e528f52780dc38d447102cb1a92bea80503b4943be91133415110a5369
ADDRESS: aec8a97955aaafb2b1609418b5aed1c2b2a8c738472f7788b2fd189f78bbbf26
