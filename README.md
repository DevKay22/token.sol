# Token
This contract is a simple "Token" contract that demostrates how to write a basic token contract using the solidity programming language.

## Description
This contract is a simple token contract written in solidity, an object-oriented programming language widely used in the development of smart contracts aimed at targeting the Ethereum Virtual Machine. The contract has three state variables: i. the token name, ii. the abbreviated token name, and iii. the total supply. Also, the contract contains two functions; one for minting the token and the other for burning the token.

## Getting Started
### Executing Program
To run this program, you can use Remix, an online Solidity IDE. To get started, go to the Remix website at https://remix.ethereum.org/.

Once you are on the Remix website, create a new file by clicking on the "+" icon in the left-hand sidebar. Save the file with a .sol extension (e.g., MyToken.sol). Copy and paste the following code into the file:

pragma solidity ^0.8.10;

contract MyToken{ //public variables here string public tokenName = "KAYODE"; string public tokenAbbrv = "KAY"; uint public totalSupply = 0;

//mapping variable here
mapping (address=>uint) public balances;

//mint function
function mint (address _address, uint _value) public {
    totalSupply += _value;
    balances[_address] += _value;
} 

//burn function
function burn (address _address, uint _value) public {
    if (balances[_address] >= _value) {
        totalSupply -= _value;
        balances[_address] -= _value; 
    }
}
}

### Interacting with the code
To compile the code, click on the "Solidity Compiler" tab in the left-hand sidebar. Make sure the "Compiler" option is set to "0.8.4" (or another compatible version), and then click on the "Compile Token.sol" button.

Once the code is compiled, you can deploy the contract by clicking on the "Deploy & Run Transactions" tab in the left-hand sidebar. Select the "MyToken" contract from the dropdown menu, and then click on the "Deploy" button.

Once the contract is deployed, you can interact with the contract by first copying and pasting the address you want to use, then click on the mint function below. Paste the address and enter the value of tokens you want to mint. Cick on the "balances" button and paste the address there also. Click on the "balances" button to check the balance you have. To burn some tokens, click on the "burn" function and enter the value of tokens you want to burn which should be less than or equal to the total value of tokens you have.

## License
This project is licensed under the MIT License.