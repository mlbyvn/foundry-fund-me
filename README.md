# FundMe

Project purpose is to get acquainted with foundry, Chainlink price feeds, deploying to SepoliaETH testnet (or to the mainnet), some code optimization and testing. It is a part of a Cyfrin Updraft course, which [could be found here](https://updraft.cyfrin.io/courses/foundry).

## Description

Functionality: 
* FundMe.sol:
    * function fund(): allows to fund the contract with some ETH (more than minimum allowed amount MINIMUM_USD). A funder is added to the list of all funders. 
    * function getVersion(): returns the price feed version.
    * function withdraw(): allows the contract owner to withdraw funds. 
    * getter functions.
* PriceConverter.sol:
    * function getPrice(AggregatorV3Interface priceFeed): returns ETH/USD rate for Sepolia testnet in 18 digit.
    * function function getConversionRate(uint256 ethAmount, AggregatorV3Interface priceFeed): returns the actual SepoliaETH/USD conversion rate.

## Getting Started

### Dependencies

* [foundry](https://github.com/foundry-rs) 
* Sepolia node on [Alchemy](https://dashboard.alchemy.com/)
* [Etherscan](https://etherscan.io/) api (optional)

### Installing

* How/where to download your program
* Add an .env file, in order to be able to deploy on sepolia using makefile
    * SEPOLIA_RPC_URL: sepolia rpc url (possibly node on Alchemy)
    * MAINNET_RPC_URL: mainnet rpc url
    * ETHERSCAN_API_KEY: etherscan api key
    * ACCOUNT_NAME: pre-setup account (cast wallet import)
    * SENDER: address of ACCOUNT_NAME

### Executing program

* Build:
```
make build
```
* Tests on anvil:
```
forge test
```
* Tests on sepolia:
```
forge test --fork-url $SEPOLIA_RPC_URL
```
* Deploy on sepolia:
```
make deploy-sepolia
```

## Authors

Aleksandr Rybin  

## Version History

* 0.1
    * Initial Release
