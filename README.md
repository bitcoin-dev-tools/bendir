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

once you have `direnv` setup, either compile or download your preferred bitcoin client version and place the `bitcoind` and `bitcoin-cli` binaries in the `bin/` folder. after cd'ing into the directory, you can run `bitcoind`, `bitcoin-cli` directly and they will run on the appropriate network.

## adding additional aliases

if you want to add a new command, you can write your alias as a script and place it in the `aliases/` folder.
