# ccminer

Based on Christian Buchner's &amp; Christian H.'s CUDA project, no more active on github since 2014.

Check the [README.txt](README.txt) for the additions

BTC donation address: 1AJdfCpLWPNoAMDfHF1wD5y8VgKSSTHxPo (tpruvot)

A part of the recent algos were originally written by [djm34](https://github.com/djm34) and [alexis78](https://github.com/alexis78)

This variant was tested and built on Linux (ubuntu server 14.04, 16.04, Fedora 22 to 25)
It is also built for Windows 7 to 10 with VStudio 2013, to stay compatible with Windows 7 and Vista.

Note that the x86 releases are generally faster than x64 ones on Windows, but that tend to change with the recent drivers.

The recommended CUDA Toolkit version was the [6.5.19](http://developer.download.nvidia.com/compute/cuda/6_5/rel/installers/cuda_6.5.19_windows_general_64.exe), but some light algos could be faster with the version 7.5 and 8.0 (like lbry, decred and skein).

About source code dependencies
------------------------------

This project requires some libraries to be built :

- OpenSSL (prebuilt for win)
- Curl (prebuilt for win)
- pthreads (prebuilt for win)

The tree now contains recent prebuilt openssl and curl .lib for both x86 and x64 platforms (windows).

To rebuild them, you need to clone this repository and its submodules :
    git clone https://github.com/peters/curl-for-windows.git compat/curl-for-windows


Compile on Linux
----------------

Please see [INSTALL](https://github.com/tpruvot/ccminer/blob/linux/INSTALL) file or [project Wiki](https://github.com/tpruvot/ccminer/wiki/Compatibility)


Compile on FreeBSD
------------------

Make sure you have `gmake` installed from the ports tree. Use `build-freebsd.sh`


CPU ONLY CCminer Verushash2.2 v3.7.0
@monkins1010 monkins1010 released this on 11 Jun 2020 · 12 commits to Verus2.2 since this release

There are 3 active branch names in ccminer github repo:

ARM(for 64bit ARM chips with AES intrinsic)

Verus2.2(standard x86-64 pc's)

Verus2.2gpu(NVIDIA GPUs) Please see: ccminer for NVIDIA GPUS

Note: Replace ARM in the git clone line below with the branchname above you want to use. e.g.
for standard x86-64 CPUS use

--single-branch Verus2.2

Installation instructions:

sudo apt-get install libcurl4-openssl-dev libssl-dev libjansson-dev automake autotools-dev build-essential

git clone --single-branch -b ARM https://github.com/monkins1010/ccminer.git

cd ccminer

chmod +x build.sh

chmod +x configure.sh

chmod +x autogen.sh

./build.sh

Then To Run the miner do the following

branch	Program	Algo	Pool	User	Password	threads	devices
ARM	ccminer	-a verus	-o stratum+tcp://POOLURL:PORT	-u WALLETADDRESS.name	-p password	-t 4	N/A
Verus2.2GPU	ccminer.exe	-a verus	-o stratum+tcp://POOLURL:PORT	-u WALLETADDRESS.name	-p password	N/A	-d 0,1,2
Verus2.2 PC	ccminer.exe	-a verus	-o stratum+tcp://POOLURL:PORT	-u WALLETADDRESS.name	-p password	-t 4	N/A
For example to run 8 threads on a CPU miner do:

ccminer.exe -a verus -o stratum+tcp://na.luckpool.net:3956 -u RWiFDfsyw7kw8ACj4tfPDasMvxH1RWzyhX.name -p x -t 8

Mining on Atomic PI (Atom based)



