# Troubleshooting

# Masternode
- <b>Corrupt Chain on VPS</b><br>
- <b>VPS Syncing or Loading chain for too long</b>

Log on to the VPS:
```bash
~/nodium/src/nodium-cli stop
cd nodium
rm -Rf blocks 
rm -Rf chainstate 
rm -f mncache.dat 
rm -f peers.dat 
rm -f .lock
~/nodium/src/nodiumd -daemon
```
Straight after. In Local Wallet. Tools > Debug Console, type:
```bash
# (MN01 should be the alias of your masternode)
startmasternode alias 0 "MN01"
```

Back on VPS:
`~/nodium/src/nodium-cli getmasternodestatus`

You should get this result:
```js
{
  // txhash, outputidx, netaddr, addr
  "status" : 4,
  "message" : "Masternode successfully started"
}
```

- <b>Failed to Start Masternode</b><br>
- <b>ERROR: Invalid IP Address</b><br>
- <b>Hot Node requires remote activation</b><br>
- <b>Node goes missing randomly and wallet open for more than 5 minutes</b><br>

Reboot the server (through putty/terminal):
```bash
sudo reboot
```

Log back on and type:
_DISCLAIMER: the daemon should auto start, so if this next command is run, it may throw an error stating it is running_
`~/nodium/src/nodiumd -daemon`

Straight after. In Local Wallet. Tools > Debug Console, type:
```bash
# (MN01 should be the alias of your masternode)
startmasternode alias 0 "MN01"
```

Back on VPS:
```bash
~/nodium/src/nodium-cli getmasternodestatus
```

You should get this result:
```js
{
  // txhash, outputidx, netaddr, addr
  "status" : 4,
  "message" : "Masternode successfully started"
}
```

# VPS

<b>Cannot bind port</b>
When using another VPS provider (Microsoft Azure for example) as mentioned in this guide, you might not be able to directly bind the port to your external VPS IP. You will get an error at the end of the setup. In that case you need to bind it to your local IP. You can find the local IP by typing logging in to the VPS with the in the guide given user:
* Type: `ifconfig`  ENTER
* Look for the `eth0` interface:<br>
![Imgur](https://i.imgur.com/ftQlQLp.png)
* Copy `inet addr:<i>10.0.1.5</i>` (example)<br>
* Type: `nano ~/.Nodium/nodium.conf`  ENTER
* Change: `bind=<i>10.0.1.5</i>` (example)<br>
* Type: `ctrl+o`
* Type: `ctrl+x` <br>

Now, login to the VPS portal to add the inbound network port (6250) because your host could not bind it through the VPS host.
This is pretty generic (Microsoft Azure example) please follow the hoster guides for your situation. 
<br>
![Imgur](https://i.imgur.com/YcNrWKF.png)
<br>
Next, back on the VPS:
* Type: `~/nodium/src/nodiumd -daemon`
Now it will start the Nodium NM using the new settings you just made.

# Wallet
<b>In the Nodium Wallet there are repair tools to fix common QT issues. Go to 'Tools' in the menu and select 'Wallet repair'</b>
<br>
![Imgur](https://i.imgur.com/13tW7J7.jpg)


