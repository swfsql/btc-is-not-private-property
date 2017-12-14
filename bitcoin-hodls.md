# Definition

Bitcoin hodls is a hodl quantity that a given unspent bitcoin transaction output has. It does not require a code fork, nor a data change over the blockchain data. It's simply a new (additive) subjective perspective over the blockchain, particularly over the transaction-chains hidden inside of it. At most, wallets could be adapted (featured) to show how many Bitcoin hodls it's user (or any address) has.

# Creation

A hodl is produced when a user locks (timelock) their own unspent transaction outputs. He forbids himself of transfering it, thus, a hodler for certain. For each mined block that happens during the certain hodling period, each locked satoshi procudes a hodl.

# Explanation

Pieces of gold may be pure or diluted, metals may be bright and colored or grey, batteries may be charged or empty, tuna may be fat or slim, and game characters may be experienced or a newbie. We can apply the same kind of concept in various ways into bitcoin, and one of those is the result (or appearance) of the hodl quantity.
Just like gold purity, it's part of the piece's characteristics. Sure players aren't required to not ignore any characteristic they want to. But again, just like gold purity, the hodl quantity is one characteristic - like a "physical" one -  that does exists, whether we choose to ignore it or not. This is because all value is subjective, and bitcoin must be, entirely, be reasoned about (subjectively interpreted) - or it's nothing more than numbers at random, they have no meaning within themselves.

# Usage

A hodl quantity is attached to each bitcoin transaction's output. For simple init, it's attached to a bitcoin itself. So if I hodl'd (timelocked, in this case) one bitcoin for a block, that bitcoin created 1 hodl*bitcoin*block/(satoshi*block) units (in hodl). If I send you that bitcoin, you've got a bitcoin plus "it's" hodl units. Other transfer usecases are showed later.

## Impact

The appearance of hodls fit's well with the hodlers position regarding bitcoin trading. It's also a chance to have this kind of extra valuation from that very positioning. But this is quite subjective.

What is objective though is the possibility of dismissing the homegeonity of bitcoin units. If ever desired by bitcoin users, they may (even only temporarily) increase their subjective price valuation over hodl units in order to fight an eventual and suspeciously strong short positioning of cash settled bitcoin futures beign traded. Those future tardes will start to lose purpose if some of the subjective valuation jumps into bitcoin hodl units. This would make it impossible for a cash settled future market to exist, they'd be forced to use bitcoin itself, and this could be important to the network at some point.

In fact, a decision to produce hodl units is a partial "future trade" decision, where you take the price variance risk but get the hodls in return.

## Lightning Network combination

Since bitcoins in Lightning Networks are locked, depending on the lock type, they may also produce hodl units, so the two could fit well together. You could consider your bitcoins are "charging up" while timelocked in a lightning contract! Isn't that just sweet?

## Other transfer usecases

Well, hodl units aren't really on bitcoins but on unspent transaction inputs/outputs. So if I gave you a bitcoin + 10 hodl units, you may split that bitcoin in half (thus also splitting the hodl units in some way). Also, you may receive bitcoins (as a single unspent output) from various inputs (thus merging inputs means merging hodls in some way).

I think it's sensate and practical, in a given transaction, to sum the hodls of each input, to have the merged hodl quantity, and then to split this merged quantity into each output, proportionally to the bitcoin quantity beign transfered.
Therefore any bitcoins spent as fees have no hodl quantity attached to it, since it's not formally a transaction's output. If that's the case, miners wouldn't change how they determine which transaction get's confirmed and which doesn't. And it would be crystal clear that this change doesn't regard miners.

# helper structure

So it could be quite helpful to build a structure layered on top of bitcoin's blockchain data to compute this information. It takes only one iteration and then needs a lightweight synchronization for new blocks - it can also be prunned. So considering this, I assume lot's of bits could be given when storing the hodl units. But I didn't think about linearity (or lack of) of this information representation storage (int vs float kind of question).

# Calculations and formulas

Besides the type of information decision, there is the "timestep" decision of this increase. To prevent any short term locking & unlocking congestionment, perhaps the timestep should be N blocks, such as N=2016 (same as difficulty re-calculation). Also, to incentivate longer ter holders, the hodl quantity could be less than 1.0 for each satoshi (rounded to zero), and gradually reach that 1.0 rate ammount the longer the holding period is. The same bitcoin reward formula dynamic could be used (starts distant from 1.0, but rapdly reaches it in a decreasing positive slope).
There's no need to calculate for each step (each block). By knowing the first and last blocks during the timelock period, one can just calculate the total ammount of hodl units created. But it's sure usefull to describe the step dynamic.

I hope you enjoyed!
