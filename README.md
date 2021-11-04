Quick Guide on Android Mining For VerusCoin Users
Their are already two Miners applications out for I0S and Android that save you time and worth a try

Android :
VerusCoinMiner9000 For Android smartphones/tablets made possible by @shmutalov aka Lukeisky Get it Here Or Here

I0S :
CCminer-IOS ,The IOS version brought by @MR-Bossman aka #Jess , Head up to his github repo here and follow all the Instructions on the read-Me file carefully

Command Line:
There are two others methods (or more?), to compile ccminer on Android: The first method is installing a Linux distribution with help of Termux + proot-distro described on the article .

The second methode is by compiling ccminer on Android  without any ch-rooted Linux distribution ,using a Terminal emulator Termux

Follow the step by step instructions

1- Download and install Termux from F-droid here

or from the Github release section under “Asset”

After a successful install launch the application We are going to Run all the commands inside the termux shell Window so keep it open until the end of compilation.

2- Install additional packages

  pkg install automake build-essential curl git gnupg openssl nano
apt-get install libcurl4-openssl-dev libssl-dev libjansson-dev
automake autotools-dev build-essential
if after this command you get this error : ` Package libjansson-dev is not available, but is referred to by another package. This may mean that the package is missing, has been obsoleted, or is only available from another source However the following packages replace it: libjansson E: Unable to locate package libcurl4-openssl-dev E: Unable to locate package libssl-dev E: Package ‘libjansson-dev’ has no installation candidate E: Unable to locate package autotools-dev `

just remove them from the command and install the available or suggested ones like so

apt-get install  libjansson automake build-essential
this may not work on all systems just try to read the ouput error on the terminal and do some search

Clone the ccminer git repo (ARM branch):

git clone --single-branch -b ARM https://github.com/monkins1010/ccminer.git && cd ccminer
if you get no errors then you end on the ccminer folder,

Make Scripts Executable

chmod +x build.sh && chmod +x configure.sh && chmod +x autogen.sh
buid the miner binarie

./build.sh
if all go fine and End no errors we should find on the folder a fresh ccminer binaries ready for use .
