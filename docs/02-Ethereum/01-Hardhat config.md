Due different networks configurations we have to configurate tool for our network. Also we need to set private keys.

Open and set-up ***hardhat.config.js***

Remove deterministicDeployment section from hardhat config, because we won't use this feature.

Due "HttpNetworkHDAccountsConfig" you need to replace broken networks part.
Count and process.env didn't worked for me, so I simply remove all "count: 50" and replace "process.env.ETH_MNEMONIC" with "*MY_MNEMONIC*"

# Remove all lines thats include dai, usdt and usdc if you deploying to *testnet*.

5. Run npx hardhat deploy --network "*YOUR_NETWORK*"

You may need to increase gas price in ***hardhat.config.js***, ***gasPrice*** field.