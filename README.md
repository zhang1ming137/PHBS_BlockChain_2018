## 1.Introduction  
### 1.1 The argument of expansion of Bitcoin and forks
Different parties need to use common rules to maintain the history of the blockchain. When parties are not in agreement, alternative chains may emerge and fork happens. Forks can be classified as accidental or intentional. Accidental fork happens when two or more miners find a block at nearly the same time. The fork is resolved when subsequent block(s) are added and one of the chains becomes longer than the alternative(s). Intentional forks that modify the rules of a blockchain can be classified as hardfork and softfork. Hardfork broadens the protocol and makes previously invalid events valid. Softfork tightens the protocol and makes previously valid transactions are invalid.
The block size of the BTC network is currently limited to 1MB. This means during congestion, as people compete to confirm their transactions as early as possible, transaction fee may become very expensive (over 30 dollars per transaction). This fact significantly limits the payment ability of Bitcoin and makes it almost impossible to embed smart contracts in Bitcoin network. 
![Image of Transactionfee](https://github.com/zhang1ming137/PHBS_BlockChain_2018/blob/master/Transactionfee.png)
In the bitcoin world, the large miners group represented by Bitmain has monopolized most of the computing power. The developer team Bitcoin Core controls the update rights of the Bitcoin code. There was a heated argument between the two sides around the topic of whether the block size of Bitcoin needs expansion.
The miners' group supports expansion plans for their own interests. Bitcoin Core chose another upgrade solution beyond the expansion - [lightning network(LN)](https://en.wikipedia.org/wiki/Bitcoin_scalability_problem)

The view of most of the bitcoin enthusiasts are somewhere between the two extreme sides - they support expansion, and do not reject the lightning network, but they are afraid of the hard fork that may split the Bitcoin consensus.
Since the conflict was irreconcilable, in August 2017, the development teams of Bitcoin-ABC, ViaBTC and BU designed the hardfork chain of Bitcoin--Bitcoin Cash. Bitcoin Cash is the first meaningful hard fork of Bitcoin in history. The astounding success of the BCH hardfork incentivized a wave of other forks including Bitcoin Gold and Bitcoin Diamond.

### 1.2 Review of the history of Bitcoin forks
Bitcoin Magazine has made a map for 
![Image of History](https://github.com/zhang1ming137/PHBS_BlockChain_2018/blob/master/History.jpg)


## 2.Bitcoin Cash(BCH)   
### 2.1 The Mechanism of BCH
#### 2.2.1 Block Size
#### 2.2.2 Difficulty adjustment mechanism
#### 2.2.3 Segregated Witness(Segwit)
[Segwit](https://en.wikipedia.org/wiki/SegWit) technology in BTC is mainly used for two purposes:
##### 1) Proper expansion
Although the block limit of BTC is 1M, with the increasing of SW adoption rate, the current average block size has reached 1.2M (if everyone uses SW, it can reach 1.4M).
##### 2) Serving Lightning Network (LN)
[Bitcoin scalability problem](https://en.wikipedia.org/wiki/Bitcoin_scalability_problem) makes the deployment of [Lightning Network (https://en.wikipedia.org/wiki/Lightning_Network) very difficult. With the use of Segwit, the problem can be "repair" but must use the SegWit-specific address.
For BCH, the capacity increase brought by SegWit can be completely ignored and the scalability problem is expected to be solved in the upgrades in November 2019. As a result, Segwit technology is of no value to BCH, BCH has remove the technology.
#### 2.2.4 RBF(replace by fee)
[RBF](https://en.bitcoin.it/wiki/Replace_by_fee)in Bitcoin means that if you make a transaction, you can use the RRF function to reissue a transaction to replace the old one and invalidate the old one. With RBF, BTC's zero confirmation transaction becomes 100% unsafe. There have been news before, someone used this feature to steal money.
BCH removed this flawed function when it was first born.
#### 2.2.5 Signature Technology
The signature technology of Bitcoin is ECDSA. However, BCH will add [Schnorr signature](https://en.wikipedia.org/wiki/Schnorr_signature) technology in the May 2019 upgrade. Schnorr signature has a faster signature speed and much smaller signature data.
### 1.2 Review of the history of Bitcoin forks
