# Agoric agoric-upgrade-8 Upgrade

The Upgrade is scheduled for block `7179262`. A countdown clock is [here](https://ping.pub/agoric/gov/16)

This guide assumes that you use cosmovisor to manage upgrades

This upgrade is a major upgrade with some agoric Javascript VM specific procedures. Please follow the [official guide](https://github.com/Agoric/agoric-sdk/wiki/ag0-to-agd-upgrade). You wil install NodeJS, Yarn and the agd binary.

# check the version

```bash
# should be 0.32.2
agd version
# Should be commit 2c812d221
agd version --long
```

# Two important caveats

Because this is a major upgrade, we want to call out two important issues before proceeding with this guide.

1. The binary file name has been changed from ag0 to agd. This will be a potential issue for cosmovisor users.
2. The node require access to a `ag-chain-cosmos` file (or symlink) deep in the `agoric-sdk` repo. This will be a potential issue for a systemd service that does not understand where to look for it.

This guide offers one solution for each caveat while we fully aware there are other solutions. Please do your own research to find out what's best for your situation.

# 1. Solve ag0/agd confusion

As a degen validator, we will take the lazy approach and just rename the binary to ag0 for cosmovisor.

```bash
mkdir -p $HOME/.agoric/cosmovisor/upgrades/agoric-upgrade-8/bin
cp /home/ubuntu/go/bin/agd $HOME/.agoric/cosmovisor/upgrades/agoric-upgrade-8/bin/ag0
```

check the version again

```bash
# should be 0.32.2
$HOME/.agoric/cosmovisor/upgrades/agoric-upgrade-8/bin/ag0 version
```

# 2. Solve ag-chain-cosmos lookup issue

As a degen validator, we will add the `ag-chain-cosmos` path to the systemd PATH Environment variable. See below. The last part is the important one. You might have a slightly different path depending your file/folder structure.

```bash
Environment="PATH=/home/ubuntu/bin:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin:/home/ubuntu/agoric-sdk/packages/cosmic-swingset/bin"
```

```bash
sudo systemctl daemon-reload
sudo service agoric restart
```
