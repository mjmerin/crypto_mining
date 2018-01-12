How to Mine Ethereum
=======================

# Intro

This guide assumes you have read through [README](README.md) and have the sufficient hardware to begin mining. Ethereum is poised to go up in value very quick and it is my opinion that this is currently one of the best cryptocurrencies to invest and mine. 

# Graphics Cards and Hashrates for Ethereum

#### NVIDIA
1. GTX 1050 TI (75W) (~12 MH/s)
2. GTX 1060 (120W) (~19 MH/s)
3. GTX 1070 (150W) (~25 MH/s)
4. GTX 1070 TI (180W) (~28 MH/s)
5. GTX 1080 (180W) (~21 MH/s)
6. GTX 1080 TI (250W) (~32 MH/s)

#### Radeon
1. RX550 (50W) (~10 MH/s)
2. RX560 (75W) (~12 MH/s)
3. RX570 (120W) (~22 MH/s)
4. RX580 (185W) (~24 MH/s)
5. RX Vega 56 (210W) (~32 MH/s)
6. RX Vega 64 (295 W) (~34 MH/s)

# Getting A Wallet

A wallet is necessary, as it provides a means of receiving any coins you have mined. It has a static address that is used during configuration of the mining programs. Don't lose the password to your wallet and don't lose your wallet. Create backups as needed.

Keep in mind that this is different from a wallet held on an exchange such as Coinbase. 

Download Installer at [Get An Ethereum Wallet](https://github.com/ethereum/mist/releases). Choose the file appropriate for your operating system.

Download the latest release. As of this writing (December 2017), the current release is 0.9.3

It will take several hours to download the blockchain when the program is first run. 

Once the blockchain is fully synced, you'll be asked to choose a network. Choose "USE THE MAIN NETWORK" option. 

Create a password. Do not lose this. It cannot be changed or recovered so once it's gone, you lose it and any funds in your wallet forever. 


# Coinbase Account

There are many exchanges to choose from, but for this guide we will be using Coinbase. 

An exchange account is not neccessary, but it provides a reliable way to convert your mined Ethereum to other currencies supported on the exchange, or back to USD. 
Do not use your Coinbase Ethereum wallet for mining as that address changes periodically.

Visit [Coinbase](https://www.coinbase.com/) to create your account

# Mining

As mentioned previously, there are several miners available. For this guide we will be using Claymore. 

Download the latest at [Claymore](https://github.com/nanopool/Claymore-Dual-Miner/releases). Choose the file appropriate for your operating system. 

Extract the contents 

### Windows

Once extracted, edit the start.bat file

Delete it's contents and put in the following

    setx GPU_FORCE_64BIT_PTR 0
    setx GPU_MAX_HEAP_SIZE 100
    setx GPU_USE_SYNC_OBJECTS 1
    setx GPU_MAX_ALLOC_PERCENT 100
    setx GPU_SINGLE_ALLOC_PERCENT 100

    EthDcrMiner64.exe -epool eth-us-west1.nanopool.org:9999 -ewal wallet_address/machine_nick/email -mode 1

**wallet_address:** Address of the wallet you created using geth. Do not use coinbase ethereum wallet address. 
**machine_nick:**   Give your machine a nickname of your choosing
**email:**          Email you want to be notified at when the miner has a status change

Once again, do not put your coinbase address as it can change periodically and you will lose your mined funds

Double click the start.bat file and you'll be mining!

### Ubuntu

Once extracted, edit the start_eth_only bash script

Delete it's contents and put in the following

    setx GPU_MAX_ALLOC_PERCENT 100
    setx GPU_SINGLE_ALLOC_PERCENT 100

    EthDcrMiner64.exe -epool eth-us-west1.nanopool.org:9999 -ewal wallet_address/machine_nick/email -mode 1

**wallet_address:** Address of the wallet you created using geth. Do not use coinbase ethereum wallet address. 
**machine_nick:**   Give your machine a nickname of your choosing
**email:**          Email you want to be notified at when the miner has a status change

Once again, do not put your coinbase address as it can change periodically and you will lose your mined funds

Execute the edited script on your terminal

# Monitor Mining Progress

The miner will repeatedly output status information to the screen. Keep an eye on your GPU's temperature making sure it does not exceed the manufacturer's maximum temperature specification.

To monitor how much ethereum is being mined, visit https://eth.nanopool.org/account/wallet_address. A minimum of 1 share has to have been mined before any account information can be visible. 