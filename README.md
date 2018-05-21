# FAQ
Most frequently asked questions at nodium

<b>How much coins do I need to run a masternode?</b>
- 10,000 XN.

<b>What is Masternode and staking reward?</b>
- 90% Masternodes, 10% stakers.

<b>How much is the total supply of Nodium?</b>
- Refer to main coin specs, github.

<b>Where can I download a wallet?</b>
- Directly on our Github, wallets repository. Apple, Windows and Linux available.

<b>Troubleshooting:</b>
<br>
Failed to Start Masternode
<br>
ERROR: Invalid IP Address
<br>
Hot Node requires remote activation
<br>
Node goes missing randomly and wallet open for more than 5 minutes
<br>

- Reboot the VPS, insert command when logged in:
- sudo reboot

- After reboot, log back on the VPS and input:

#DISCLAIMER: the daemon should auto start, so if this next command is run, it may throw an error stating it is running
- ~/nodium/src/nodiumd -daemon

- Next, go to your (local) installed wallet. Click: Tools (Preferences on MacOS) > Debug Console, and input:

#MN01 should be the alias of your masternode, correct this to your chosen alias.
- startmasternode alias 0 "MN01"

- Switch back to the VPS and input:
- ~/nodium/src/nodium-cli getmasternodestatus

- You should get the following result:
- "status" : 4
- "message" : "Masternode successfully started"
<br>

<b>Troubleshooting block out of sync:</b>
<br>
When the masternode blocks are out of sync, please do the following.

- Login to your VPS and input:

- ~/nodium/src/nodium-cli stop
- ~/nodium/src/nodiumd -resync
- ~/nodium/src/nodium-cli getinfo

- When done, input:
- sudo reboot

- Next, go to your (local) installed wallet. Click: Tools (Preferences on MacOS) > Debug Console, and input:
- #MN01 should be the alias of your masternode, correct this to your chosen alias.
- startwallet alias 0 “mn1”

- Switch back to the VPS and input:
- ~/nodium/src/nodium-cli getmasternodestatus

- You should get the following result:
- "status" : 4
- "message" : "Masternode successfully started"
<br>
Now you masternode should be on the most current block and you will have confirmed the masternode to be succesfully started.

---

Will be continuously be updated.



