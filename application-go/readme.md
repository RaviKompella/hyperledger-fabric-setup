# Running Hyperledger Fabric on server
This includes smart contract and application code in multiple languages. This sample shows create, read, update, transfer and delete of an asset.

For a more detailed walk-through of the application code and client API usage, refer to the Running a Fabric Application tutorial in the main Hyperledger Fabric documentation.

Application
Follow the execution flow in the client application code, and corresponding output on running the application. Pay attention to the sequence of:

Transaction invocations (console output like "--> Submit Transaction" and "--> Evaluate Transaction").
Results returned by transactions (console output like "*** Result").
Smart Contract
The smart contract (in folder chaincode-xyz) implements the following functions to support the application:

* CreateAsset
* ReadAsset
* UpdateAsset
* DeleteAsset
* TransferAsset
  
Note that the asset transfer implemented by the smart contract is a simplified scenario, without ownership validation, meant only to demonstrate how to invoke transactions.

Running the sample
The Fabric test network is used to deploy and run this sample. Follow these steps in order:

## Step 1: Create the test network and a channel (from the test-network folder).

Deploy one of the smart contract implementations (from the test-network folder).

`./network.sh up createChannel -c mychannel -ca`\


## Step 2: To deploy the chaincode implementation
`./network.sh deployCC -ccn basic -ccp ../asset-transfer-basic/chaincode-go/ -ccl go`

## Step 3: To run the Go sample application
`cd application-gateway-go `\
`go run .`

## Step 4: Clean up
When you are finished, you can bring down the test network (from the test-network folder). The command will remove all the nodes of the test network, and delete any ledger data that you created.

`./network.sh down`
