# Definition

Bitcoin hodls is a hodl quantity that a given unspent bitcoin transaction output has. It requires a wallet soft-fork and some analysis over the blockchain data, particularly over the transaction-chains hidden inside of it - then the user's hodl units (and their price) could be optionally shown.

# Creation function

A hodl is produced when a user timelocks their own unspent transaction outputs - he forbids himself of transfering it, thus the unit name. From that satoshi ammount and (block)time duration, some hodl quantity is created according to some function.
The function (satoshi: i64, duration: u64) => satoshi * duration/2016u64 looks simple enought to me (where 2016 is the bitcoin's dificulty's recalculation cycle period; the return value could be u128 bits).

# Explanation

Pieces of gold may be pure or diluted, metals may be bright and colored or grey, batteries may be charged or empty, tuna may be fat or slim, and game characters may be experienced or a newbie. We can apply the same kind of concept in various ways into bitcoin, and one of those is the result (or appearance) of the hodl quantity.
Just like gold purity, it's part of the piece's characteristics. Sure players aren't required to *not ignore* any characteristic they want to. But again, just like gold purity, the hodl quantity is one characteristic - like a "physical" one -  that does exists, whether we choose to ignore it or not. This is because all value is subjective, and bitcoin must be, entirely, be reasoned about (subjectively interpreted) - or it's nothing more than numbers at random that have no meaning within themselves.

So I'll let myself name hodl units as *bitcoin charges*, and timelocking as *charging*.

# Usage

A charge quantity is attached to each bitcoin transaction's output. For simple init, it's on the bitcoin itself. So if I charged one bitcoin for a a difficulty cycle period, that bitcoin has 1 *charge * bitcoin/satoshi* units. If I send you that bitcoin, you've got a bitcoin plus it's charges. Other usecases are discussed later.

## Impact (subjective)

The appearance of charges fits well with the hodlers position regarding bitcoin trading. It's also a chance to have this kind of extra valuation from that very positioning.

What is objective though is the possibility of dismissing the homegeonity of bitcoin units. If ever desired by bitcoin users, they may (even only temporarily) increase their subjective price valuation over charge units in order to fight an eventual and suspeciously strong short positioning of cash settled bitcoin futures beign traded. Those future trades will start to lose purpose if some of the subjective valuation jumps into bitcoin charge units. This would make it impossible for a cash settled future market to exist, they'd be forced to use bitcoin itself, and this could, at some point, be important to the network.

In fact, a decision to charge your bitcoins is a partial "future trade" decision, where you take the price variance risk but get the charged units in return. That is, you may bet the unit's price will be superior to the price of the risk of not being able to move your bitcoins for some time.

## Lightning Network combination

Since bitcoins in Lightning Networks are timelocked, they may also charge bitcoins, so the two could fit well together. This is why I preffer calling hodls as charges.

## Other transfer usecases

Charge units aren't really on bitcoins but on unspent transaction inputs/outputs. So if I gave you a bitcoin + 10 charges, you may split that bitcoin in half (thus also splitting the charges units in some way). Also, you may receive bitcoins (as a single unspent output) from various inputs (thus merging inputs means merging charges in some way).

### Transaction function

For a given transaction, to sum the input charges and then to equally distribute them according to each output satoshi ammount looks simple enought to me. That is, if bitcoins were electrically charged metal balls, you just group them altogether before merging and splitting into the outputs holes (they would end up with the same charge density).

#### Miners

1. fee transactions have no charges since they are not an output, so a given transaction bitcoin fee appeal won't be changed;
2. only them may increase a bitcoin's charge density, when mining a block with a private transaction that uses a desired (high) ammount of fee rate. I expect that a fixed density would be desired for some traders;
3. some will decide to create create fee-only private transactions. This would fully separate the charges from the bitcoins, but the charges would have nowhere to go. So another cryptocurrency could be created out of that, where it has a charge-only currency and requires some reading over the bitcoin's blockchain data (a parasyte blockchain).
4. if a charge decrease is desired, negative fee rate could be allowed (hardfork in bitcoin), where the transaction's output comes from the coinbase - so only miners would still be able to do that.

So even without a node/miner soft/hardfork, miners still have a (optional) specific function and their user behaviour might be impacted.

# light node

Since the chaining of transactions inputs and outputs must be analysed, initially the full blockchain must be read, but read spent output can be prunned away. So a data structure can be layered on top of the blockchain, containing the unspent output's charges information. So the ~60Mtx (according to https://blockchain.info/charts/utxo-count), would consume ~3GB of information (32B txID, 1B outputID, 4B charges), or a light node.

---

I hope you enjoyed!
