# Quick Guid on Android Mining For VerusCoin Users

Their are already two Miners applications out for Ios and Android that save you time and worth a try

- Android :

`VerusCoinMiner9000` For Android smatphones/tablettes made possible by @shmutalov aka Lukeisky Get it [Here](https://docs.verus.io/economy/start-mining.html#mobile
) Or [Here](https://github.com/shmutalov/VerusMiner9000/releases
)

- I0S :

`CCminer-IOS` ,The IOS version brought by @MR-Bossman aka #Jess , Head up to  his github repo [here](https://github.com/Mr-Bossman/CCminer-IOS/releases) and follow  all the Instructions on the readMe file carefully  

-Command Line: 

There are two others methods (or more?), to compile ccminer on Android:
The first methode is  installing a Linux distribution with help of [Termux + proot-distro](https://medium.com/veruscoin/mining-veruscoin-on-smartphone-208dbb06905f) discribed on the article .

The second methode is by compiling `ccminer` on Android natively without any chrooted Linux distribution ,using a Terminal emulator `Termux`

Follow the step by step instructions 

1- Downoad and install `Termux` from F-droid [here](https://f-droid.org/packages/com.termux/)

   or from  the [Github release section under "Asset"](https://github.com/termux/termux-app)


After a succesful install launch the application We are going to Run all the commands inside the termux shell Window so keep it open until the end of compilation.


2- Install additionals pakages

  ```shell
  pkg install automake build-essential curl git gnupg openssl nano
  ```
  
## Compile instructions:

```shell
apt-get install libcurl4-openssl-dev libssl-dev libjansson-dev automake autotools-dev build-essential
```

_if after this command you get this error :
Package libjansson-dev is not available, but is referred to by another package.
This may mean that the package is missing, has been obsoleted, or
is only available from another source
However the following packages replace it:
  libjansson
E: Unable to locate package libcurl4-openssl-dev
E: Unable to locate package libssl-dev
E: Package 'libjansson-dev' has no installation candidate
E: Unable to locate package autotools-dev`_

just remove them from the command and install the aviable or suggested ones like so 

```shell
apt-get install  libjansson automake build-essential
``` 
this may not work on all systemes just try to read the ouput error on the terminal and do some search 

Clone the ccminer git repo (ARM branch):

```shell
git clone --single-branch -b ARM https://github.com/monkins1010/ccminer.git && cd ccminer
```

if you get no errors then you end on the `ccminer folder`,

Make Scripts Executables

```shell
chmod +x build.sh && chmod +x configure.sh && chmod +x autogen.sh
```

buid the miner binarie   

```shell
./build.sh
``` 
if all go fine and End no errors we should find on the folder a fresh ccminer binaries ready for use 

```shell
NOTES :
**apt-get install libcurl4-openssl-dev libssl-dev libjansson-dev automake autotools-dev build-essential**
Reading package lists... Done
Building dependency tree... Done
Reading state information... Done
Package libjansson-dev is not available, but is referred to by another package.
This may mean that the package is missing, has been obsoleted, or
is only available from another source
However the following packages replace it:
  libjansson
E: Unable to locate package libcurl4-openssl-dev
E: Unable to locate package libssl-dev
E: Package 'libjansson-dev' has no installation candidate
E: Unable to locate package autotools-dev`
```
