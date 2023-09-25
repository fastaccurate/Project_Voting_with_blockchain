# Project_Voting_with_blockchain

## Guidelines regarding input format
- Minting of tokens, distribution, and the voting system are implemented in a single contract.
- The format of input to constructor before deployment:
   1. `_CANDIDATES: ["a", "b", "c"]`
   2. `mint_tokens_to: ["0xAddress1", "0xAddress2", "0xAddress3"]`

- Functions like `addCandidate`, `Mint_tokens_to`, `StartElection`, `endElection`, `checkBalanceOf`, and `hasVotedStatus` can be called by the owner only.

## Blockheight and timestamp are also implemented for transparency

## Security improvement: Two-layer Contract Encryption
- Two layers of security are implemented instead of just one.
- This is done by checking two conditions:
   1. Checking if the address has sufficient token balance: `_VTRbalances[msg.sender]`
   2. Maintaining one more mapping: `hasVoted[msg.sender]`. It is initially false and becomes true once a voter has voted.
- So, by checking two conditions, it enhances the contract security and shields it from Reentry attacks.
