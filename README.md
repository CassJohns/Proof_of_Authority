# Proof_of_Authority

NodeA:

Public address of the key:   0x2e5632261B97c06323eaE4601719490D4F1C7F73
Path of the secret key file: nodeA\keystore\UTC--2021-01-31T13-29-45.098176800Z--2e5632261b97c06323eae4601719490d4f1c7f73


NodeB:

Public address of the key:   0x25e1cf3463A9e591D64822351346B8fb217aeCd6
Path of the secret key file: nodeB\keystore\UTC--2021-01-31T13-30-44.801396800Z--25e1cf3463a9e591d64822351346b8fb217aecd6


Run the first node, unlock the account, enable mining, and the RPC flag. Only one node needs RPC enabled.

./geth --datadir nodeA --unlock "25e1cf3463A9e591D64822351346B8fb217aeCd6" --mine --minerthreads 1 --rpc --allow-insecure-unlock


Node A: 
self=enode://d50dc2db0ab1288cbc47aff4be5c0d12d56ddae39f90331edbd1a2f51182bed8b0599f835bd4fa39e7b24acfc34756eb5b3f386a46cc6ed05dc5e4dc78a9ef43@127.0.0.1:30303

Start Node A
INFO [01-31|10:53:20.048] Commit new mining work                   number=1 sealhash="8e81b0…d1cb67" uncles=0 txs=0 gas=0 fees=0 elapsed=0s


Set a different peer port for the second node and use the first node's enode address as the bootnode flag.

Be sure to unlock the account and enable mining on the second node

./geth --datadir nodeB --port 30304 --mine --minerthreads 1 -bootnodes "enode://d50dc2db0ab1288cbc47aff4be5c0d12d56ddae39f90331edbd1a2f51182bed8b0599f835bd4fa39e7b24acfc34756eb5b3f386a46cc6ed05dc5e4dc78a9ef43@127.0.0.1:30303" --ipcdisable
  

Node B:

INFO [01-31|10:54:47.818] Started P2P networking                   self=enode://384afed120583e3dc1b55c61c0cf056282aac895ad31d5d6a1d8542e06458c2c518df92c5496375bae96b7c61589c1aa336b4ea2d8384e963a63bd211cec3d40@1
27.0.0.1:30304

Start Node B

INFO [01-31|10:54:47.834] Etherbase automatically configured       address=0x25e1cf3463A9e591D64822351346B8fb217aeCd6
INFO [01-31|10:54:47.838] Commit new mining work                   number=1 sealhash="c48567…a1b3b6" uncles=0 txs=0 gas=0 fees=0 elapsed=0s

