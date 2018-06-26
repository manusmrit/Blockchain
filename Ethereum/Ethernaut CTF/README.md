This is meant to be my code submissions for the harder Ethernaut challenges I faced.

CoinFlip
-------------------------------------------------------------------------------------------------------------------------------------------------------------------------
CoinFlipAttack.sol is my code that intialises the target exploitable contract within my own malicious contract.
The idea is to generate 10 consecutive flips in the CoinFlip contract. To achieve this within the contract itself is nearly impossible.

What I did was to instantiate my own malicious contract that will initialise a CoinFlip contract with the target instance address (provided by Ethernaut CTF)
This ensures that the CoinFlip contract created here will point to that address.

My malicious contract has a predict() function that would derive the answer to the coin flip before hand, before passing that answer into the CoinFlip contract as my guess. This is possible as the answer to each coin flip is deterministic --> it is dependent on the latest block header hash. Hence, we can easily determine the answer in a seperate function before passing it into the CoinFlip contract's guess function automatically.
-------------------------------------------------------------------------------------------------------------------------------------------------------------------------