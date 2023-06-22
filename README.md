# Create a Token

The program provided is an example of a smart contract written in Solidity.The purpose of this program is to create a basic token contract with functionalities for minting and burning tokens. Minting means adding some token and burning means decreasing some amount of token.

## Description

This program is a simple contract written in Solidity, a programming language used for developing smart contracts on the Ethereum blockchain. The contract has a two functions mint and burn. Mint is use for adding some tokens and Burn is use for subtracting some token. By implementing all the components in our smart contract, we can manage the token details, track token balances for different addresses, mint new tokens, and burn existing tokens while maintaining appropriate checks and balances to ensure the integrity of the token system.

## Getting Started

### Executing program

To run this program, we have used Remix, an online Solidity IDE. To get started, go to the Remix website at https://remix.ethereum.org/.

Once you are on the Remix website, create a new file by clicking on the "+" icon in the left-hand sidebar. Save the file with a .sol extension (e.g., ethproof.sol). Copy and paste the following code into the file:

```javascript
// SPDX-License-Identifier: MIT
pragma solidity 0.8.18;

contract MyToken {

    // public variables here
    string public tokenName;
    string public tokenAbbrv;
    uint public totalSupply;
    // mapping variable here
     mapping(address => uint) public balances;

    constructor(string memory name, string memory abbrv, uint supply) {
        tokenName = name;
        tokenAbbrv = abbrv;
        totalSupply = supply;
        balances[msg.sender] = supply;
    }
    // mint function
         function mint(address account, uint value) public {
        totalSupply += value;
        balances[account] += value;
    }
    // burn function
       
    function burn(address account, uint value) public {
        require(balances[account] >= value, "Insufficient balance");

        totalSupply -= value;
        balances[account] -= value;
    }
}
```

To compile the code, click on the "Solidity Compiler" tab in the left-hand sidebar. Make sure the "Compiler" option is set to "0.8.4" (or another compatible version), and then click on the "Compile ethproof.sol" button.

Once the code is compiled, you can deploy the contract by clicking on the "Deploy & Run Transactions" tab in the left-hand sidebar. Select the "ethproof" contract from the dropdown menu, and then click on the "Deploy" button.

Once the contract is deployed, you can interact with it by intializing the variables and calling the mint and burn function function. First give the token name then abbrivation and totalsupply and click on the "transact" contract in the left-hand sidebar, and then click on the totalsupply to see the total supply, tokenName for token name and tokenabbrv for abbriviation and put the address and value in the "mint" and "burn" function and deploy the contract. 


## Authors

Navneet Shahi 



## License

This project is licensed under the MIT License. You are free to modify and distribute the code for personal and educational purposes.
