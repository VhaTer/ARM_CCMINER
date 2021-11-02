---
permalink: /index.md/
---
# Quick Guid on Android Mining For VerusCoin Users

The very fastest and easy way made by @shmutalov  (aKa.Lukretsiy) verus community member
is the `VerusCoinMiner9000` application no more.

You can Get the `.apk` from :

       [official Verus Project Website](https://docs.verus.io/economy/start-mining.html#mobile)

       [from Github](https://github.com/shmutalov/VerusMiner9000/releases)



someone make a apk install and configuration blahblahblah ......


## Alternatives:

There are two methods (or more?), to compile ccminer on Android:

1 - By installing a Linux distribution with help of [Termux + proot-distro](https://medium.com/veruscoin/mining-veruscoin-on-smartphone-208dbb06905f)

2 - By compiling without any chrooted Linux distribution , 
    using just `termux` the android terminal emulator.
    This document try expand and explains the (2) second methode.


Prerequests: 

First obtain Termux builds 

- a) From [F-droid](https://f-droid.org/packages/com.termux/)
     "_According to the Termux Wiki Do not install it from Google Play. in addition scroll down to apk link no need to install f-droid_"

- b) From [Github Repository](https://github.com/termux/termux-app) , on the release section under "Asset" 

on first termux usage issue to have an up to date pkgs 

            `pkg update && pkg upgrade`
 
Next step We need to install some additionals dependency pakages 

run the following commands inside the 'same' termux shell

            `pkg install automake build-essential curl git gnupg openssl nano`

Install a GCC
I can't build the ccminer with clang that default compiler which comes with Termux (and Termux makes clang as alias for gcc). Also,
Termux deprecated a real gcc compiler tools,so we need to use Its-Pointless Termux repo, to install gcc from it.
Run the following command, to set-up Its-Pointless Termux Repo:

            `curl -s <https://its-pointless.github.io/setup-pointless-repo.sh> | bash`

After we need to install gcc-6 (or gcc-7, gcc-8, gcc-9, gcc-10) package:

             `pkg install gcc-6` (_or pkg install gcc-7, pkg install gcc-8, pkg install gcc-9, pkg install gcc-10,
                                    it depends on the Android version you are running_)


Build Clone the ccminer git repo (ARM branch):

            `git clone --single-branch -b ARM <https://github.com/shmutalov/ccminer.git> && cd ccmine/`

To build `ccminer` from sources we need to switch the default clang compiler to the gcc we installed on the gcc6 in this case we have the gcc-6 by 
executing following commands:

            `setupgcc-6` (_or setupgcc-7, setupgcc-8, setupgcc-9, setupgcc-10_)
            
and then (to make configure process happy)

            `setup-patchforgcc`

We can now run the build script to start compile ccminer :

            `./build.sh`  
