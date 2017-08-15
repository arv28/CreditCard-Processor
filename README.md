# CreditCard-Processor
A program that will add new credit card accounts, process charges and credits and display summary information

Imagine that you're writing software for a credit card provider.  Implement a program that will add new credit card accounts, process charges and credits against them, and display summary information.

## Requirements:
- This program accepts input from two sources: a filename passed in command line arguments and STDIN. For example, on Linux or OSX both
  './myprogram input.txt' and './myprogram < input.txt' should work.
- This program accepts three input commands passed with space delimited arguments.
- "Add" will create a new credit card for a given name, card number, and limit
   - Card numbers should be validated using Luhn 10
   - New cards start with a $0 balance
- "Charge" will increase the balance of the card associated with the provided name by the amount specified
   - Charges that would raise the balance over the limit are ignored as if they
     were declined
   - Charges against Luhn 10 invalid cards are ignored
- "Credit" will decrease the balance of the card associated with the provided name by the amount specified
   - Credits that would drop the balance below $0 will create a negative balance
   - Credits against Luhn 10 invalid cards are ignored
- When all input has been read and processed, a summary is generated and written to STDOUT in the format shown in the example below.
- The summary includes the name of each person followed by a colon and balance.
- The names are displayed alphabetically.
- Displays "error" instead of the balance if the credit card number does not pass Luhn 10.

## Input and Output:

Given the following input:

```
Add Tom 4111111111111111 $1000
Add Lisa 5454545454545454 $3000
Add Quincy 1234567890123456 $2000
Charge Tom $500
Charge Tom $800
Charge Lisa $7
Credit Lisa $100
Credit Quincy $200
```
Output:
```
Lisa: $-93
Quincy: error
Tom: $500
```
