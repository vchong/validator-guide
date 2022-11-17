# Injective 10008 Upgrade using Cosmovisor

The Upgrade is scheduled for block `19761600`. A countdown clock is [here](https://www.mintscan.io/injective/blocks/19761600).

Get the new version

```bash
wget https://github.com/InjectiveLabs/injective-chain-releases/releases/download/v1.8.0-1668679102/linux-amd64.zip
unzip linux-amd64.zip
mv injectived $HOME/go/bin
```

Remove unused files

```bash
rm injective-exchange
rm linux-amd64.zip
rm libwasmvm.x86_64.so
rm peggo
```

Check the version - should be ade8906

```bash
injectived version

# Result
Version dev (64c9081)
Compiled at 20221117-0959 using Go go1.18.3 (amd64)
```

If you are using cosmovisor, you then need to create folder and copy this new binary

```bash
mkdir -p $HOME/.injectived/cosmovisor/upgrades/v1.8/bin
cp $HOME/go/bin/injectived $HOME/.injectived/cosmovisor/upgrades/v1.8/bin
```

Find out what version you are about to run - should be 6a0cae53

```bash
# should be 64c9081
$HOME/.injectived/cosmovisor/upgrades/v1.8/bin/injectived version
```
