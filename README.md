# KaseiCoin: ERC-20 Token Crowdsale

This repository contains `KaseiCoin` and `KaseiCoinCrowdsale` smart contracts. These are custom ERC20 tokens and associated crowdsale contracts developed using Solidity language and leveraging the OpenZeppelin libraries. The primary purpose of this repository is to provide a fundamental understanding of developing and deploying smart contracts on the Ethereum network.

### Table of Contents

- [Technologies](#technologies)
- [Installation](#installation)
- [Instructions](#instructions)
- [Contributors](#contributors)
- [License](#license)

### Technologies

The project incorporates the following technologies:

* [Solidity ^0.5.17](https://soliditylang.org/): Solidity is a statically-typed programming language designed for developing Ethereum smart contracts. It's Ethereum's native language, providing a secure and robust platform for blockchain developers.

* [OpenZeppelin](https://www.openzeppelin.com/): We leverage OpenZeppelin library for implementing secure and standardized contracts.

* [Remix IDE](https://remix-project.org/): A powerful, open-source tool used for writing Solidity contracts directly from a web browser. Remix IDE facilitates a connected and intuitive environment for developing, testing, and deploying your Solidity code.

* [MetaMask](https://metamask.io): Our gateway to the Ethereum blockchain, enabling us to interact with our smart contracts.


* [Ganache](https://trufflesuite.com/ganache/): A personal blockchain used for Ethereum development you can use to deploy contracts, develop applications, and run tests.

### Installation

Please follow the steps outlined below to deploy JointSavingsn smart contracton your local machine:

1. Install Ganache on your machine.
2. Install MetaMask in your browser.
3. Set up and connect MetaMask to your local Ethereum blockchain provided by Ganache.
4. Open Remix IDE in your preferred web browser.
5. Download the KaseiCoin.sol and KaseiCoinCrowdsale.sol files from this repository.
6. Upload the downloaded files into Remix IDE.
7. In Remix IDE, set the environment to `Web3 Provider` or `Injected Web3` in order to connect with Ganache (your local blockchain) or Metamask (your wallet), respectively.
8. Now you're set to compile and deploy the contract, and interact with it in the Remix IDE environment.

### Instructions

The project is divided into multiple sections: 

* Creating the KaseiCoin Token Contract
* KaseiCoin Crowdsale Contract
* KaseiCoin Deployer Contract
* Deploying the Crowdsale to a Local Blockchain
* Testing the Crowdsale Contract

Please follow the detailed step-by-step guide provided with screenshots showing the deployment and testing process.

#### Creating the KaseiCoin Token Contract

Our first step started with designing the KaseiCoin as an ERC20 token, which unfolded through the following steps:

1. The project begining involved importing the KaseiCoin.sol starter file into our development workspace, which is the Remix IDE.
2. To ensure `KaseiCoin` incorporated all necessary attributes of a standard ERC20 token, we drew from the OpenZeppelin library and imported the following fundamental contracts:

* ERC20
* ERC20Detailed
* ERC20Mintable

3. We then outlined a contract for our `KaseiCoin` token, setting it to inherit from the OpenZeppelin contracts mentioned earlier.
4. To add specifications to our token, we introduced a constructor within the `KaseiCoin` contract. This constructor held parameters for the token's `name`, `symbol`, and `initial_supply`.
5. Made sure to align with the ERC20 token standards by calling the `ERC20Detailed` contract's constructor from within our constructor definition, passing `name`, `symbol`, and `18` as parameters. Here, `18` was used to specify the decimal parameter value.
6. The contract was then compiled using the `0.5.17` compiler version.

Successful compilation of `KaseiCoin` contarct:

![compile_KaseiCoin](execution_results/compile_KaseiCoin.gif)

#### KaseiCoin Crowdsale Contract

After the successful creation of the KaseiCoin, we can contunue with building the crowdsale contract by performing the following steps:

1. Imported the `KaseiCoinCrowdsale.sol` starter code into our workspace in the Remix IDE.
2. Defined the new contract to inherit from the OpenZeppelin's `Crowdsale` and `MintedCrowdsale` contracts, ensuring a robust structure.
3. Within the `KaseiCoinCrowdsale` constructor, we added the parameters necessary for our crowdsale, including `rate`, `wallet`, and `token`.
4. After defining the essential features, the contract was compiled using the `0.5.17`

Successful compilation of `KaseiCoinCrowdsale` contarct:

![compile_KaseiCoinCrowdsale](execution_results/compile_KaseiCoinCrowdsale.gif)

#### KaseiCoin Deployer Contract

Having set up the KaseiCoin and Crowdsale contracts, our next objective was configuring the KaseiCoin Deployer Contract by performing the following steps:

1. Added variables within the `KaseiCoinCrowdsaleDeployer` contract to store the addresses of the `KaseiCoin` and `KaseiCoinCrowdsale` contracts.
2. Two public address variables, `kasei_token_address` and `kasei_crowdsale_address`, were defined.
3. The constructor for `KaseiCoinCrowdsaleDeployer` was enhanced with parameters `name`, `symbol`, and `wallet`.
4. We then implemented steps for creating the constructor body. New instance of the `KaseiCoin` token is instantiated with specific `name` and `symbol` parameters, and an `initial_supply` of zero. The address of this new token is stored in the `kasei_token_address` variable for future reference, marking the deployment of `KaseiCoin` token on the blockchain.
5. The contract was compiled using the 0.5.17

#### Deploying the Crowdsale to a Local Blockchain

Once the `KaseiCoinCrowdsaleDeployer` and associated contracts were ready, we deployed the crowdsale on a local blockchain:

1. The deployment process was initiated using Remix IDE, MetaMask, and Ganache to seamlessly interact with our local Ethereum blockchain.
2. Post-deployment, we verified the correctness of the deployment process and ensured that the crowdsale contract was functioning as expected on the local blockchain.

Successful deployment of `KaseiCoinCrowdsaleDeployer` contarct:

![deploy_KaseiCoinCrowdsaleDeployer](execution_results/deploy_KaseiCoinCrowdsaleDeployer.gif)

Linking contracts:

![link_contracts](execution_results/link_contracts.gif)



#### Testing the Crowdsale Contract

To ascertain the full functionality and accuracy of our KaseiCoin crowdsale contract, we executed the testing process:

1. The testing phase was started by using test accounts to simulate token purchase scenarios. This not only provided a practical demonstration of our contract's operations but also allowed us to observe any possible irregularities.
2. After performing multiple token purchases with our test accounts, we examined the balance of these accounts to verify the accuracy of transactions.
3. We inspected the total supply of minted tokens and evaluated the amount of wei raised through the crowdsale contract. This helped us confirm the successful operation of the crowdsale mechanism.

Successful purchases of the `KaseiCoin` token:

![buy_tokens](execution_results/buy_tokens.gif)


### Contributors

Alexander Likhachev

### License
MIT

