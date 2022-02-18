# polkadot_npm
This package allow user to create wallet, check balance, transaction, encoding and decoding in polkadot blockchain

Polkadot is a next-generation blockchain protocol connecting multiple specialized blockchains into one unified network. Designed as part of a broad vision for a web that returns control to individuals over internet monopolies, Polkadot builds on the revolutionary promise of previous blockchain networks while offering several fundamental advantages.

```sh 
npm  install polkadot_npm 
```

Connect to the polkadot blockchain

```sh
const {connect } = require("polkadot_npm")

const connection=async()=>{

 const testConnection = await connect();
 
 console.log(`Network connection is ready ${testConnection.isConnected}`)

}
```

Create Account on Polkadot with polkadot address which start with 1

```sh
const {getPolkaAddress } = require("polkadot_npm")

const createAccount=async()=>{

 const wallet = await getPolkaAddress();
 
 console.log(`wallet details`,wallet.address)
 console.log(`wallet details`,wallet)

}
```


Create Account on Polkadot with Kusama address which start with C, D, E, F capital letters

```sh
const {getKusamaAddress } = require("polkadot_npm")

const createAccount=async()=>{

 const wallet = await getKusamaAddress();
 
 console.log(`wallet details`,wallet.address)
 console.log(`wallet details`,wallet)

}
```


Create Account on Polkadot with generic address which start with 5

```sh
const {generateGenericAddress } = require("polkadot_npm")

const createAccount=async()=>{

 const wallet = await generateGenericAddress();
 
 console.log(`wallet details`,wallet.address)
 console.log(`wallet details`,wallet)

}
```

Generate account details with seed 

```sh

const {importPrivateKey } = require("polkadot_npm")

const importAccount=async()=>{

const seed = "exotic ski jazz network mobile unit subway slim rebel garbage milk fringe"

 const wallet = await importPrivateKey(seed);
 
 console.log(`wallet details`,wallet.address)
 console.log(`wallet details`,wallet)

}
```

Get wallet Balance 

```sh

const {getBalance } = require("polkadot_npm")

const getAccountBalance=async()=>{

const address = "14akjYCdTjvnPN7cVgZ14qManYAPQfZutKtFSeFT2cbNqw1H"

 const balance = await getBalance(address);
 
 console.log(`Wallet Balance :`,balance)

}
```

Decode address 

```sh

const {decryption } = require("polkadot_npm")

const decode=async()=>{

const address = "14akjYCdTjvnPN7cVgZ14qManYAPQfZutKtFSeFT2cbNqw1H"

 const decodedAddress = await decryption(address);
 
 console.log(`decoded Address :`,decodedAddress)

}
```

Encode address 

```sh

const {encryption } = require("polkadot_npm")

const encode=async()=>{

const publicKey = [
  128, 107,  30,  17,  65,  79,  76, 203,
    6, 101,  52,  16, 255, 212,  81, 108,
  241, 151, 219, 102, 213,  11, 181, 203,
  119, 209,  74,  73,  37, 179, 226,   4
]

 const encodeAddress = await encryption(publicKey);
 
 console.log(`Encode Address :`,encodeAddress)

}
```

Transfer balance 

```sh

const {createPolkaTrx } = require("polkadot_npm")

const transaction=async()=>{

const senderSeed = "exotic ski jazz network mobile unit subway slim rebel garbage milk fringe"

const receiverAddress = "14akjYCdTjvnPN7cVgZ14qManYAPQfZutKtFSeFT2cbNqw1H"

const amount=0.1

 const transactionId = await createPolkaTrx(senderSeed,receiverAddress,amount);
 
 console.log(`transaction Id :`,transactionId)

}
```
