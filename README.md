./geth # Proof_of_Authority

#Node Information 

NodeA1:
Public address of the key:   0xca13091C81977ADD89a921dF951912C3e2AFB036
Path of the secret key file: nodeA1\keystore\UTC--2021-02-06T20-28-45.471016000Z
--ca13091c81977add89a921df951912c3e2afb03


Node2A:
Public address of the key:   0x5F9A55f7D011a4c45492A6155C572fdB535648fb
Path of the secret key file: node2A\keystore\UTC--2021-02-06T20-29-10.207286600Z
--5f9a55f7d011a4c45492a6155c572fdb535648fb


#Run the Nodes 

Run the first node, unlock the account, enable mining, and the RPC flag. 

./geth --datadir nodeA1 --unlock "ca13091C81977ADD89a921dF951912C3e2AFB036" --mine --rpc --allow-insecure-unlock

Record the enode: 
Node A1: 
self=enode://ce7ff7625b21070dd2afa980f61d2da328d0264f014dd8f5c233f605cdcc71f0eb23427dd2d265b539a8cca8884ff4ea70fb31cd23957c4ff72851b6c3fc1d74@1
27.0.0.1:30303

Unlock the account and enable mining on the second node: 

./geth --datadir node2A --unlock "5F9A55f7D011a4c45492A6155C572fdB535648fb" --mine --port 30304 --bootnodes "enode://ce7ff7625b21070dd2afa980f61d2da328d0264f014dd8f5c233f605cdcc71f0eb23427dd2d265b539a8cca8884ff4ea70fb31cd23957c4ff72851b6c3fc1d74@127.0.0.1:30303" --ipcdisable --allow-insecure-unlock
  
Record the enode:

Node 2A:

self=enode://f67af224af520b10942032e59c1acf4b3af9468826d143b244c82b56d7bfd6a7eacf41bb7c2bd196a628798e4070ffcc6f240c78f59c5f239be4d990
1db666c7@127.0.0.1:30304

#My Crypto Connect 

Create a custom node using the network name authofpuppernet, using ETH currency, and the chain ID of 500.  Import the keystore file from NodeA1. 

#Initiate a transaction

Initiate a transaction from NodeA1 using hte custom node just set up, and send to the public address shown above for node2A.  




