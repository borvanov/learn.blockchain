# Learn blockchain and NFT

## Getting Started

This guide gives you a few tips on learning blockchain and NFT concepts. Read the articles, clone an example application. Probably there is some otherissues could appear in your requirement - google them. But I hope that this list will help you to get started with the NFT.

## Table of contents

- [Blockchain](https://github.com/borvanov/learn.blockchain#blockchain)
- [NFT](https://github.com/borvanov/learn.blockchain#nft)
- [Examples](https://github.com/borvanov/learn.blockchain#examples)
- [Resources](https://github.com/borvanov/learn.blockchain#resources)

### Blockchain

First of all, you need to get familiar with the Blockchain itself. Smart contracts and NFT technologies are using blockchain under their hood, so the technology is definitely needs to be investigated.

Blockchain concept is well described in [Solidity documentation](https://docs.soliditylang.org/en/v0.8.4/introduction-to-smart-contracts.html#blockchain-basics).
To understand deeply how does it work you can write your own example in Node JS using [this article](https://itnext.io/writing-a-blockchain-in-node-js-cd3e903226cf).

### NFT

As as second step you need to understand what is NFT itself. Ethereum documentation covers the description by a [great article](https://ethereum.org/en/nft/).

Q: What is an NFT?
A: An NFT is an item stored on the blockchain. Every NFT is unique. Purchasing an NFT gives you the sole right to control that item. You can read more about it [here](https://ethereum.org/en/nft/#nft-use-cases).

Q: What is an NFT collectable?
A: Like an autographed baseball or a Super Bowl ring worn by Tom BradyElvis, an NFT can be collected and valued. It’s is a connection to a team or star. Protected by the technology itself -- the immutable nature of the blockchain digital ledger -- you know it is authentic.

### Ethereum

Ethereum is the community-run technology powering the cryptocurrency, ether (ETH) and thousands of decentralized applications. [documentation](https://ethereum.org/en/what-is-ethereum/).
At the moment Ethereum is the most powerful network that supports NFT concept and allows you to configure and use all the features related to it. Here is an [article](https://preethikasireddy.medium.com/how-does-ethereum-work-anyway-22d1df506369) that shows all the details of Ethereum implementation.

### Smart contracts

...WIP

## Deployment process for the contract

For the deployment we can use Truffle tools.

For the first, we need to configure `truffle-config.js` file. Go to the file and open _network_ section:

```
...
networks: {
  production: {
    provider: function() {
      return new HDWalletProvider(MNEMONIC, INFURA_NODE_HTTP_ADDRESS)
    },
    network_id: 11297108109,
    gas: 4000000,
  },
}
...
```

MNEMONIC is a secret phrase that MetaMask give you once you create new account. The secret phrase is used to identify the wallet from which we want to deploy the account.

INFURA_NODE_HTTP_ADDRESS is an http URL to node in Ethereum system where we want to deploy the contract.

To deploy to INFURA node you also need to specify a chain ID. This is something you can obtain using _getChainId_ method from _web3_ library.

Run the command:
`truffle deploy --network production`

Once the command is executed - the smart contract will be deployed to INFURA NODE using the information we provided in `truffle-config.js`.
