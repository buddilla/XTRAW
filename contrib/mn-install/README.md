# XTraw
Shell script to install a [XTraw Masternode](https://traw.network) on a Linux server running Ubuntu 16.04. Use it on your own risk.
***

## Installation
```
wget -N https://raw.githubusercontent.com/BitcoinGOAT/XTRAW/master/contrib/mn-install/xtraw_install.sh
bash xtraw_install.sh
```
***

## Desktop wallet setup  

After the MN is up and running, you need to configure the desktop wallet accordingly. Here are the steps:  
1. Open the XTraw Desktop Wallet.  
2. Go to RECEIVE and create a New Address: **MN1**  
3. Send **145000** XTRAW to **MN1**. You need to send all 145000 coins in one single transaction.
4. Wait for 15 confirmations.  
5. Go to **Tools -> "Debug Console"**  
6. Type the following command: **masternode outputs**  
7. Go to  **Tools -> "Open Masternode Configuration File"**
8. Add the following entry:
```
Alias Address Privkey TxHash TxIndex
```
* Alias: **MN1**
* Address: **VPS_IP:PORT**
* Privkey: **Masternode Private Key**
* TxHash: **First value from Step 6**
* TxIndex:  **Second value from Step 6**
9. Save and close the file.
10. Go to **Masternode Tab**. If you tab is not shown, please enable it from: **Settings - Options - Wallet - Show Masternodes Tab**
11. Click **Update status** to see your node. If it is not shown, close the wallet and start it again. Make sure the wallet is unlocked.
12. Select your MN and click **Start Alias** to start it.
13. Alternatively, open **Debug Console** and type:
```
masternode start-alias MN1
```
14. Login to your VPS and check your masternode status by running the following command to confirm your MN is running:
```
xtraw-cli masternode status
```
***

## Usage:
```
xtraw-cli masternode status
xtraw-cli getinfo
xtraw-cli mnsync status
```
Also, if you want to check/start/stop **XTraw**, run one of the following commands as **root**:

```
systemctl status XTraw #To check if XTraw service is running  
systemctl start XTraw #To start XTraw service  
systemctl stop XTraw #To stop XTraw service  
systemctl is-enabled XTraw #To check if XTraw service is enabled on boot  
```  
***

Based on awesome install scripts by [Zoldur](https://github.com/zoldur)
