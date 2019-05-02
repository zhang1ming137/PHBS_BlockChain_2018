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
The people who are not familiar with BCH may only consider BCH as an expanded version of Bitcoin and besides the larger block size, there is nothing special for BCH. However, the most significant change brought by BCH is a decentralized development team which make the evolution of the system realizable. (https://www.bitcoin.com/what-is-bitcoin-cash/). Base on multiple independent developers’s efforts, great innovations and upgrads have been implemented on BCH. As a result, the technical differences between the two have become quite large. The summary of the key differences is below:

#### 2.2.1 Block Size
BTC still maintain the size limit of block at 1M. However, when BCH was first born, the block size was 8M, and later it was upgraded to 32M. The 32M block can handle about 10 million transactions per day, which makes it necessary for BCH to pay only 1 Satoshi/byte in any case. At the same time, 32M is not the limit of BCH. As technology advances and future demand grows, BCH will continue to increase the block size so that users can always use low rate transfers.
#### 2.2.2 Difficulty adjustment mechanism
The difficulty of the BTC is fixed for the 2016 block adjustment (about 2 weeks). This means that If the hush rate has a sudden change, for example only 50% of the previous hash rate is available on the chain, miners need to tolerate for 4 weeks and during this period, lots of transactions won’t be recognized and the network will falter.
The BCH initially used the EDA (Emergency Difficulty Adjustment) mechanism, which was later changed to a more reasonable DAA (difficulty adjustment algorithm) and has been used ever since. The DAA adopts a block-by-block adjustment difficulty algorithm. If the hash rate changes drastically, the DAA can be quickly adjusted. The specific algorithm can be seen in DAA LINK. DAA gurantee the stability of the block and the performance.
#### 2.2.3 Segregated Witness(Segwit)
[Segwit](https://en.wikipedia.org/wiki/SegWit) technology in BTC is mainly used for two purposes:
##### 1) Proper expansion
Although the block limit of BTC is 1M, with the increasing of SW adoption rate, the current average block size has reached 1.2M (if everyone uses SW, it can reach 1.4M).
##### 2) Serving Lightning Network (LN)
[Bitcoin scalability problem](https://en.wikipedia.org/wiki/Bitcoin_scalability_problem) makes the deployment of [Lightning Network] (https://en.wikipedia.org/wiki/Lightning_Network) very difficult. With the use of Segwit, the problem can be "repair" but must use the SegWit-specific address.
For BCH, the capacity increase brought by SegWit can be completely ignored and the scalability problem is expected to be solved in the upgrades in November 2019. As a result, Segwit technology is of no value to BCH, BCH has remove the technology.
#### 2.2.4 RBF(replace by fee)
[RBF](https://en.bitcoin.it/wiki/Replace_by_fee) in Bitcoin means that if you make a transaction, you can use the RRF function to reissue a transaction to replace the old one and invalidate the old one. With RBF, BTC's zero confirmation transaction becomes 100% unsafe. There have been news before, someone used this feature to steal money.
BCH removed this flawed function when it was first born.
#### 2.2.5 Signature Technology
The signature technology of Bitcoin is ECDSA. However, BCH will add [Schnorr signature](https://en.wikipedia.org/wiki/Schnorr_signature) technology in the May 2019 upgrade. Schnorr signature has a faster signature speed and much smaller signature data.
### 2.2 Price parity relationship between BCH and BTC
**A Fact**: Miners typically invest in ASICs, which are hardware implementations of a
particular PoW algorithm. Therefore, they can easily shift or reallocate their hash
rate between blockchains that share the same PoW algorithm. Because BCH shares the same hashing algorithms with BTC, the arbitrage will make the reward of mining between the two types of coin maintain same. This will result the price parity relationship between BCH and BTC.
Because BCH has the same supply and decrease pattern as BTC, the number of coins reward for block creation between BCH and BTC is always equal, now it’s 12.5 per block. Based on this fact, use the historical price and hash rate data of BCH and BTC, we can get the exact reward only from the block creation per EH/s during the past year. Use the formation below:  
Reward from Block Generation=(Price×12.5)/(Total Hash Rate of the Network)

The result indicate that the arbitrage is really exist and most of the time, the reward of BTC is lower than BCH. However, if we take the transaction fee into account, the relationship will be more clear. 
![Image of Reward](https://github.com/zhang1ming137/PHBS_BlockChain_2018/blob/master/Reward.jpg)
 
Considering the generator of the block will get all the transaction fees of the recognized transactions during the period, BCH mast have a higher basic reward of mining to stay the miners. The difference between the basic reward should just be the transaction fees (transaction fees for BCH can be recognized as zero).
Reward of BTC Block Generation+Transaction Fees=Reward of BCH Block Generation
Meaning for the price parity relationship:absolute
The most important thing of the relationship is the mechanism of the like the picture below. The hash rate allocation and the Relative price is measured the formation below: 
Hash Rate Allocation=(Total Hash Rate of BTC)/(Total Hash Rate of BTC and BCH)
Relative Price=(Exchange Rate of BTC to USD)/(Exchange Rate of BCH to USD)
From the picture, we can conclude that the changes in the relative price will led to the reallocation of the hash rate. The change target is mentioned before.
![Image of Hash](https://github.com/zhang1ming137/PHBS_BlockChain_2018/blob/master/Hash.jpg)
