# BitcoinX nodejs-server-exit mod

check you have nodejs 0.10.x:

```
$ node --version
v0.10.3
```

If not, find package for your system or proceed to http://nodejs.org/download/

Installing the server (a bit convoluted to be able edit things in-place):

```
cd node-leveldb
git checkout dev/update_0.10
npm install coffee-script
cd ../bitcoinjs-server
npm install ../node-leveldb
npm install .
cd ../node-bitcoin-exit
mkdir node_modules
ln -s ../../bitcoinjs-server node_modules/bitcoinjs
ln -s ../bitcoinjs-gui public
npm install .
node server.js --bchdbg --testnet
```

Add to ```~/.bitcoinjs/testnet/settings.js```:

```cfg.verifyScripts = false; ```

(Bitcoinjs is not capable enough to verify odd testnet scripts).


