# Lesson 9 in Patrick's course

In this lesson we made a decentralized automated raffle using chainlink VRF and Keepers

Some take aways:

- Install `yarn add dev hardhat-shorthand`. Now you can run `hh compile` instead of `yarn hardhat compile`... what a relief.
- We modify our contract to request random numbers from chainlink VRF.

- I learned the differences between s_variables, i_variables and variables used in functions.

- currentBalance of a contract is a uint256.

- calldata doesnt work with strings.

- Basically when making a dapp you have to:
  1. Writte the contract and make sure it compiles.
  2. Deploy to a local testnet or to rinkeby and see how it goes. A basic script for deploy would be:

```javascript
const { getNamedAccounts, deployments, network, ethers } = require('hardhat')

module.exports = async ({ getNamedAccounts, deployments }) => {
  const { deploy, log } = deployments
  const { deployer } = await getNamedAccounts()

  await deploy('NameOfContract', {
    from: deployer,
    log: true,
    args: [],
  })
}

module.exports.tags = ['all']
```

- The helper-hardhat-config.js can be used to set some constructor parameters when deploying. Nice.

- The order of the parameters in the constructor is important when you are passing them in tests.

- contract.callStatic.yourFunction() simulates a transaction.
- contract.once -> listen for events.

- Staging tests are for testing in testnets like Rinkeby.

- Contract address of this raffle in Rinkeby -> 0x8B3cd113C919272969b211a935c5d2B6410dB235

**really nice! Patrick is awesome!**
