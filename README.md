# BENDIR
![image](https://user-images.githubusercontent.com/7444140/213140436-340280aa-34b6-43dd-ab4e-19f9ffdce862.png)

`direnv` to manage signet, regtest, and testnet automatically via directories and environment variables.

## how to use

clone this repo and copy it over to a new directory:

```bash
git clone https://github.com/josibake/bendir.git 
cp bendir my-cool-project
```

make sure you have `direnv` installed. after `direnv` is installed, you may need to run `direnv allow` the first time you cd into the project directory and again after each time you change the `.envrc` file. alternatively, you can whitelist these directories in your direnv config so that they are always trusted (not recommended)

once you have `direnv` setup, either compile or download your preferred bitcoin client version and place the `bitcoind` and `bitcoin-cli` binaries in the `bin/` folder:

```bash
# replace this with whatever your bitcoin src directory is named
# or the location of the downloaded binaries
cp ~/bitcoin/src/bitcoind ~/my-cool-project/bin/
cp ~/bitcoin/src/bitcoin-cli ~/my-cool-project/bin/
```

after cd'ing into the directory, run:

```bash
init signet # can be one of mainnet, signet, testnet, regtest
bitcoind
```

you can now run `bitcoin-cli` commands. if you you want to switch networks, you can run `wipe`. this stops your node and resets the `BITCOIN_NETWORK` variable.

## adding additional aliases

if you want to add a new command, you can write your alias as a script and place it in the `aliases/` folder:

```bash
cat << EOF > aliases/my_cool_cmd
echo "my cool script!"
EOF

chmod +x aliases/my_cool_cmd
my_cool_cmd
```

