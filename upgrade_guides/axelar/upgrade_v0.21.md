# Axelar v0.21 Upgrade

Upgrade height is `3643500`

```bash
# get the new version
cd axelar
git pull
git checkout v0.21.1
make build
mv ~/axelar/bin/axelard ~/go/bin
```

# check the version

```bash
# should be 0.21.1
axelard version
# Should be commit 246984b0f5c234d4922fedf3e5078b8e58b78a3c
axelard version --long
```

# Make new directory and copy binary

```bash
mkdir -p $HOME/.axelar/cosmovisor/upgrades/v0.21/bin
cp $HOME/go/bin/axelard $HOME/.axelar/cosmovisor/upgrades/v0.21/bin
```

# check the version again

```bash
# should be 0.21.1
$HOME/.axelar/cosmovisor/upgrades/v0.21/bin/axelard version
```
