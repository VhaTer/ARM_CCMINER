# Quick Guid on Android Mining For VerusCoin Users

Their are already two Miners applications out for Ios and Android that save you time and worth a try

## android icon

`VerusCoinMiner9000` For Android smatphone and tablettes by @shmutalov aka Lukeisky Get ita [Here](https://docs.verus.io/economy/start-mining.html#mobile
) Or [Here](https://github.com/shmutalov/VerusMiner9000/releases
)

### I0S 
`CCminer-IOS` ,The IOS version brought by @MR-Bossman aka #Jess , Head up to  his github repo [here](https://github.com/Mr-Bossman/CCminer-IOS/releases) and follow  all the Instructions on the readMe file carefully  


#### Command Line 

There are two others methods (or more?), to compile ccminer on Android:

The first methode is  installing a Linux distribution with help of [Termux + proot-distro](https://medium.com/veruscoin/mining-veruscoin-on-smartphone-208dbb06905f) discribed on the article .

The second methode is by compiling `ccminer` without any chrooted Linux distribution , using just one application `termux` android terminal emulator.

before we start compiling `ccminer` We need to Downoad and install `Termux`
You can obtain it  from F-droid [here](https://f-droid.org/packages/com.termux/)

_According to termux wiki "Do not install it from Google Play"
scroll down to apk link no need to install f-droid to ;)_

You can Also Obtain `termux.apk` on the [Github release section under "Asset"](https://github.com/termux/termux-app)
After a succesful install launch the application

We need to install some basic additional pakages, like nano , git.
_**Run following commands inside the `termux` shell Windows._
 
``` pkg install automake build-essential curl git gnupg openssl nano```


## Compile instructions:
_**Run following commands inside the `termux` shell Windows._

```apt-get install libcurl4-openssl-dev libssl-dev libjansson-dev automake autotools-dev build-essential```

Clone ccminer/ARM branch repository

```git clone --single-branch -b ARM https://github.com/monkins1010/ccminer.git && cd ccminer```

if you get no errors then you end on the `ccminer folder`,
next run
        ```chmod +x build.sh && chmod +x configure.sh && chmod +x autogen.sh```
to buid our binary run  ```./build.sh```

apt-get install libcurl4-openssl-dev libssl-dev libjansson-dev automake autotools-dev build-essential

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
E: Unable to locate package autotools-dev```
