# Quick Guid on Android Mining For VerusCoin Users

>Note that their are already two Smartphones Miners applications out for Ios >and Android that save you time and worth a try 

 
`VerusCoinMiner9000` For Android smatphone and tablettes by @sh
Get it [Here](https://docs.verus.io/economy/start-mining.html#mobile
) Or [Here](https://github.com/shmutalov/VerusMiner9000/releases
)



`CCminer-IOS` ,The IOS version brought by @MR-Bossman aka #Jess , Head up to  his github repo [here](https://github.com/Mr-Bossman/CCminer-IOS/releases) and follow  all the Instructions on the readMe file carefully  


There are two others methods (or more?), to compile ccminer on Android:

The first methode is  installing a Linux distribution with help of [Termux + proot-distro](https://medium.com/veruscoin/mining-veruscoin-on-smartphone-208dbb06905f) discribed on the article .

2 - The second methode is by compiling `ccminer` without any chrooted Linux distribution , using just one application the `termux` android terminal emulator.


This document try expand and explains the second way.

before we start compiling `ccminer` We need to Downoad  `Termux` 
You can obtain it  from F-droid [here](https://f-droid.org/packages/com.termux/)

>According to termux wiki "Do not install it from Google Play"

"_scroll down to apk link no need to install f-droid to ;) _"

You can Also Obtain `termux.apk` on the [Github release section under "Asset"](https://github.com/termux/termux-app)

After a succesful install launch the application, now 
We need to install additional dependency pakages,

>Run following commands inside the `termux` shell Windows .

```shell
pkg install automake build-essential curl git gnupg openssl nano
```
```shell
apt-get install  libjansson automake  build-essential
```

Step 4 

git clone --single-branch -b ARM <https://github.com/shmutalov/ccminer.git>

Then change the current directory:

cd ccminer

Then start the build:

```./build.sh```

```
After successful build you can run built ccminer binary file to start the mining




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

