
# BoritoJK_SolidityAssessment
A Basic Solidity Program which using a basic handling of Mint, Burn, checking available balance or your current token supply.

## Description
A Simple Program, In Which I Discuss My Written Solidity Program. Solidity is basically used for implementing Ethereum-based smart contracts. The contract token consists of using Mint (to create a token), Burn (to subtract a token), and lastly, checking your current balance. This is a simple program to start with, and it's basically straightforward for this type of introduction. 

## Getting Started
### Executing Program
To use this code use the online IDE that i currently using for testing solidity program, To get started, go to the Remix website at https://remix.ethereum.org/.

once you access the IDE create a new file or create a new workspace and go to contracts after open the file create a file with a template of ("title"+.sol) and save after that you follow this steps use this code below:


```
// SPDX-License-Identifier: MIT
pragma solidity >=0.8.26;

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
contract MyToken  {
      
      // public variables here
  string public tokenName = "GrandTurismoRacing";
  string public tokenAbbrv = "GTR";
  uint public totalSupply = 0;
      
      //mapping variable here
  mapping(address => uint) public balances;

      // mint function
  function mint (address _address, uint _value) public {
    totalSupply += _value;
    balances[_address] +=_value;
  }
      // burn function
    function burn (address _address, uint _value) public{
      if (balances[_address] >= _value) {
        totalSupply -= _value;
        balances[_address] -= _value;
    }
  } 
}
```

### Compile
to compile this program, click on the "Solidity Compiler" tab in the left-hand sidebar. Make sure the "Compiler"  select the current license that the the code has been currenly use which put on the option and set it to 0.8.26 (or for the current compatible version)and then click on the "Compile Name_Token.sol" and click the auto compile box to be check and click compile or use this short cut keys(Ctrl+S) to easy compile.

You may deploy the contract by selecting the "Deploy & Run Transactions" button from the left-hand sidebar once the code has been built. After choosing "MyToken - Name_Token.sol" from the drop-down menu, press the "Deploy" button.

To interact with a deployed contract, use the functions mint, burn, tokenAbbrv, tokenName, and totalSupply. First, find your account address with an unlimited amount of tokens in "Deploy and run transactions". In "Deployed/Unpinned Contracts" section, check the totalSupply function to determine if the token supply is at zero. To mint tokens, paste your account address and the desired amount. Check the totalSupply or Balance function for the amount of tokens. The Burn function deducts tokens from the same address, type 500 in the value type. Check if the function works by calling tokenSupply or Balance.

and that it for my simple guidance to use MyToken Contract.

## Authors

- [@JohnKennethBorito31](https://github.com/JohnKennethBorito31)

- [@metacraftersio](https://www.metacrafters.io/)


## License

- [MIT](https://github.com/JohnKennethBorito31/BoritoJK_SolidityAssessment/blob/main/LICENSE)


