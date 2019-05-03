## Introduction  
### The argument around the expansion of Bitcoin
Different parties need to use common rules to maintain the history of the blockchain. When parties are not in agreement, alternative chains may emerge and fork happens. [Forks](https://en.wikipedia.org/wiki/Fork_(blockchain)#Hard_fork) can be classified as accidental or intentional. Accidental fork happens when two or more miners find a block at nearly the same time. The fork is resolved when subsequent block(s) are added and one of the chains becomes longer than the alternative(s). Intentional forks that modify the rules of a blockchain can be classified as hardfork and softfork. Hardfork broadens the protocol and makes previously invalid events valid. Softfork tightens the protocol and makes previously valid transactions are invalid.
The block size of the BTC network is currently limited to 1MB. This means during congestion, as people compete to confirm their transactions as early as possible, transaction fee may become very expensive (over 30 dollars per transaction). This fact significantly limits the payment ability of Bitcoin and makes it almost impossible to embed smart contracts in Bitcoin network. 
![Image of Transactionfee](https://github.com/zhang1ming137/PHBS_BlockChain_2018/blob/master/Transactionfee.png)
In the Bitcoin world, the large miners group represented by Bitmain has monopolized most of the computing power. The developer team Bitcoin Core controls the update rights of the Bitcoin code. There was a heated argument between the two sides around the topic of whether the block size of Bitcoin needs expansion.
The miners' group supports expansion plans for their own interests. Bitcoin Core chose another upgrade solution beyond the expansion - [lightning network(LN)](https://en.wikipedia.org/wiki/Bitcoin_scalability_problem)

The view of most of the bitcoin enthusiasts are somewhere between the two extreme sides - they support expansion, and do not reject the lightning network, but they are afraid of the hard fork that may split the Bitcoin consensus.
Since the conflict was irreconcilable, in August 2017, the development teams of Bitcoin-ABC, ViaBTC and BU designed the hardfork chain of Bitcoin--Bitcoin Cash. Bitcoin Cash is the first meaningful hard fork of Bitcoin in history. The astounding success of the BCH hardfork incentivized a wave of other forks including Bitcoin Gold and Bitcoin Diamond.

### Review of the history of Bitcoin forks
### Bitcoin Magazine has made a map for the history of forks on Bitcoin as below. The explaination of the items in the map can be access through [Click Here](https://finance.yahoo.com/news/infographic-map-bitcoin-forks-150848824.html)
![Image of History](https://github.com/zhang1ming137/PHBS_BlockChain_2018/blob/master/History.jpg)



## Bitcoin Cash(BCH)   
### The Mechanism of BCH

The people who are not familiar with BCH may only consider BCH as an expanded version of Bitcoin. However, the most significant change brought by BCH is a `decentralized developer team` which make the evolution of the system realizable. [(Bitcoin.com, 2018)](https://www.bitcoin.com/what-is-bitcoin-cash/). Base on multiple independent developers’s efforts, great innovations and upgrads have been implemented on BCH. As a result, the technical differences between the two have become quite large. The summary of the key differences is below:

* Block Size

BTC still maintain the size limit of block at 1M. However, when BCH was first born, the block size was 8M, and later it was upgraded to 32M. The 32M block can handle about 10 million transactions per day, which makes it necessary for BCH to pay only 1 Satoshi/byte in any case. At the same time, 32M is not the limit of BCH. As technology advances and future demand grows, BCH will continue to increase the block size so that users can always use low rate transfers.
* Difficulty adjustment mechanism

The difficulty of the BTC is fixed for the 2016 block adjustment (about 2 weeks). This means that If the hush rate has a sudden change, for example only 50% of the previous hash rate is available on the chain, miners need to tolerate for 4 weeks and during this period, lots of transactions won’t be recognized and the network will falter.
The BCH initially used the EDA (Emergency Difficulty Adjustment) mechanism, which was later changed to a more reasonable DAA (difficulty adjustment algorithm) and has been used ever since. The DAA adopts a block-by-block adjustment difficulty algorithm. If the hash rate changes drastically, the DAA can be quickly adjusted. The specific algorithm can be seen in DAA LINK. DAA gurantee the stability of the block and the performance.
* Segregated Witness(Segwit)

[Segwit](https://en.wikipedia.org/wiki/SegWit) technology in BTC is mainly used for two purposes:
 1) Proper expansion
 Although the block limit of BTC is 1M, with the increasing of SW adoption rate, the current average block size has reached 1.2M (if     everyone uses SW, it can reach 1.4M).
 2) Serving Lightning Network (LN)[Bitcoin scalability problem](https://en.wikipedia.org/wiki/Bitcoin_scalability_problem) makes the deployment of [Lightning Network](https://en.wikipedia.org/wiki/Lightning_Network) very difficult. With the use of Segwit, the problem can be "repair" but must use the SegWit-specific address.
For BCH, the capacity increase brought by SegWit can be completely ignored and the scalability problem is expected to be solved in the upgrades in November 2019. As a result, Segwit technology is of no value to BCH, BCH has remove the technology.
* RBF(replace by fee)

[RBF](https://en.bitcoin.it/wiki/Replace_by_fee) in Bitcoin means that if you make a transaction, you can use the RRF function to reissue a transaction to replace the old one and invalidate the old one. With RBF, BTC's zero confirmation transaction becomes 100% unsafe. There have been news before, someone used this feature to steal money.
BCH removed this flawed function when it was first born.
* Signature Technology 

The signature technology of Bitcoin is ECDSA. However, BCH will add [Schnorr signature](https://en.wikipedia.org/wiki/Schnorr_signature) technology in the May 2019 upgrade. Schnorr signature has a faster signature speed and much smaller signature data.
### Price parity relationship between BCH and BTC
`A Fact:` Miners typically invest in ASICs, which are hardware implementations of a
particular PoW algorithm. Therefore, they can easily shift or reallocate their hash
rate between blockchains that share the same PoW algorithm[(Bissias, Levine & Thibodeau, 2018)](https://arxiv.org/pdf/1806.07189.pdf). Because BCH shares the same hashing algorithms with BTC, the arbitrage will make the reward of mining between the two types of coin maintain same. This will result the price parity relationship between BCH and BTC.
Because BCH has the same supply and decrease pattern as BTC, the number of coins reward for block creation between BCH and BTC is always equal, now it’s 12.5 per block. Based on this fact, use the historical price and hash rate data of BCH and BTC, we can get the exact reward only from the block creation per EH/s during the past year. Use the formula below:  
![Image of formula1](https://github.com/zhang1ming137/PHBS_BlockChain_2018/blob/master/formula1.png)

The result indicate that the arbitrage is really exist and most of the time, the reward of BTC is lower than BCH. However, if we take the transaction fee into account, the relationship will be more clear. 
![Image of Reward](https://github.com/zhang1ming137/PHBS_BlockChain_2018/blob/master/Reward.jpg)
 
Considering the generator of the block will get all the transaction fees of the recognized transactions during the period, BCH mast have a higher basic reward of mining to stay the miners. The difference between the basic reward should just be the transaction fees (transaction fees for BCH can be recognized as zero).

`Reward of BTC Block Generation+Transaction Fees=Reward of BCH Block Generation`

The most important thing of the relationship is the mechanism of the like the picture below. The hash rate allocation and the Relative price is measured the formula below: 
![Image of formula2](https://github.com/zhang1ming137/PHBS_BlockChain_2018/blob/master/formula2.png)
From the picture, we can conclude that the changes in the relative price will led to the reallocation of the hash rate. The change target is mentioned before.
![Image of Hash](https://github.com/zhang1ming137/PHBS_BlockChain_2018/blob/master/Hash.jpg)
#### `Significance of the realtionship:`
* because of the relationship, the sudden change of the relative price change will result to the reallocation of the hash rate. For BCH it’s not a problem because the DAA of BCH is update every block. However, things are different for BTC. The difficult of BTC changes every 2016 blocks which is about two weeks, during this period, the sudden and severe negative change in the relative price of BTC will result the generation time of Bitcoin increase significantly and have an impact of experience of the users. 
*	When congestion happens and the transaction fees goes up, mining BTC will be more profitable and drive the miners shift their hash rate to BTC mining pool. When the difficult is stable, this will increase the efficiency of BTC and cut down the transaction fees. In conclusion, the relationship makes the operating of BTC much more flexible. 
 
## Why BCH is the special one?
After the meaningful success of BCH, a wave of forks comes. In a short time, more than 100 different fork coins of Bitcoin emerges such as Bitcoin Gold and Bitcoin Diamond. However, `when the wave pass, only BCH still be active`. The below characters of BCH may explain this result:

* BCH represent the interests of miners

BCH use the same hashing algorithm as BTC, which means that the miners of BTC can transfer their caculation ability to BCH freely. Because the total market cap of BTC and BCH is larger than the BTC before hand fork, introduction of BCH increase the return of miners in fact. The other fork coins based on the other hash algorithm like Bitcoin Gold (BTG) which based on GPU mining actually damage the interests of existing miners. As a result, BTG can't gurantee the effective block generation and was abandoned by the community. Supports of miners gurantees the stability of BCH.
* Inclusiveness carried by decentralized developing team

BTC's development team is relatively single, only Bitcoin Core, and BCH's development team comprised of five technical teams: Bitcoin XT, Bitcoin Classic, Bitcoin Unlimited, Bitcoin ABC, and Bitprim, which solves the development centralization of Bitcoin and brings the most important advantage of BCH: **BCH can do very important, and very useful technology upgrades which is not feasible for BTC**. This comprehensive, developed, and rapid roadmap for technology upgrades will constitute a significant advantage for BCH. 
* Symbolic meaning

As the first meaningful success of hardfork is a priceless sybolic meaning for BCH. Although BTC has lots of drawbacks, as the first currency based on blockchain, no one can threat the dominate status of BTC. BCH has the familiar effect
* Acceptance by Retailers 

The features like no congestion, low transaction fees of BCH makes it very attractive for the payment prictice. The number of online retailers accepting bitcoin cash (BCH) has swelled to more than 945 stores in the last few months[(Bitcoin.com, 2019)](https://news.bitcoin.com/over-900-retailers-worldwide-now-accept-bitcoin-cash/). Increasing acceptance of BCH by retailers will create stickiness and generate the value basis of BCH.  

## Applications of BCH
In the development process of BCH for more than one year, many excellent related applications have emerged. However, for some reason, the usage of most applications is not ideal, and some even fade out of the vision of the BCH community. At the same time, some applications have not been abandoned, the creators are trying to change the version, and the number of users is constantly increasing, such as Cointext (quick transfer without Internet) , Memo（decentralized social software） and Yous（high-quality contents social network）[(ChainNews, 2018)](https://www.chainnews.com/articles/367885872901.htm). Whether or not these applications will continue to survive in the future, it is a meaningful attempt for BCH, because they at least let everyone see some of the potential possibilities of BCH. At the same time, these applications were developed spontaneously by community developers in the absence of funding and technical supporting. This performance has been excellent

### [Cointext](https://cointext.io/)
#### Project Description
Cointext provide a service that using SMS to encrypt cryptocurrencies with any type of mobile phone without the Internet. Cointext does not require accounts, passwords, Apps or complex cryptographic currency addresses. Anyone can get a Cointext wallet by sending the word RECEIVE to the access number in their area, or when another user sends money to their phone.
#### Mechanism
* Recharge：

When the user sends a SMS `Receive` to one of the phone numbers of CoinText (for example `16666666666`), CoinText will return a SMS to him and tell him the recharge address. During this process, CoinText will use the user's mobile phone number as a parameter to generate a BCH private key and the address based on the specific algorithm on the CoinText server. Because the phone number is definitely unique and cannot be repeated, it is certainly feasible to logically generate a private key with the phone number. The address is then sent back to the user through SMS. Then the user can use the other BCH wallet to recharge to this specific address.

According to CoinText's technical documentation, CoinText will delete the private key one second after generating the private key and address for the user, and will also delete the user's mobile phone number. CoinText's server does not retain the user's phone number and does not retain the user's private key. The user's phone will not save the private key also.

* Send BCH：

When the user finishes the recharge, then he can write a SMS like `Send 0.001BCH18988888888` and send it to `16666666666`. In this way, the user finishes 0.001 BCH delivery to the owner of `18988888888`. 

In the above scenario, CoinText first generates (or reproduces) a private key by using the mobile phone number of `18988888888` and then reproduces the private key by using the mobile phone number of the user who sends the money, and then constructs the transaction with the private key of the user who sends the money. Signature to send the BCH to the address corresponding to the private key generated by the mobile phone number 18988888888. `Reproduction of the user's private key is the key technology in the CoinText`. 
* Checks CoinText balance

The user edits SMS `balance` and sends the number `16666666666` to check the balance. The process is that CoinText takes the user's mobile phone number, reproduces the corresponding address through the algorithm, and then uses the blockchain get the balance.

#### Current Situation
The project received a $600,000 Bitcoin Cash (BCH) seed fund led by Yeoman's Capital in July 2018 and currently actives in eight countries: USA, Canada, UK, Australia, South Africa, Netherlands, Sweden And Switzerland. According to the official website data, the amount of the transfer is still within a small range, and the users mostly use the service for promotion of BCH.

### [Memo](https://pypi.org/project/bchmemo/)
**`Project Description:`** BCH-based decentralized social network, similar to Weibo but cannot be deleted. Each piece of information will be recorded in the chain, personal information can not be reviewed through encryption, and the content is written with [op-return](https://en.bitcoin.it/wiki/OP_RETURN).

**`Current Situation:`** When Memo was first launched, the page was relatively simple, with a maximum of 77 characters posted and unavailable for images and video content. Thanks to the BCH network upgrade in May 2018, after several generations of updating, Memo's current posting content can reach 217 bytes. In addition to the increased text content sent, Memo can also becomes available for animations and even videos. 
In addition, its developer Andreas Brekken recently launched a Memo Enhancement Suite (MES) protocol that allows users to customize the Memo application. Open source enables users to update their layouts and provide the ability to "like" posts. MES can remember what users like and their profile passwords. Passwords are stored in plain text in the browser's localStorage, unless the computer has a hardware problem, the password is secure.

### [Yours](https://www.yours.org/)
**`Project Description:`** A social network that can give BCH bonus to article posting, with the goal of improving the quality of web content and allowing users to pay for content they like. The viewer can vote for the high-quality contents with 25 cents per ticket, the money will be paid to the producer of the content and the earlier voter.

**`Current Situation:`** High activity, a large number of original articles are published every day, the content is no longer limited to BCH, but most of the rewards of the related articles is in the forms of BCH. The most profitable articles have a vote of 3512 US dollars.
## Summary
The emergence of BCH solve the problems caused by the 1MB size limit of Bitcoin such as congestion and high transaction fees. Many people think BCH is exactly the real Bitcoin (The intention of BTC is P2P electronic cash system) consider it's low cost. However, the most significant change carried by BCH is the rapid roadmap for technology upgrades. The protocol of BCH update every 6 months and is going to  develop the smart contract founctions and not only focus on a cash system. No one can deny that the value of BCH comes from Bitcoin, however, with topic of blockchain transfer from hype to implemention, the inclusiveness and advance of BCH will make it becomes increasingly recongnized. We can expect more about BCH in the future.
## References
[Bissias G, Levine B N, Thibodeau D. Using Economic Risk to Model Miner Hash Rate Allocation in Cryptocurrencies[J]. 2018.](https://arxiv.org/pdf/1806.07189.pdf)

Bitcoin Magazine.(2019, April 4). A Map of Bitcoin Forks. Retrieved from https://finance.yahoo.com/news/infographic-map-bitcoin-forks-150848824.html

Bitcoin.com.(2019, Jan 2). Over 900 Retailers Worldwide Now Accept Bitcoin Cash. Retrieved from https://news.bitcoin.com/over-900-retailers-worldwide-now-accept-bitcoin-cash/

Chainnews.(2018, July 31). A year after its birth, Bitcoin cash has already had a number of applications. Retrieved from https://www.chainnews.com/articles/367885872901.htm

https://www.bitcoin.com/what-is-bitcoin-cash/ 

