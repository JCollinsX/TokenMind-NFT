### Running this project

#### Local setup

To run this project locally, follow these steps.

1. Start the local Hardhat node

```sh
npx hardhat node
```

2. With the network running, deploy the contracts to the local network in a separate terminal window

```sh
npx hardhat run scripts/deploy.js --network localhost
```

### Configuration

To deploy to Polygon test or main networks, update the configurations located in __hardhat.config.js__ to use a private key and, optionally, deploy to a private RPC like Infura.

```javascript
require("@nomiclabs/hardhat-waffle");
const fs = require('fs');
const privateKey = fs.readFileSync(".secret").toString().trim() || "01234567890123456789";

// infuraId is optional if you are using Infura RPC
const infuraId = fs.readFileSync(".infuraid").toString().trim() || "";

module.exports = {
  defaultNetwork: "hardhat",
  networks: {
    hardhat: {
      chainId: 1337
    },
    mumbai: {
      // Infura
      // url: `https://polygon-mumbai.infura.io/v3/${infuraId}`
      url: "https://rpc-mumbai.matic.today",
      accounts: [privateKey]
    },
    matic: {
      // Infura
      // url: `https://polygon-mainnet.infura.io/v3/${infuraId}`,
      url: "https://rpc-mainnet.maticvigil.com",
      accounts: [privateKey]
    }
  },
  solidity: {
    version: "0.8.4",
    settings: {
      optimizer: {
        enabled: true,
        runs: 200
      }
    }
  }
};
```

If using Infura, update __.infuraid__ with your [Infura](https://infura.io/) project ID.


## Deployed Contract address

### Rinkeby Testnet
NFT token Contract
```sh
https://rinkeby.etherscan.io/address/0xAb88A6dbB32C49a303cdAe0dcDE1B37A69b7E9C9
```

NFT marketplace Contract
```sh
https://rinkeby.etherscan.io/address/0x2396Ba8C4CF9F00b0F5C82f85E7bA2fBeF1b6Fca
```

### Ropsten Testnet

NFT token Contract
```sh
https://ropsten.etherscan.io/address/0xE6a79C34D5b10a2601EeC9C00EaDB441ed287230#code
```

NFT marketplace Contract
```sh
https://ropsten.etherscan.io/address/0xE27E5148a328e7614a1836e6E4CA7a9efC95ECA9#code