# Description
* Arionum CPU miner implemented in C++
	* based on a modified version of phc-winner-argon2, libcurl, libopenssl and gmp / mpir
	* can be a little bit faster than java miner (up to 4% faster on Windows10)
	* dev fee: first share, then 0.5% of next shares found (1 on 200, randomly)
	* only pool mining for now (no solo mining)
* There are 3 versions, slowest to fastest:
	* ariocppminer: for older cpu not supporting AVX
	* ariocppminer_avx: for cpu supporting AVX
	* ariocppminer_avx2: for recent cpu supporting AVX2

# Download Binaries
* Up to date binaries can be found here:
	* https://bitbucket.org/cryptogone/ariocppminer/downloads/

# Installation / Basic usage
* Windows:
	* unzip the archive to a folder
	* launch one of ariocppminer / ariocppminer_avx / ariocppminer_avx2
	* WINDOWS 32BITS VERSION: a 32bit program can only use up to 3GB memory
	  so this means that you cannot use more than 6 threads on windows 32bits, and probably less if you consider RAM already used by the OS
	  also miner will tend to crash/freeze on win32 system if it uses too much memory for windows taste ...
	  so on win32, it is advised to start testing with only 1 thread and then progressively increase number of threads until finding your sweet spot
	  (you can change the number of threads at 4th line of config.cfg, you need to restart miner once changed)
* Linux:
	* IMPORTANT: first install required packages by running: 
		* ubuntu: sudo apt-get install libssl-dev libcurl3
		* redhat: sudo yum install libcurl-devel gmp-devel openssl-devel
	* unzip the archive to a folder
	* open a terminal
	* use 'cd' command to go into the folder
	* launch ./ariocppminer or ./ariocppminer_avx or ./ariocppminer_avx2 depending on what your cpu supports
* Mac:
	* unzip the archive to a folder
	* launch one of ariocppminer / ariocppminer_avx / ariocppminer_avx2
* On first launch the miner will ask you to enter some informations (ex: your wallet address) in order to create a config file (config.cfg)
* If you want to restart the config process, just delete config.cfg and restart the miner
* The config file uses the same format as java miner, so you can reuse the one you have from it
 
# Advanced usage
* You can pass commandline parameters to the miner, for example (linux/mac terminal):
	* ./arioCppMiner -a wallet_address -p pool_url
* To see all available parameters: 
	* ./arioCppMiner -h
* IMPORTANT:
	* CLI parameters override the values from configuration file
	* if you pass any CLI parameter the first time you launch the miner, it will skip the configuration step (useful for scripted install on a server/VM)

# Building
* git hub repo:
	* https://bitbucket.org/cryptogone/ariocppminer
 * Clone the repository then see instructions in build_win.md / build_linux.md / build_mac.md

# Compatibility
* Windows10 64bits
* Linux 64bits: tested on Ubuntu 16, Xubuntu 17 and Ubuntu 16 server
* MacOs: tested on MacOS 10.13 (High Sierra)
* You can use a tool like CPUZ to check if your system supports AVX / AVX2 and chose the correct exe
* 32bits platforms not supported

# Contact / Reporting bugs
* Email: cryptogone.dev@gmail.com
* Discord: cryptogone#3107
* Report bugs: https://bitbucket.org/cryptogone/ariocppminer/issues
