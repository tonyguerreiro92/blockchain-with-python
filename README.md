<h1>Blockchain with Python </h1>

![](https://nu.bootcampcontent.com/NU-Coding-Bootcamp/nu-chi-fin-pt-07-2021-u-c/-/raw/master/02-Homework/19-Blockchain-Python/Instructions/Images/newtons-coin-cradle.jpg)

<h2>Instructions for Wallet</h2>

<p> 
Main focus of a newly founded company is to build a portfolio management system (PMS) that supports both, traditional assets
(like gold, silver, stocks, etc) and currently very hot topic - crypto-assets!!! But, as there are so many coins out there, our task to understand how HD wallets work, and to build out a system that can create them.

## Race to the market: Let the games begin !!!

Unfortunately, there aren't as many tools available in Python for this sort of thing, yet.

Thankfully, there is a command line tool, `hd-wallet-derive` that supports not only BIP32, BIP39, and BIP44, but
also supports non-standard derivation paths for the most popular wallets out there today! 

Indeed, we have to develop and integrate the script `wallet.py` at backend with our dearest old friend, Python.

Once we integrate this "universal" wallet, we can use it to manage billions of addresses across 300+ coins, and it will give
us serious edge against the competition.

In this assignment, we will only need to get 2 coins working: Ethereum and Bitcoin Testnet.
Ethereum keys are the same format on any network, so the Ethereum keys should work with your custom networks or testnets. </p>


<p> Dependencies <p>
   
- PHP must be installed on your operating system (any version, 5 or 7). Don't worry, you will *not* need to know any PHP
  (just in case if `./derive` is not working in comand line, which in my experience happened on Windows machine, we will use it as a    backup in one coding line).

- We have to clone the [`hd-wallet-derive`](https://github.com/dan-da/hd-wallet-derive) tool.

- [`bit`](https://ofek.github.io/bit/) Python Bitcoin library.

- [`web3.py`](https://github.com/ethereum/web3.py) Python Ethereum library.



<p> Set-up Project <p>
  
- Create a project directory called `wallet` and `cd` into it.

- Clone the `hd-wallet-derive` tool into this folder and install it using the instructions on its `README.md`.

- Create a symlink called `derive` for the `hd-wallet-derive/hd-wallet-derive.php` script into the top level project
  directory like so: `ln -s hd-wallet-derive/hd-wallet-derive.php derive`
 
  This will clean up the command needed to run the script in our code, as we can call `./derive`
  instead of `./hd-wallet-derive/hd-wallet-derive.php`.

- Test that you can run the `./derive` script properly, use one of the examples on the repo's `README.md`.

#### NOTE: If one get an error running `./derive`, as it can happen on windows machine then use: `php ./hd-wallet-derive/hd-wallet-derive.php`.

- Create a file called `wallet.py` -- this will be your universal wallet script.

Your directory tree should look something like this:

![](https://nu.bootcampcontent.com/NU-Coding-Bootcamp/nu-chi-fin-pt-07-2021-u-c/-/raw/master/02-Homework/19-Blockchain-Python/Instructions/Images/tree.png)

### Setup constants file to manage coins

- In a separate file, `constants.py`, set the following constants:
  - `BTC = 'btc'`
  - `ETH = 'eth'`
  - `BTCTEST = 'btc-test'`

- In `wallet.py`, import all constants: `from constants import *`

- Use these anytime you reference these strings, both in function calls, and in setting object keys.

### Generate a Mnemonic phrase

- Generate a new 12 word mnemonic using `hd-wallet-derive` or by using [this tool](https://iancoleman.io/bip39/).

- Set this mnemonic as an environment variable, and include the one you generated as a fallback using:
  `mnemonic = os.getenv('MNEMONIC', 'insert mnemonic here')`

### Deriving a wallet

![](/screenshots/derive.png)
![](/screenshots/derive-0.png)
![](/screenshots/derive-1.png)

## Executing test transactions by calling the functions from `wallet.py` 

### BTCTest transaction 

- Fund the account with https://testnet-faucet.mempool.co/

- Do the transactions

![](/screenshots/btc-transaction-1.png)
    
### ETH transaction

- Fund the account with Metamask and Ganache
    
- Do the transactions

![](/screenshots/eth-transaction-0.png)
![](/screenshots/eth-transaction-1.png)







