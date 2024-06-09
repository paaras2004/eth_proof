
# Token minter and burner

This project is a Solidity-based smart contract designed to manage a custom token. The contract includes essential features such as minting new tokens, burning existing tokens, and storing key details about the token, including its name, abbreviation, and total supply.

## Description

This project is a solidity based contract will fullfill certain requirements.

 REQUIREMENTS
1. This contract will have public variables that store the details about your coin (Token Name, Token Abbrv., Total Supply)

2. This contract will have a mapping of addresses to balances (address => uint)

3. It will have a mint function that takes two parameters: an address and a value. The function then increases the total supply by that number and increases the balance 
of the “sender” address by that amount

4. This contract will have a burn function, which works the opposite of the mint function, as it will destroy tokens. 
It will take an address and value just like the mint functions. It will then deduct the value from the total supply and from the balance of the “sender”.

5. Lastly, burn function will have conditions to make sure the balance of "sender" is greater than or equal 
to the amount that is supposed to be burned.

## Getting Started
### Executing program
To run this program, you can use Remix, an online Solidity IDE. To get started, go to the Remix website at https://remix.ethereum.org/.

Once you are on the Remix website, create a new file by clicking on the "+" icon in the left-hand sidebar. Save the file with a .sol extension (e.g., assessment2.sol). Copy and paste the following code into the file:
```javascript


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
   string public token_name = "mine";
   string public token_abr="mi";
   uint public TotalSupply=0;

   mapping(address=>uint) public balance;
   function mint(address _address,uint value) public{
      //mapping use kr skta hu mai yha to map adresses to values and also update it 
      balance[_address]+=value;
      
      TotalSupply+=value;

   }
   function burn(address _address,uint value) public{
      if(balance[_address]>=value){
         balance[_address]-=value;
         TotalSupply-=value;
      }
      

   }


    // public variables here

    // mapping variable here

    // mint function

    // burn function

}

```

To compile the code, click on the "Solidity Compiler" tab in the left-hand sidebar. Make sure the "Compiler" option is set to "0.8.18" (or another compatible version), and then click on the "Compile assessment2.sol" button.

Once the code is compiled, you can deploy the contract by clicking on the "Deploy & Run Transactions" tab in the left-hand sidebar. Select the "assessment2" contract from the dropdown menu, and then click on the "Deploy" button.

Once the contract is deployed, you can interact with it . you will scroll down till you see name of your contract and then click on the downwards arrow the you will be provided with many fuction box like burn (to burn token), mint(to mint token), balance(to check balance on account) in these you can provide the given parameters like in mint provide the address, value you want to add then click transact ,it will mint the given ammount value to the provided address . you can also check token_abr,token_name, total_supply.

## Authors
Paaras

## License

This project is licensed under the MIT License - see the LICENSE.md file for details

