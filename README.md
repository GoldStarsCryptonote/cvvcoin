Copyright (c) 2009-2019 Bitcoin Developers
Copyright (c) 2013 Darkcoin Developers
Copyright (c) 2019 CvvCoin Developers

What is CvvCoin?
----------------

CvvCoin (CVV) is a peer-to-peer and business-to-business cryptocurrency designed 
with a long-term vision in mind. We are determined to create a resilient digital 
currency that will play a pivotal role in the digital finance macrocosm of the 
future due to being built upon solid programming design and advanced financial 
technology with genuine usability and merchant integration.

CvvCoin is based on darkcoin and bitcoin and uses X11 as proof-of-work algorithm.

 - 1 minute block target
 - Reward Maturity: 21 blocks
 - 1 Day or 10000 blocks to retarget difficulty
 - P2P Port: 10108
 - RPC Port: 10109


License
-------

CvvCoin is released under the terms of the MIT license. See `COPYING` for more
information or see http://opensource.org/licenses/MIT.


Get Started
-----------

1. For Linux: You can use both GUI and CLI version of CvvCoin depending upon your needs.

We recommend any stable version of Ubuntu 16.04


 1.1 Installing Dependencies 

Open the terminal and run following commands one by one:


sudo apt-get install git

sudo apt-get install build-essential libtool autotools-dev automake pkg-config libssl-dev libevent-dev bsdmainutils

sudo apt-get install libboost-system-dev libboost-filesystem-dev libboost-chrono-dev libboost-program-options-dev libboost-test-dev libboost-thread-dev

sudo apt-get install libboost-all-dev

sudo apt-get install software-properties-common

sudo add-apt-repository ppa:bitcoin/bitcoin

sudo apt-get update

sudo apt-get install libdb4.8-dev libdb4.8++-dev

sudo apt-get install libminiupnpc-dev

sudo apt-get install libzmq3-dev

sudo apt-get install libqt5gui5 libqt5core5a libqt5dbus5 qttools5-dev qttools5-dev-tools libprotobuf-dev protobuf-compiler 

sudo apt-get install libqt4-dev libprotobuf-dev protobuf-compiler


 1.2 Giving Permissions

Once you have installed all dependencies, next step is to give read write and execute permissions to CvvCoin folder. For that, go to the directory where CvvCoin folder is located and then do:

sudo chmod -R 777 CvvCoin/


 1.3 Compilation

After sucessfully giving all permissions, go to CvvCoin folder and run:

cd src && make clean -f makefile.unix && make -f makefile.unix

It will take a while depending upon your system's hardware configuration (RAM and Processor)


 1.4 Running CvvCoin CLI

Once compilation successfully ends, you can run CvvCoin daemon with following steps:

a) Make sure you are in src folder of CvvCoin ( your_directory/CvvCoin/src )
b) Run: ./CvvCoin -daemon
c) The above comamnd will create "data directory for CvvCoin"(.CvvCoin folder) in your home folder. And will flash an error message:

(The error message flashes for the first time only, not for subsequent uses)

Error: To use the "-daemon" option, you must set a rpcpassword in the configuration file:
/home/your_linux_username/.CvvCoin/CvvCoin.conf
It is recommended you use the following random password:
rpcuser=CvvCoinrpc
rpcpassword=some_long_password
(you do not need to remember this password)
The username and password MUST NOT be the same.
If the file does not exist, create it with owner-readable-only file permissions.

d) Run: touch /home/your_linux_username/.CvvCoin/CvvCoin.conf
e) Run: nano /home/your_linux_username/.CvvCoin/CvvCoin.conf
NOTE: Replace "your_linux_username" in above commands with your own linux username

f) Copy rpc credentails from error message to CvvCoin.conf file and save.
g) Run: ./CvvCoin -daemon ( This time there won't be any error message )
h) Run: ./CvvCoin getinfo (To check conenction status, blocks and other information)
You have a running CLI wallet now

i) Refer to cli-commands for more information.

 1.5 Running CvvCoin-qt (Linux GUI Wallet)

After successfully comiling CvvCoin CLI, you can proceed for CvvCoin-qt Wallet

a) Make sure you are in CvvCoin's root directory ( your_directory/CvvCoin)
b) Run: qmake
b) Run: make
c) You will see GUI wallet being complied on your screen, it will take some time.
d) Once compilation ends, Run: ./CvvCoin-qt
e) You will see an CvvCoin-qt icon in your CvvCoin's root Directory, use that for subsequent uses.

Enjoy your GUI wallet


2. For Windows: GUI client is available.

2.1 Use the setup file to install CvvCoin GUI Wallet

2.2 Default Location of CvvCoin's root Directory in Windows is:
    
    32-bit: Program Files/CvvCoin
    64-bit: Program Files (x86)/CvvCoin

2.3 Data Directory is located at: Users/your_windows_user/AppData/Roaming/CvvCoin


3. CLI Commands (for linux)

3.1 Make sure you are in src folder of CvvCoin ( your_directory/CvvCoin/src )

3.2 Run daemon: ./CvvCoin -daemon
    (It will take some time, press Enter key if it's too long)

3.3 Run given CLI commands to use your CLI Wallet:

a) Check you CLI Wallet's Status: ./CvvCoin getinfo

b) Check your Wallet's Balance: ./CvvCoin getbalance

c) Check number of Nodes you are connected to: ./CvvCoin getconnectioncount

d) Display Detailed information of Connedted Nodes: ./CvvCoin getpeerinfo

e) Generate New Address for Wallet: ./CvvCoin getnewaddress

f) Send some CVV amount to an CVV address: ./CvvCoin sendtoaddress <CVV Address> <Amount>
   example: ./CvvCoin sendtoaddress iVFWg6saZ4L6yvaJso14y2YpRD5hGPNVEL 0.999

g) View all transactions in your wallet: ./CvvCoin listtransactions

h) Encrypt CLI and GUI Wallet: ./CvvCoin encryptwallet <passphrase>
   example: ./CvvCoin encryptwallet thehard*&password!!

i) Unlock CLI Wallet for given time (in seconds): ./CvvCoin walletpassphrase <passphrase> <timeout>
   example: ./CvvCoin walletpassphrase theahard*&password!! 90

j) Change Wallet Passphrase: ./CvvCoin walletpassphrasechange <oldpassphrase> <newpassphrase>
   example: ./CvvCoin walletpassphrase thehard*&password!! thenew%^password

