# MN-Setup

Masternode Guide
						
Download wallet from releases and Pay 1000 BANQ to yourself.
Make sure you have a little more than 1000 BANQ in your balance. 
Pay exactly 1000 BANQ to yourself. When you make transaction you pay a small fee, this is the reason you need a little more than 1000 BANQ.

To make transaction:

a) Go to File -> Receiving Addresses
						
b) Click on «New» and give LABEL name, something like «MN» and click «Ok». Select the created address and click «copy».
						
c) On your main window go to «Send» tab. Paste the copied address to address box. Type 1000 for «Amount» box.
Do not select «Subtract fee from amount» checkbox. Send the coin.
						
Now it will take some time until this transaction is confirmed.
						
Let’s move to your VPS.						
						
Masternode Installation
						
Login to your VPS server with root user. 

We recommend http://digitalocean.com for your VPS and Ubuntu OS 

Run following commands from console:

(**FOR UBUNTU 14.04**)
						
apt-get install wget -y

wget https://raw.githubusercontent.com/banq-platform/MN-Setup/master/install.sh 

chmod 740 install.sh

./install.sh

						
Now it will take some time. Wait until : «GOOD LUCK». It will also print masternode private key as: «Masternode private key:». Save that somewhere, you will use it later.
						
Now come back to your wallet in your PC.
					
Set Masternode config		

Now hopefully your transaction to yourself has been confirmed. 		

Go to Tools → Debug Console						 								
In text box below run the following command:	

masternode outputs

It should print something like this: 
{“a61877d567694a5f050cfbca8104e53e349076149af7cb6c37e013e62565377f”:“1”}
						
The long string is the transaction id of your payment and the number is transaction ID . You will use them shortly.
						
Go to Tools → Masternode configuration file. It will open your masternode config file.
						
Take # out and change in accordingly - Label vps_ip:7717 masternode_priv_key trx_id_of_your_payment trx_ID
																	 								
Note that each data is separated by space, so do not introduce any space yourself.
		
Remember that transaction id and index do not contain any quotes
		
Save and close the config file. Restart the wallet.
			
Go to «Masternodes» tab. You should see your configured masternode as missing. Click on «Start All». Now you should see your masternode as «Pre_Enabled» or «Enabled»
If so, you are all set. It will start getting rewards in around 24 hours.
											 						
You are all set, GOOD LUCK.
