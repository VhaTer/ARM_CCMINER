---
permalink: /docs/quick-guid
---

# How to compile on Android

'NOTE: Tested on rooted Android 6
      and a non rooted huwai p20 lite Android 9'

There are two methods (or more?), to compile ccminer on Android:

By installing a Linux distribution with help of Termux + proot-distro: <https://medium.com/veruscoin/mining-veruscoin-on-smartphone-208dbb06905f>

By compiling without the any Linux distribution, purely on the system.
This document explains the second way.

- Step 1 :  Install the Termux

Download and install the Termux application. Open the Termux after install. Next steps we need to do inside it.

- Step 2 :  Install the dependency packages

        Run following command, to install the development dependencies:

```pkg install automake build-essential curl git gnupg openssl nano```

- Step 3 : Install a GCC

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

After successful build you can run built ccminer binary file to start the mining
