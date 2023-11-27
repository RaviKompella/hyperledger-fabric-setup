# Asset Transfer Test Cases

## Test Case 1: Create Marble

**Description**: Test the successful creation of a marble.

**Steps**:

1. Bob initiates a transaction to create a marble with specific attributes (color, size, owner, etc.).
2. Verify that the transaction is successful.
3. Verify that the new marble exists in the ledger with the correct attributes.

## Test Case 2: Transfer Marble Success

**Description**: Test the successful transfer of a marble from one participant to another.

**Steps**:

1. Bob initiates a transfer of Marble X to Alice.
2. Verify that the transaction is successful.
3. Verify that Bob no longer owns Marble X.
4. Verify that Alice is now the owner of Marble X.

## Test Case 3: Insufficient Marble Balance

**Description**: Test the scenario where a participant attempts to transfer a marble they do not own.

**Steps**:

1. Bob initiates a transfer of Marble X (which he does not own) to Alice.
2. Verify that the transaction fails.
3. Verify that the owner of Marble X has not changed.

## Test Case 4: Transfer Marble to Self

**Description**: Test the scenario where a participant attempts to transfer a marble to themselves.

**Steps**:

1. Bob initiates a transfer of Marble X (which he owns) to himself.
2. Verify that the transaction fails or is a no-op.
3. Verify that Bob remains the owner of Marble X.

## Test Case 5: Transfer Non-existent Marble

**Description**: Test the scenario where a participant attempts to transfer a marble that does not exist.

**Steps**:

1. Bob initiates a transfer of Marble Y (which does not exist) to Alice.
2. Verify that the transaction fails.
3. Verify that the ownership of all existing marbles has not changed.

## Test Case 6: Transfer Marble to Non-existent Participant

**Description**: Test the scenario where a participant attempts to transfer a marble to a participant that does not exist.

**Steps**:

1. Bob initiates a transfer of Marble X to Charlie (who does not exist).
2. Verify that the transaction fails.
3. Verify that Bob remains the owner of Marble X.

## Test Case 7: Verify Transaction in Blockchain Explorer

**Description**: This test case verifies that a completed transaction is correctly reflected in the blockchain explorer.

**Steps**:

1. Bob initiates a transfer of Marble X to Alice.
2. Verify that the transaction is successful.
3. Open the local blockchain explorer.
4. Locate the completed transaction in the blockchain explorer.
5. Verify that the transaction details are correct (e.g., sender is Bob, receiver is Alice, transferred item is Marble X).

## Test Case 8: Verify Art Piece Creation in Blockchain Explorer

**Description**: This test case checks that a newly minted art piece is correctly reflected in the blockchain explorer.

**Steps**:

1. Artist Bob mints a new digital art piece with specific attributes (title, description, etc.).
2. Verify that the transaction is successful.
3. Open the local blockchain explorer.
4. Locate the completed transaction in the blockchain explorer.
5. Verify that the transaction details are correct (e.g., artist is Bob, art piece attributes match those provided).

## Test Case 9: Verify Failed Transaction in Blockchain Explorer

**Description**: This test case verifies that a failed transaction (e.g., due to insufficient balance) is correctly reflected in the blockchain explorer.

**Steps**:

1. Bob, with insufficient marbles, initiates a transfer of Marble X to Alice.
2. Verify that the transaction fails.
3. Open the local blockchain explorer.
4. Locate the failed transaction in the blockchain explorer.
5. Verify that the transaction details are correct and reflect the failure (e.g., sender is Bob, intended receiver is Alice, transferred item is Marble X, status is "failed").

