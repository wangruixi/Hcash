Hcash Projects information:
=====================================

The official website of Hcash Https://h.cash

What is Hcash?
--------------

The UTXO-based blockchain system (e.g. Bitcoin) and account-based blockchain system (e.g. Ethereum ) opened the door of a brand-new world for us. Despite facing some drawbacks along the way, the impressive success of Bitcoin and Ethereum has certainly proven the value of the blockchain technology and its massive potential in the future. Since 2015, there has been quite a few highly-promising distributed ledger systems which are not block-based blockchain technology turned up, such as DAG (Directed Acyclic Graph). With no doubt, a decentralized digital world is dawning and Bitcoin or Ethereum has the potential to become the fundamental currency in block-based blockchain system. IOTA or Byteball, on the other hand may fulfil a similar role in a system based upon DAG. Although all blockchain issued tokens can be traded on some exchange platform, they can only circulate within their own blockchain systems. We want to create a new decentralized platform, which will be the connecting point of the major blockchain systems, regardless the block-based or blockless-based blockchain system, hence allowing value and information circulate smoothly within different blockchain system. We call it “HyperCash” or Hcash in short.

Development Process
-------------------

The Hcash is being developed by cryptography labs in one of the China’s most prestigious university as well as other famous universities in Australia. We will periodically update you with the progress on this over time, and we expected the first release upgrade will happen soon at Dec 2017. Thanks for your attention and stay tuned for the further update from Hcash dev team.

Build on Linux
-------------------

update apt get and install addtional libraries

```
apt-get update
apt-get install -y git cmake libboost1.58-dev libboost1.58-all-dev autoconf
```

download code

```
git clone https://github.com/HcashOrg/Hcash.git --recursive
cd ./Hcash
git submodule update --init --recursive
```

building openssl

```
cd dependence/openssl1.0.2/
./config
make -j
sudo make install
```

building miniupnp

```
cd ../miniupnp/miniupnpc
cmake .
make
```

building leveldb

```
cd ../../leveldb
chmod u+x build_detect_platform
make
```

building berkeleyDB

```
cd ../db-5.3.28.NC/build_unix/
chmod u+x ../dist/configure
../dist/configure --enable-cxx
make -j
```

building fc

```
cd ../../fc
export OPENSSL_ROOT_DIR=”/usr/local/ssl/”
cmake .
chmod u+x ./vendor/scrypt-jane/test-speed.sh
chmod u+x ./vendor/scrypt-jane/test.sh
chmod u+x ./vendor/cyoencode-1.0.2/src/build.sh
chmod u+x ./vendor/secp256k1-zkp/configure
chmod u+x ./vendor/secp256k1-zkp/autogen.sh
cd ./vendor/secp256k1-zkp/
./autogen.sh
cd ../../
make
```

building hsrcore

```
cd ../../
cmake .
make
```

Build on Mac
-------------------


install homebrew

```
/usr/bin/ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"
```

install addtional libraries

```
brew update
sudo xcode-select --install
sudo xcodebuild -license accept
brew install cmake
brew install git
brew link --overwrite git
brew install boost@1.57
brew install autoconf
brew install automake
brew install libtool
```

download code

```
git clone https://github.com/HcashOrg/Hcash.git --recursive
cd ./Hcash
git submodule update --init --recursive
```

building openssl

```
cd dependence/openssl1.0.2/
./Configure darwin64-x86_64-cc
make -j
sudo make install
```

building miniupnp

```
cd ../miniupnp/miniupnpc
cmake .
make
```

building leveldb

```
cd ../../leveldb
chmod u+x build_detect_platform
make
```

building berkeleyDB

```
cd ../db-5.3.28.NC/build_unix/
chmod u+x ../dist/configure
../dist/configure --enable-cxx
make -j
```
if build error see https://lists.freebsd.org/pipermail/freebsd-current/2012-May/033615.html

building fc

```
cd ../../fc
export OPENSSL_ROOT_DIR="/usr/local/ssl/"
brew link boost\@1.57 --force
cmake .
chmod u+x ./vendor/scrypt-jane/test-speed.sh
chmod u+x ./vendor/scrypt-jane/test.sh
chmod u+x ./vendor/cyoencode-1.0.2/src/build.sh
chmod u+x ./vendor/secp256k1-zkp/configure
chmod u+x ./vendor/secp256k1-zkp/autogen.sh
cd ./vendor/secp256k1-zkp/
./autogen.sh
cd ../../
make
```

building hsrcore
```
cd ../../
cmake .
make -j3
make
```

License
-------

Hcash is released under the terms of the MIT license. To get more information please refer to  https://opensource.org/licenses/MIT.
