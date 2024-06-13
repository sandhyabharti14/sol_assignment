# MyToken Smart Contract

This Solidity smart contract defines a simple token with minting and burning functionality. The contract includes public variables to store token details, a mapping to manage balances, and functions to mint and burn tokens.


## Description
This program is a simple contract written in Solidity, a programming language used for developing smart contracts on the Ethereum blockchain.It allows for the creation (minting) and destruction (burning) of tokens, while maintaining an accurate record of token balances and total supply.
## Getting Started
## Executing Program
To run this program, you can use Remix, an online Solidity IDE. To get started, go to the Remix website at https://remix.ethereum.org/.

Once you are on the Remix website, create a new file by clicking on the "+" icon in the left-hand sidebar. Save the file with a .sol extension (e.g., Assesment.sol). Copy and paste the following code into the file:




     bash
        // SPDX-License-Identifier: MIT
        pragma solidity ^0.8.0;


    /*
       REQUIREMENTS
    1. Your contract will have public variables that store the details about your coin (Token Name, Token Abbrv., Total Supply)
    2. Your contract will have a mapping of addresses to balances (address => uint)
    3. You will have a mint function that takes two parameters: an address and a value. 
       The function then increases the total supply by that number and increases the balance 
       of the “sender” address by that amount
    4. Your contract will have a burn function, which works the opposite of the mint function, as it will destroy tokens. 
       It will take an address and value just like the mint functions. It will then deduct the value from the total supply 
       and from the balance of the “sender”.
    5. Lastly, your burn function should have conditionals to make sure the balance of "sender" is greater than or equal 
       to the amount that is supposed to be burned.
    */

    contract MyToken {
  
    // public variables here
    string public tokenname = "METACRAFTERS";
    string public tokenabbrv ="MCS";
    uint public totalsupply =0;
    // mapping variable here
    mapping(address => uint) public balances;
    // mint function
    function mint (address _add,uint _val) public{
        totalsupply += _val;
        balances[_add] += _val;      
    }
    // burn function
    function burn (address _add,uint _val) public{
        if (balances[_add]>=_val){
            totalsupply -= _val;
            balances[_add] -= _val;

          }
       }
    }






To compile the code, click on the "Solidity Compiler" tab in the left-hand sidebar. Make sure the "Compiler" option is set to "0.8.0" (or another compatible version), and then click on the "Compile Assesment.sol" button.

To compile the code, click on the "Solidity Compiler" tab in the left-hand sidebar. Make sure the "Compiler" option is set to "0.8.0" (or another compatible version), and then click on the "Compile Assesment.sol" button.

Once the code is compiled, you can deploy the contract by clicking on the "Deploy & Run Transactions" tab in the left-hand sidebar. Select the "Assesment" contract from the dropdown menu, and then click on the "Deploy" button.MetaMask will prompt you to confirm the transaction. Confirm the transaction to deploy the contract.

In the "Deployed Contracts" section, expand the MyToken contract.
Under the "mint" function, enter the address to receive tokens and the amount of tokens to mint.Click the "transact" button next to the mint function.Confirm the transaction in MetaMask.

Under the "burn" function, enter the address from which tokens should be burned (your MetaMask address) and the amount of tokens to burn.Click the "transact" button next to the burn function.Confirm the transaction in MetaMask.

Under the "balances" function, enter an address to check its token balance.Click the "call" button to retrieve the balance.

Under the totalsupply variable, click the "totalsupply" button to retrieve the total supply of tokens.


## Authors

- Sandhya Bharti
bhartisandhya1411@gmail.com



## License

This project is licensed under [MIT](https://choosealicense.com/licenses/mit/) License - see the LICENSE.md file for details
