# Definition

Bitcoin hodls is a hodl quantity that a given unspent bitcoin transaction output has. It does not require a code fork, nor a data change over the blockchain data. It's simply a new (additive) subjective perspective over the blockchain, particularly over the transaction-chains hidden inside of it. At most, wallets could be adapted (featured) to show how many Bitcoin hodls it's user (or any address) has.

# Creation

A hodl is produced when a user locks (timelock) their own unspent transaction outputs. He forbids himself of transfering it, thus, a hodler for certain. For each mined block that happens during the certain hodling period, each locked satoshi procudes a hodl.

# Explanation

Pieces of gold may differ in characterists, such as purity. Different metals may have different colors, and different game characters may have different experience/level. We can apply the same kind of concept in various ways into bitcoin, and one of those is the result (or appearance) of the hodl quantity. Just like gold purity, it's part of the piece's characteristics. Sure players aren't required to not ignore any characteristic they want to. But again, just like gold purity, the hodl quantity is one characteristic - like a "physical" one -  that does exists, whether we choose to ignore it or not. This is because all value is subjective, and bitcoin must be, entirely, be reasoned about (subjectively interpreted) - or it's nothing more than numbers at random, they have no meaning within themselves.

# Usage

A hodl quantity is attached to each bitcoin transaction's output. For simple init, it's attached to a bitcoin itself. So if I hodl'd (timelocked, in this case) one bitcoin for a block, that bitcoin created 1 hodl*bitcoin*block/(satoshi*block) units (in hodl). If I send you that bitcoin, you've got a bitcoin plus "it's" hodl units. Other transfer usecases are showed later.

## Impact

The appearance of hodls fit's well with the hodlers position regarding bitcoin trading. It's also a chance to have this kind of extra valuation from that very positioning. But this is quite subjective.

What is objective though is the possibility of dismissing the homegeonity of bitcoin units. If ever desired by bitcoin users, they may (even only temporarily) increase their subjective price valuation over hodl units in order to fight an eventual and suspeciously strong short positioning of cash settled bitcoin futures beign traded. Those future tardes will start to lose purpose if some of the subjective valuation jumps into bitcoin hodl units. This would make it impossible for a cash settled future market to exist, they'd be forced to use bitcoin itself, and this could be important to the network at some point.

In fact, a decision to produce hodl units is a partial "future trade" decision, where you take the price variance risk but get the hodls in return.

## Lightning Network combination

Since bitcoins in Lightning Networks are locked, depending on the lock type, they may also produce hodl units, so the two could fit well together. (but I'm ignorant on the LN stuff)

## Other transfer usecases

Well, hodl units aren't really on bitcoins but on unspent transaction inputs/outputs. So if I gave you a bitcoin + 10 hodl units, you may split that bitcoin in half (thus also splitting the hodl units in some way). Also, you may receive bitcoins (as a single unspent output) from various inputs (thus merging inputs means merging hodls in some way).

I think it's sensate and practical, in a given transaction, to sum the hodls of each input, to have the merged hodl quantity, and then to split this merged quantity into each output, proportionally to the bitcoin quantity beign transfered.
I also think it makes sense to bring hodl units down to zero when the output comes from a coinbase transaction. This will prevent any miner behavioral change regarding transactions fees. And this is not really about miners, it's all about users.

# helper structure

So it could be quite helpful to build a structure layered on top of bitcoin's blockchain data to compute this information. It takes only one iteration and then needs a lightweight synchronization for new blocks - it can also be prunned. So considering this, I assume lot's of bits could be given when storing the hodl units. But I didn't think about linearity (or lack of) of this information representation storage (int vs float kind of question).

I hope you enjoyed!
