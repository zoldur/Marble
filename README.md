# Marble
Shell script to install a [Marble Masternode](http://www.marblecoin.co/) on a Linux server running Ubuntu 16.04. Use it on your own risk.
***

## Installation
```
wget -q https://raw.githubusercontent.com/zoldur/Marble/master/marble_install.sh
bash marble2_install.sh
```
***

## Desktop wallet setup  

After the MN is up and running, you need to configure the desktop wallet accordingly. Here are the steps:  
1. Open the Marble Desktop Wallet.  
2. Go to RECEIVE and create a New Address: **MN1**  
3. Send **25000** MARCO to **MN1**. You need to send all 25000 coins in one single transaction.
4. Wait for 15 confirmations.  
5. Go to **Help -> "Debug Window - Console"**  
6. Type the following command: **masternode outputs**  
7. Open Windows Explorer and go to **%APPDATA%\Marbel2** folder
8. Open/create masternode.conf
9. Add the following entry:
```
Alias Address Privkey TxHash TxIndex
```
* Alias: **MN1**
* Address: **VPS_IP:PORT**
* Privkey: **Masternode Private Key**
* TxHash: **First value from Step 6**
* TxIndex:  **Second value from Step 6**
10. Save and close the file.
11. Open **Debug Console** and type:
```
masternode start-alias MN1
```
12. Login to your VPS and check your masternode status by running the following command. If you get **Status 9**, it means your masternode is active.
```
Marbled masternode status
```
***

## Usage:
```
marble-cli mnsync status
marble-cli masternode status  
marble-cli getinfo
```
Also, if you want to check/start/stop **Marble**, run one of the following commands as **root**:

```
systemctl status Marble #To check if Marble2 service is running
systemctl start Marble #To start Marble2 service
systemctl stop Marble #To stop Marble2 service
systemctl is-enabled Marble #To check if Marble2 service is enabled on boot
```  
***

## Donations

Any donation is highly appreciated

**BTC**: 3MQLEcHXVvxpmwbB811qiC1c6g21ZKa7Jh  
**ETH**: 0x26B9dDa0616FE0759273D651e77Fe7dd7751E01E  
**LTC**: LNZpK4rCd1JVSB3rGKTAnTkudV9So9zexB  
