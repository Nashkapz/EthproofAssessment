# Kapzeum Token

This program demonstrates the basic syntax and functionality of creating a token using the Solidity programming language. The purpose of this program is to understand the basic requirements of token i.e. it's name, abbreviation and two important functionalities which are minting token to add new token in the current flow of blockchain and burn function to remove the token from the blockchain.

## Description

In this program we build a contract named MyToken in which we created a token and described it's name and abbreviation and total supply provided and then mapped the address to the value as balance. After that we minted the tokens and added the value to total supply and to the balance of the addresss. Atlast we created a function named burn which deducts the the value from total supply as well as the balance if and only if the value is less than or equal to the balance.

## Getting Started

### Executing program

To run this program, we can use Remix, an online Solidity IDE. To get started, go to the Remix website at https://remix.ethereum.org/.

Once you are on the Remix website, create a new file by clicking on the "+" icon in the left-hand sidebar. Save the file with a .sol extension (e.g., Kapzeum.sol). Copy and paste the following code into the file:

```solidity
// SPDX-License-Identifier: MIT
pragma solidity 0.8.18;

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
    string public TokenName = "Kapzeum";
    string public TokenAbbrev = "Kzee";
    uint public TotalSupply = 0;
    // mapping variable here
    mapping(address=>uint) public balances;
    // mint function
    function mint(address _address,uint _value) public{
        TotalSupply += _value;
        balances[_address] += _value;
    }
    // burn function
    function burn(address _address,uint _value) public{
        if(balances[_address] >= _value){
            TotalSupply -= _value;
            balances[_address] -= _value;
        }
    }
}

```

To compile the code, click on the "Solidity Compiler" tab in the left-hand sidebar. Make sure the "Compiler" option is set to "0.8.18" (or another compatible version), and then click on the "Compile Kapzeum.sol" button.

Once the code is compiled, you can deploy the contract by clicking on the "Deploy & Run Transactions" tab in the left-hand sidebar. Select the "MyToken" contract from the dropdown menu, and then click on the "Deploy" button.

Once the contract is deployed, you can interact with it by calling the "mint" and "burn" functions and retrieving the values of total supply as well as the balance amount in the given address. Click on the "MyToken" contract in the left-hand sidebar, and then click on the "mint" function and add the proper arguments. Finally, click on the "transact" button to execute the function and adding balance to the total supply and the given address. We can also interact with the "burn" function and remove the amount from total supply and the given balance. We can also interact with the variables such as total supply and balance(mapped to a given address) and retrieve their values as well.

For detailed explanation you can also visit my loom link given below:
https://www.loom.com/share/be160f6acfc3405c8d2fb540b251b32b?sid=8c066c38-fa85-4ae1-81fd-b5013b8628f5
