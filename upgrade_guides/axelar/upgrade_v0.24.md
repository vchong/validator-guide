# Axelar v0.24 Upgrade

Upgrade height is `3644000`

```bash
# get the new version
cd axelar
git pull
git checkout v0.24.0
make build
mv ~/axelar/bin/axelard ~/go/bin
```

# check the version

```bash
# should be 0.24.0
axelard version
# Should be commit 981196d61fea1b9ad66eab69b27ae2ff3c2524b2
axelard version --long
```

# Make new directory and copy binary

```bash
mkdir -p $HOME/.axelar/cosmovisor/upgrades/v0.24/bin
cp $HOME/go/bin/axelard $HOME/.axelar/cosmovisor/upgrades/v0.24/bin
```

# check the version again

```bash
# should be 0.24.0
$HOME/.axelar/cosmovisor/upgrades/v0.24/bin/axelard version
```
