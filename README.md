## Signatures and Merkle Trees | The deep dive to understand it

### Merkle Trees
- Merkle proofs comes from the merkle trees
- Merkle trees is a data structure
- Merkle proofs verify that that data exists in merkle trees and comes from it
- Each of the leap represent a data, and is mostly referred to leap node
- Data is hashed via keccak to produce leap node -> leap nodes are hashed to produce intermediate nodes -> then intermediate nodes are hashed to produces root hash
- In blockchains the block header includes transaction root, receipt root and state root. And these are merkle root hashes ... these are merkle patricia roots!
- Merkle trees are used in roll ups (`L2 scaling solutions`)
    - Batch roots, state roots
    
### Signatures
- ECDSA
    - elliptic curve digital signature algorithm
    - generate key pairs
    - create signatures
    - verify signatures
- r: x point on the secp256k1 curve 
- S: proof signer knows the private key
- v: if in positive or negative part of the curve
- direct use of ecrecover is not recommended
- EIP-191, Signed Data Standard
- EIP-712 signatures and verifications. It made signatures more easy to read. It prevents replay attacks
    - 0x91 0x01 <domain seperator> <hashStruct(message)>
- EIP-712 provides a structured and human-readable way to sign typed data, enhancing clarity and reducing errors, while EIP-191 offers a simpler, more flexible method for signing arbitrary data.    
 
Ref: https://youtu.be/jGC3pGCfYQE