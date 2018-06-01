<b>Staking</b>
Proof-of-Stake (PoS, staking) means that wallets connected and unlocked for staking to the network generate new coins and make a passive income possible simply by holding XN. 
The staking process produces new coins without consuming significant computational power like with mining and keeps the Nodium network safer. 
Anyone who holds XN in the Nodium Wallet will receive rewards for helping the blockchain. Simply keep your wallet open and your balance will generate new coins when the blocks for that are found.

Staking should start automatically once your coins mature and you unlock your wallet. This can initially take an hour or so.
Your wallet will need to remain open and unlocked for staking to receive a reward. Please see below for some guidance on staking.

<b>Unlock to stake</b>
To begin staking, download the Nodium wallet from https://nodium.org ,initialize it and send XN to a receiving address you own.

If you have previously encrypted your wallet you must unlock it for staking, goto settings and click unlock wallet:
![Imgur](https://i.imgur.com/9VYRHSW.png)
<br>

Next, enter your password. <b>Make sure you check: For anonymization and staking only</b>
![Imgur](https://i.imgur.com/8OXAe0C.png)

<b>How to 'force' staking on/off</b>
Open the wallet. Tools >  Open Wallet Config File, add the line staking=1 for ON or staking=0 for OFF
![Imgur](https://i.imgur.com/lV5BwIl.png)

<b>How to set inputs not to split after get stake?</b>
In the debug console type setstakesplitthreshold <1 - 9999999>, <1 - 9999999> is the amount. When the input is big enough to split in set amount the split will happen. for example setstakesplitthreshold 500 and your input is bigger than 1000 the input will split, if it's less than 1000 will not. 

<b>What is the best input amount?</b>
Best input amount for staking depends from the network weight. Network weight is the sum of all staking coins. More coins is staking faster.

<b>When do coins start staking?</b>
When the minimum mature time is reached, 1 hour

<b>Troubleshooting</b>
- How to start Staking?
- Troubleshoot Staking Activation
- Toggle On/Off Staking

First way to check. Open the wallet, bottom right corner, hover over the up arrow.
It should display <b>Staking is active</b>
![Imgur](https://i.imgur.com/G53PoP4.png)

If not:
Check inside the wallet. Tools > Debug Console, type: getstakingstatus
This is the correct output to receive staking coins:
![Imgur](https://i.imgur.com/ErKmWoS.png)

The output should show all as True. If this is the case, be patient.

<b>False Output fixes</b>
- haveconnections :  if false, you don't have connections to the coin network. Make sure you have internet access, consider port being blocked or bad connectivity.
- walletunlocked : if false, Go to Settings > Unlock Wallet and enter your passphrase and check "For anonymous and staking only"
- mintablecoins :if false, you either don't have any unlocked coins or they are too fresh and you will need to wait for them to be able used for staking. Patience is key. Just leave the wallet open.
- enoughcoins :if false, you need more coins unlocked. There should be no minimum.
- mnsync :if false, wait 20 minutes. If still false consider an mnsync reset.
- staking status :if all of the above is True and this is still False, first try, close the wallet for 30 seconds, open and unlock (if encrypted), wait 5 minutes.
