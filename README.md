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

![buy_tokens(execution_results/buy_tokens.gif)


### Contributors

Alexander Likhachev

### License
MIT











### Instructions

The steps for this Challenge are divided into the following sections:

1. Create the KaseiCoin Token Contract

2. Create the KaseiCoin Crowdsale Contract

3. Create the KaseiCoin Deployer Contract

4. Deploy the Crowdsale to a Local Blockchain

5. Optional: Extend the Crowdsale Contract by Using OpenZeppelin

#### Create the KaseiCoin Token Contract

In this section, you will create a smart contract that defines KaseiCoin as an ERC-20 token. To do so, complete the following steps:

1. Import the provided `KaseiCoin.sol` starter file into the Remix IDE.

2. Import the following contracts from the OpenZeppelin library:

    * `ERC20`

    * `ERC20Detailed`

    * `ERC20Mintable`

3. Define a contract for the KaseiCoin token called `KaseiCoin`, and have the contract inherit the three contracts that you just imported from OpenZeppelin.

4. Inside of your `KaseiCoin` contract, add a constructor with the following parameters: `name`, `symbol`, and `initial_supply`.

5. Then, as part of your constructor definition, add a call to the `ERC20Detailed` contract’s constructor, passing the parameters `name`, `symbol`, and `18`. Recall that 18 is the value for the `decimal` parameter.


6. Compile the contract using compiler version 0.5.0.

7. Check for any errors and debug as needed.

8. Take a screenshot of the successful compilation of the contract, and add it to the Evaluation Evidence section of the `README.md` file for your Challenge repository.

#### Create the KaseiCoin Crowdsale Contract

In this section, you will define the KaseiCoin crowdsale contract. To do so, complete the following steps:

1. Import the provided `KaseiCoinCrowdsale.sol` starter code into the Remix IDE.

2. Have this contract inherit the following OpenZeppelin contracts:

* `Crowdsale`

* `MintedCrowdsale`

3. Within the `KaisenCoinCrowdsale` constructor, provide parameters for all of the features of your crowdsale, such as `rate`, `wallet` (where the funds that the token raises should be deposited), and `token`. Configure these parameters as you see fit for your KaseiCoin token.

4. Compile the contract using compiler version 0.5.0.

5. Check for any errors and debug as needed.

6. Take a screenshot of the successful compilation of the contract, and add it to the Evaluation Evidence section of the `README.md` file for your Challenge repository.

#### Create the KaseiCoin Deployer Contract


In this section, you will create the KaseiCoin deployer contract. Start by uncommenting the `KaseiCoinCrowdsaleDeployer` contract in the provided `KaseiCoinCrowdsale.sol` starter code.

Next, within the `KaseiCoinCrowdsaleDeployer` contract, add variables to store the addresses of the `KaseiCoin` and `KaseiCoinCrowdsale` contracts, which this contract will deploy. To do so, complete the following steps:

1. Create an `address public` variable called `kasei_token_address`, which will store `KaseiCoin`’s address once that contract has been deployed.

2. Create an `address public` variable called `kasei_crowdsale_address`, which will store `KaseiCoinCrowdsale`'s address once that contract has been deployed.

3. Add the following parameters to the constructor for the `KaseiCoinCrowdsaleDeployer` contract: `name`, `symbol`, and `wallet`.

4. Inside of the constructor body (between the curly braces), complete the following steps:

    * Create a new instance of the `KaseiCoinToken` contract.

    * Assign the KaseiCoin token contract’s address to the `kasei_token_address` variable. This will allow you to easily fetch the token's address later.

    * Create a new instance of the `KaseiCoinCrowdsale` contract using the following parameters:

       * `rate` (Set `rate` equal to 1 in order to maintain parity with ether.)

       * `wallet` (Pass `wallet` in from the main constructor. This is the wallet that will get paid all of the ether raised by the crowdsale contract.)

       * `token` (This should be the `token` variable where `KaseiCoin` is stored.)

    * Assign the KaseiCoin crowdsale contract’s address to the `kasei_crowdsale_address` variable. This will allow you to easily fetch the crowdsale’s address later.

    * Set the `KaseiCoinCrowdsale` contract as a minter.

    * Have the `KaseiCoinCrowdsaleDeployer` renounce its minter role.

5. Compile the contract using compiler version 0.5.0.

6. Check for any errors and debug as needed.

7. Take a screenshot of the successful compilation of the contract, and add it to the Evaluation Evidence section of the `README.md` file for your Challenge repository.

#### Deploy the Crowdsale to a Local Blockchain

In this section, you will deploy the crowdsale to a local blockchain using Remix, MetaMask, and Ganache. To do so, complete the following steps. Record a short video or take screenshots that illustrate the three steps outlined below as evidence of your deployed crowdsale contract.


1. Deploy the crowdsale to a local blockchain with Remix, MetaMask, and Ganache.

2. Test the functionality of the crowdsale by using test accounts to buy new tokens and then checking the balances associated with those accounts.

3. After purchasing tokens with one or more test accounts, view the total supply of minted tokens and the amount of wei that has been raised in the crowdsale contract.

#### Optional: Extend the Crowdsale Contract by Using OpenZeppelin

In this **optional** section, you may extend the crowdsale contract to enhance its functionality. To do so, you will use the following OpenZeppelin contracts:

* `CappedCrowdsale`: This contract allows you to cap the total amount of ether that may be raised during your crowdsale.

* `TimedCrowdsale`: This contract allows you to set a time limit for your crowdsale by adding an opening time and a closing time.

* `RefundablePostDeliveryCrowdsale`: Every time you launch a crowdsale, you set a goal amount of ether to raise. If the goal is not reached, it is common practice to refund your investors. This contract adds this capability to a crowdsale.

> **Hint** We encourage you to read more about these contracts on the [Crowdsales page](https://docs.openzeppelin.com/contracts/2.x/crowdsales) of the OpenZeppelin documentation.

To enhance your KaseiCoin crowdsale with this added functionality, complete the following steps:

1. Import the three OpenZeppelin contracts described above into the `KaseiCoinCrowdsale.sol` contract by using the following code:

    ```solidity
    import "https://github.com/OpenZeppelin/openzeppelin-contracts/blob/release-v2.5.0/contracts/crowdsale/validation/CappedCrowdsale.sol";
    import "https://github.com/OpenZeppelin/openzeppelin-contracts/blob/release-v2.5.0/contracts/crowdsale/validation/TimedCrowdsale.sol";
    import "https://github.com/OpenZeppelin/openzeppelin-contracts/blob/release-v2.5.0/contracts/crowdsale/distribution/RefundablePostDeliveryCrowdsale.sol";
    ```

2. In addition to the `Crowdsale` and `MintedCrowdsale` contracts, which your contract previously inherited from OpenZeppelin, have your `KaseiCoinCrowdsale` contract inherit the three contracts that you imported in the previous step:

* `CappedCrowdsale`

* `TimedCrowdsale`

* `RefundablePostDeliveryCrowdsale`

3. In the `KaseiCoinCrowdsale` constructor, add the following new parameters:

    * `uint goal`: This variable will represent the amount of ether which you hope to raise during the crowdsale&mdash;the crowdsale’s goal.

    * `uint open`: This variable will represent the opening time for the crowdsale.

    * `uint close`: This variable will represent the closing time for the crowdsale.

4. Complete the `KaseiCoinCrowdsale` constructor code by adding calls to the new contracts, as the following code shows:

    ```solidity
    constructor(
            uint256 rate, // rate in TKNbits
            address payable wallet, // sale beneficiary
            KaseiCoin token, // the KaseiCoin itself that the KaseiCoinCrowdsale will work with
            uint goal, // the crowdsale goal
            uint open, // the crowdsale opening time
            uint close // the crowdsale closing time
        ) public
            Crowdsale(rate, wallet, token)
            CappedCrowdsale(goal)
            TimedCrowdsale(open, close)
            RefundableCrowdsale(goal)
        {
            // constructor can stay empty
        }
    ```

    > **Important** `RefundablePostDeliveryCrowdsale` itself inherits the `RefundableCrowdsale` contract, which requires a `goal` parameter. So, in addition to the others, you must call the `RefundableCrowdsale` constructor from your `KaseiCoinCrowdsale` constructor. `RefundablePostDeliveryCrowdsale` does not have its own constructor, which is why we use the `RefundableCrowdsale` constructor that it inherits.
    >
    > If you forget to call the `RefundableCrowdsale` constructor, the `RefundablePostDeliveryCrowdsale` will fail. This is because it does not have its own constructor, and so it relies on the `RefundableCrowdsale` constructor.

5. Next, update the `KaseiCoinCrowdsaleDeployer` contract to allow the deployment of the updated crowdsale contract. In the constructor of the deployer contract, add a new `uint` parameter called `goal` that will allow you to set the crowdsale goal.

6. In the core assignment, you added an instance of the `KaseiCoinCrowdsale` contract to the KaseiCoin deployer contract. Since we have modified the `KaseiCoinCrowdsale` contract to support new functionality, you must now update your previous code with the following code:

    ```solidity
    KaseiCoinCrowdsale kasei_crowdsale = new KaseiCoinCrowdsale (1, wallet, token, goal, now, now + 24 weeks);
    ```

   Note that in the preceding code, you added values for the three new parameters. The `goal` parameter represents the amount of ether to raise during the crowdsale, `now` represents the crowdsale opening time, and `now + 24 weeks` represents the closing time.

    The `now` function returns the current Ethereum block timestamp in the form of seconds since the Unix epoch. The **Unix epoch** (also known as **Unix time**, **POSIX time**, or **Unix timestamp**) is an integer that represents the number of seconds that have elapsed since January 1, 1970 (midnight UTC/GMT), not counting leap seconds.

7. Compile and test the updated contract by completing following steps:

    * Send ether to the crowdsale from a different account (**not** the same account that is raising funds). Then, once you confirm that the crowdsale works as expected, try to add the token to your wallet and test a transaction.

    * You can set the `close` time to be `now + 5 minutes`, or any timeline that you'd like to test, for a shorter crowdsale.

    * When sending ether to the contract, make sure that you meet the contract’s `goal`. Then, finalize the sale using the `Crowdsale` contract's `finalize` function. To finalize the sale, `isOpen` must return false (`isOpen` comes from `TimedCrowdsale` and checks to see whether the `close` time has passed yet). If you set the `goal` to 300 ether, for example, you may need to purchase tokens from multiple accounts in order to meet the goal. If you run out of pre-funded accounts in Ganache, you can create a new workspace.

    * View your tokens in MetaMask. In MetaMask, click Add Token, then click Custom Token,  and enter the token contract’s address. Make sure to purchase higher amounts of tokens in order to see the denomination appear in your wallet as more than a few wei worth.
