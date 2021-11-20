# prediction-contract

## Deploy

Contructor parameters: "0x0567F2323251f0Aab15c8dFb1967E4e8A7D42aeE","0x3EA1a17F068A1D6c4eCC9210687D7Eb975685dC0","0x3EA1a17F068A1D6c4eCC9210687D7Eb975685dC0","300","30","1000000000000000","300","300"

- [BNB / USD data feed](https://data.chain.link/bsc/mainnet/crypto-usd/bnb-usd): 0x0567F2323251f0Aab15c8dFb1967E4e8A7D42aeE
- Admin address: 0x3EA1a17F068A1D6c4eCC9210687D7Eb975685dC0
- Operator address: 0x3EA1a17F068A1D6c4eCC9210687D7Eb975685dC0
- Interval (number of seconds for valid execution of a prediction round): 300
- Buffer (interval in seconds between two prediction rounds): 30
- Minbet: 1000000000000000
- Oracle update allowance: 300
- Treasury fee: 300

## Run

- Step 1: Call `genesisStartRound` to start the first round.
- Step 2: After 600s, set gasLimit greater than 200,000 (maybe) then Call `genesisLockRound` (must be complete in 30s).
- Step 3: After 600s, call `executeRound` to start the next round n, lock price for round n-1, end round n-2.

Note: If we the time is exceeded then we must call `pause` and then `unpause` to restart the contract state

## Get history

We can use https://thegraph.com/en/ to get historical data.
