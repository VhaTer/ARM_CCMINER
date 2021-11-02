# Quick Guid on Android Mining For VerusCoin Users

Note that their are already two Smartphones Miners applications out for Ios and Android that save you time and worth a try 

 
`VerusCoinMiner9000` For Android smatphone and tablettes by @sh
Get it [Here](https://docs.verus.io/economy/start-mining.html#mobile
) Or [Here](https://github.com/shmutalov/VerusMiner9000/releases
)



`CCminer-IOS` ,The IOS version brought by @MR-Bossman aka #Jess , Head up to  his github repo [here](https://github.com/Mr-Bossman/CCminer-IOS/releases) and follow  all the Instructions on the readMe file carefully  


There are two others methods (or more?), to compile ccminer on Android:

1 - By installing a Linux distribution with help of [Termux + proot-distro](https://medium.com/veruscoin/mining-veruscoin-on-smartphone-208dbb06905f) explained on the article 

2 - By compiling without any chrooted Linux distribution , using just `termux` the android terminal emulator.



This document try expand and explains the second way.

before we start compiling `ccminer` we need to install `Termux` obtain Termux builds from F-droid [](https://f-droid.org/packages/com.termux/)

Do not install it from Google Play.according to termux wiki
"_scroll down to apk link no need to install f-droid_"

You can Also Obtain  termux apk on the release section under "Asset" [here](https://github.com/termux/termux-app)

We need to install additional dependency pakages,
Run following commands inside the termux shell

```pkg install automake build-essential curl git gnupg openssl nano```

Install a GCC

I can't build the ccminer with clang that default compiler which comes with Termux (and Termux makes clang as alias for gcc). Also,
Termux deprecated a real gcc compiler tools,
so we need to use Its-Pointless Termux repo, to install gcc from it.

Run the following command, to set-up Its-Pointless Termux Repo:

```curl -s <https://its-pointless.github.io/setup-pointless-repo.sh> | bash```

Then we need to install gcc-6 (or gcc-7, gcc-8, gcc-9, gcc-10) package:

```pkg install gcc-6```

(or pkg install gcc-7, pkg install gcc-8, pkg install gcc-9, pkg install gcc-10, it depends on the Android version you are running)

- Step 4 :

Build Clone the ccminer git repo (ARM branch):

git clone --single-branch -b ARM <https://github.com/shmutalov/ccminer.git>

Then change the current directory:

cd ccminer

To build ccminer from sources we need to switch the default clang compiler to the gcc we installed on step 3 by
executing following commands:

```setupgcc-6```

(or setupgcc-7, setupgcc-8, setupgcc-9, setupgcc-10)
and then (to make configure process happy)

```setup-patchforgcc```

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

