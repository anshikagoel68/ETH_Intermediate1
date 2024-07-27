**Title:** ErrorHandlingMethods Contract

**License**
This contract is licensed under the MIT License.

**Contract Overview**
The 'ErrorHandlingMethods' contract is a straightforward Ethereum smart contract that demonstrates fundamental Solidity features, including state management and error handling mechanisms. It allows users to store and retrieve a single 'uint256' value, providing a simple interface for basic data manipulation. Additionally, the contract includes functionality to modify the stored value by doubling it, showcasing how to update and validate state changes. The contract further illustrates key error handling concepts by using 'require', 'assert', and 'revert' statements for input validation and to ensure the contract operates correctly under various conditions. This design serves as an educational example for understanding core aspects of Solidity programming.

**Functions used in the contract**

1. setNumber(uint256 newNumber)
 - Description: a. Sets a new number in the contract. It used newNumber as a parameterto the store the 
                   number.
                b. Uses require to validate that newNumber is greater than 0. If the condition is not met, 
                   the transaction will revert with an error message: "Number must be greater than 0".

2. getNumber(uint256)
Description: Retrieves the currently stored number.

3. doubleStoredNumber()
- Description: Doubles the stored number and updates the contract state.
- Functionality: a. Computes the doubled value of the stored number.
               b. Uses assert to ensure the correctness of the doubling operation. Specifically, it checks 
                  that doubled / 2 equals the original storedNumber. If this condition fails, the 
                  transaction will revert with a default assertion error.
              c. Updates storedNumber with the doubled value.

4. checkNumber(uint256 number)
- Description: Checks if the provided number is non-zero. It used the number as parameter to check the 
                number.
- Functionality: a. Uses revert to throw an error if number is zero. The error message will be: "Number 
                    must not be zero".
               b. If number is non-zero, the function completes successfully.
  
 **Error Handling Methods**
  
1) require statement
The require statement is used to validate input parameters and conditions before executing further logic. If the condition specified in require is not met, the transaction is reverted, and an error message is returned to the caller. It helps prevent the contract from entering an invalid state.
_Example in setNumber function:_ require(newNumber > 0, "Number must be greater than 0");

2) assert statement
The assert statement is used to check for conditions that should never be false. It is typically used to verify invariants and internal logic assumptions. If the condition specified in assert fails, the transaction is reverted, and the contract state is reverted to its previous state.
_Example in doubleStoredNumber function:_ assert(doubled / 2 == storedNumber);

3) revert statement
The revert statement is used to manually revert the transaction with a specific error message. It is useful for handling cases where a specific condition is not met, and it allows custom error messages to be returned.
_Example in checkNumber function:_ if (number == 0) {
                                       revert("Number must not be zero");
                                    }
**Deployment and Usage**

1. Compile: Use a Solidity compiler compatible with version ^0.8.0.
2. Deploy: Deploy the SimpleStorage contract to an Ethereum blockchain or a test network.
3. Interact: Use a web3 interface or Ethereum development environment to call the contract's functions.


   

   
- 



