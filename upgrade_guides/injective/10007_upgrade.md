# Injective 10007 Upgrade using Cosmovisor

The Upgrade is scheduled for block `14731000`. A countdown clock is [here](https://www.mintscan.io/injective/blocks/14731000).

Get the new version

```bash
wget https://github.com/InjectiveLabs/injective-chain-releases/releases/download/v1.7.0-1661631860/linux-amd64.zip
unzip linux-amd64.zip
mv injectived $HOME/go/bin
```

Remove unused files

```bash
rm injective-exchange
rm linux-amd64.zip
rm libwasmvm.x86_64.so
rm peggo # Alternatively, you can replace the current Peggo. But there is no Peggo version change in this upgrade
```

Check the version - should be 568ce23

```bash
injectived version

# Result
Version dev (6a0cae53)
Compiled at 20220827-2024 using Go go1.18.5 (amd64)
```

If you are using cosmovisor, you then need to create folder and copy this new binary

```bash
mkdir -p $HOME/.injectived/cosmovisor/upgrades/v1.7/bin
cp $HOME/go/bin/injectived $HOME/.injectived/cosmovisor/upgrades/v1.7/bin
```

Find out what version you are about to run - should be 6a0cae53

```bash
$HOME/.injectived/cosmovisor/upgrades/v1.7/bin/injectived version
```
