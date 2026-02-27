💳 Credit Card Checker

A robust JavaScript utility suite designed to validate credit card numbers using the Luhn Algorithm. This project can process batches of card numbers, filter out invalid entries, and identify the issuing companies based on industry-standard prefixes.

🚀 Features

Luhn Validation: Implements the "Mod 10" algorithm to check the mathematical validity of card numbers.

Batch Processing: Scans through nested arrays of card data to isolate invalid entries efficiently.

Provider Identification: Maps invalid cards to their issuing companies (Amex, Visa, Mastercard, or Discover) based on the first digit.

No Mutation: Processes data without altering the original input arrays.

🛠️ The Logic: How it Works

The core of this project is the Luhn Algorithm, which validates a number through these steps:

Iterate: Starting from the farthest digit to the right (the check digit), move to the left.

Double: As you iterate, double every other digit (starting with the digit to the left of the check digit).

Adjust: If the doubled number is greater than 9, subtract 9 from it.

Sum: Add all the resulting digits in the credit card number.

Check: If the total sum modulo 10 is 0, the number is valid; otherwise, it is invalid.

📂 Function Breakdown

validateCred(array)

The primary validation function. It takes an array of numbers and returns true if the card is valid and false if not. It utilizes the "doubling" logic while keeping the original array intact.

findInvalidCards(nestedArray)

Iterates through a "batch" of credit card numbers (an array of arrays) and returns a new nested array containing only the cards that failed validation.

idInvalidCardCompanies(invalidBatch)

Takes the list of invalid cards and identifies the providers based on the following industry standards:

3: Amex (American Express)

4: Visa

5: Mastercard

6: Discover

💻 Usage

To run the script and see the validation results, use Node.js in your terminal:

node credit_card_checker.js


📝 Technologies Used

JavaScript (ES6+)

Node.js (for execution)
