# Troubleshooting

# Masternode
- <b>Corrupt Chain on VPS</b><br>
- <b>VPS Syncing or Loading chain for too long</b>

Log on to the VPS:
~/nodium/src/nodium-cli stop
cd nodium
rm -Rf blocks 
rm -Rf chainstate 
rm -f mncache.dat 
rm -f peers.dat 
rm -f .lock
~/nodium/src/nodiumd -daemon

Straight after. In Local Wallet. Tools > Debug Console, type:
MN01 should be the alias of your masternode
startmasternode alias 0 "MN01"

Back on VPS:
~/nodium/src/nodium-cli getmasternodestatus

You should get this result:
"status" : 4
"message" : "Masternode successfully started"


- <b>Failed to Start Masternode</b><br>
- <b>ERROR: Invalid IP Address</b><br>
- <b>Hot Node requires remote activation</b><br>
- <b>Node goes missing randomly and wallet open for more than 5 minutes</b><br>

Reboot the server (through putty below):
sudo reboot

Log back on and type:
DISCLAIMER: the daemon should auto start, so if this next command is run, it may throw an error stating it is running
~/nodium/src/nodiumd -daemon

Straight after. In Local Wallet. Tools > Debug Console, type:
MN01 should be the alias of your masternode
startmasternode alias 0 "MN01"

Back on VPS:
~/nodium/src/nodium-cli getmasternodestatus

You should get this result:
"status" : 4
"message" : "Masternode successfully started"

# Wallet
<b>In the Nodium Wallet there are repair tools to fix common QT issues. Go to 'Tools' in the menu and select 'Wallet repair'</b>
<br>
![Imgur](https://i.imgur.com/13tW7J7.jpg)


