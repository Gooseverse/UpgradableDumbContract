# ERC-20 Token Dumb Contract Upgradable

This is a simple implementation of an ERC-20 token contract in rubidity(dumb contract). The contract is divided into three parts: storage, logic, and proxy, following best practices for modular contract design.

## Contracts

### ERC20Storage

- `name`: The name of the token.
- `symbol`: The symbol of the token.
- `decimals`: The number of decimals for token balances.
- `totalSupply`: The total supply of tokens.
- `balanceOf`: A mapping of addresses to their token balances.
- `allowance`: A mapping of allowances for token transfers.

### ERC20Logic

- Inherits from ERC20Storage.
- `constructor(name, symbol, decimals)`: Initializes the token contract with a name, symbol, and decimal places.
- `transfer(to, amount)`: Transfers tokens from the sender to the specified address.

### ERC20Proxy

- Inherits from ERC20Storage.
- `logicContracts`: A mapping of user addresses to logic contract addresses.
- `initialized`: A flag to track contract initialization.
- `initialize(name, symbol, decimals)`: Initializes the contract with the token's name, symbol, and decimals.
- `setLogicContract(logicContractAddress)`: Sets the logic contract address for the sender.
- `fallback()`: Forwards calls to the logic contract using delegatecall.

## Usage

1. Deploy an instance of ERC20Storage to store token data.
2. Deploy an instance of ERC20Logic, passing the name, symbol, and decimals as constructor arguments.
3. Deploy an instance of ERC20Proxy, setting the logic contract address using `setLogicContract`.
4. Users can interact with the ERC20 token by calling functions on the ERC20Proxy contract.

## Development

To get started with development and testing:

1. Clone this repository.
2. Install required dependencies.
3. Compile and deploy the contracts on a development blockchain.
4. Test the functionality of the ERC-20 token using Truffle or a similar testing framework.

## License

This ERC-20 token contract is open-source and available under the [MIT License](LICENSE).

Feel free to modify and use it as a basis for your own token contracts.
