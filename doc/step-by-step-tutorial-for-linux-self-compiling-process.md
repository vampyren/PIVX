# SELF-COMPILING PIVX CORE WALLET FOR UBUNTU 18.04

These are detailed step-by-step instructions on how to self-compile PIVX Core Wallet on Ubuntu Linux 18.04 directly from Master branch.

This tutorial is intended for anyone who is willing to help with testing latest features that PIVX Core Developers are planning to implement on PIVX mainnet. If you find any bugs, please report them directly on PIVX Github:

https://github.com/PIVX-Project/PIVX/issues

---------------------------------------------------------

## Let's start...

Open the terminal (command line) on Ubuntu 18.04. Type in the commands line by line as following:

```sudo apt-get update
sudo apt-get upgrade -y
sudo apt-get install build-essential libtool bsdmainutils autotools-dev autoconf pkg-config automake python3
sudo apt-get install libssl-dev libgmp-dev libevent-dev libboost-all-dev
sudo apt-get install software-properties-common
sudo add-apt-repository ppa:pivx/pivx
sudo apt-get update
sudo apt-get upgrade -y
sudo apt-get install libdb4.8-dev libdb4.8++-dev
sudo apt-get install libminiupnpc-dev
sudo apt-get install libzmq3-dev
sudo apt-get install libqt5gui5 libqt5core5a libqt5dbus5 libqt5svg5-dev libqt5charts5-dev qttools5-dev qttools5-dev-tools libprotobuf-dev protobuf-compiler libqrencode-dev
cd Downloads
git clone https://github.com/pivx-project/pivx.git
cd pivx
./autogen.sh
./configure
make
sudo make install
cd .. && cd .. && cd .. && cd .. && cd usr/local/bin
./pivx-qt
```
--------------------------------------------
**Congratulations, you have successfully compiled and started PIVX Qt Core Wallet!**

After you successfully go through the initial welcome phase and choose the PIVX directory (you can keep default directory), wallet will start loading block files. Quit the wallet now.

We want to use the wallet on **testnet**. Now go to Files within Home folder and in the top right corner you should open Settings and check the `Show Hidden Files` checkbox. This will allow you to see the hidden folders and you will see the `.pivx` folder now. Open it, open pivx.conf file with Text Editor and add exactly:
`testnet=1`. Save the file.

Let's go back now to Terminal (command line) and type again:
```
./pivx-qt
```

**That's it, you can now play around with the latest version of PIVX Core Wallet directly compiled from master branch!**

---------------------------------------------
### COMPILING THE WALLET AGAIN WHEN YOU HAVE THE OLD VERSION ALREADY COMPILED

```
cd Downloads
rm -rf pivx
cd .. && cd .. && cd .. && cd usr/local/bin
sudo rm -f pivx-cli pivxd pivx-qt pivx-tx test_pivx test_pivx-qt
```

Use the next command, but replace the `YOURUSERNAME` with your Ubuntu 18.04 username:

```
cd .. && cd .. && cd .. && cd home/YOURUSERNAME/Downloads
git clone https://github.com/pivx-project/pivx.git
cd pivx
./autogen.sh
./configure
make
sudo make install
cd .. && cd .. && cd .. && cd .. && cd usr/local/bin
./pivx-qt
```

#### **Congratulations, you have successfully compiled and started FRESH PIVX Qt Core Wallet!**
