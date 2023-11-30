
# Asset Transfer Use Case

To transfer ownership of a stock asset, follow these steps:

1. Create a new stock asset with the given attributes.
2. Transfer ownership of the stock asset to a new owner.
3. Before completing the transfer, check if the stock price is below a certain amount.



## Stock Asset Structure

- StockID: [string] - A unique identifier for the stock asset.
- CompanyName: [string] - The name of the company the stock represents.
- ShareCount: [integer] - The number of shares the stock asset represents.
- CurrentOwner: [string] - The identifier of the current owner of the stock.
- ValuePerShare: [float] - The monetary value of each individual share.
- IssuanceDate: [date] - The date on which the stock was created/issued.
- IsDividendPaying: [boolean] - Indicates whether the stock pays dividends.
- Sector: [string] - The sector or industry to which the company and its stock belong.


## Test Case 1: Successful Creation of a Stock Asset by Bob
Objective: To verify Bob's successful creation of a stock asset with specified attributes.

## Steps:
Bob initiates a transaction to create a new stock asset with the following attributes:
- StockID: "STK123"
- CompanyName: "TechCorp"
- ShareCount: 100
- CurrentOwner: "Bob"
- ValuePerShare: $65.00
- IssuanceDate: "2023-06-01"
- IsDividendPaying: true
- Sector: "Technology"

Verify that the transaction is successful.
Confirm that the new stock asset exists in the ledger with the correct attributes.

## Test Case 2: Transfer of 2 Shares from Bob to Alice (Successful)
Objective: To test the successful transfer of 2 shares from Bob to Alice since the share price is above $60.

## Steps:
- Assuming Bob owns the stock "STK123" with a ValuePerShare of $65.00.
- Bob initiates a transaction to transfer 2 shares of "STK123" to Alice.
- Verify that the transaction is successful.
- Confirm that Bob’s ShareCount is reduced to 98 and Alice now owns 2 shares of "STK123".

## Test Case 3: Transfer of 2 Shares from Bob to Alice (Unsuccessful due to Share Price)
Objective: To test the scenario where the transfer of 2 shares from Bob to Alice does not occur because the share price is below $60.

## Steps:
- Bob changes the ValuePerShare of "STK123" to $55.00.
- Bob attempts to transfer 2 shares of "STK123" to Alice.
- Verify that the transaction fails due to the share price being below $60.
- Confirm that the ownership and ShareCount for "STK123" remain unchanged.

## Test Case 4: Transfer of Non-Existent Stock Asset by Bob
Objective: To ensure that the system handles attempts by Bob to transfer a stock asset that does not exist.

## Steps:
- Bob attempts to transfer 2 shares of a non-existent stock asset with StockID "STK999" to Alice.
- Verify that the transaction fails.
- Confirm that no changes have occurred in the ledger regarding stock assets.

## Test Case 5: Verification of Transactions in Blockchain Explorer
Objective: To verify that the transactions of creating and transferring stock assets are correctly reflected in the blockchain explorer.

## Steps:
- Complete the transactions from Test Cases 1, 2, and 3.
- Verify that the relevant transactions have been processed as expected.
- Access the blockchain explorer.
- Locate the transactions for "STK123" and verify that the details (e.g., transaction type, involved parties, asset attributes) are correctly recorded.
