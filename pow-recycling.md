Was reading this: hackingdistributed.com/2017/02/23/green-blockchains#piecework-recycling-pows

And this looks like a good idea. Under messages or bandwidth flooding, requiring some PoW for simple message passing helps.
One way to have that is to recycle mining. On the other hand, mining tends to be, even if inneficient, maxed out (have higher hashrate than otherwise).

Assume a standard node Std, and a low-end, average joe node Joe. If Joe can afford to do _any_ tx validation, he does; if he can't, he doesn't--just go with the coinbase. Then Joe and Std trade bitcoin addresses public keys, such that:  
**Ja** -> _JA_ {**Ja** is Joe's private key, _JA_ is it's public key}  
**Sa** -> _SA_ {**Sa** is Std's private key, and so on..}  

Then Joe grabs _SA_ and uses it as a private key **Ja'**, so:  
**Ja'** -> _JA'_ {so that "private key" has it's own public key}  
and then:  
**Jb** = **Ja** + **Ja'** {Joe sums his and "his other" private key (on Std's knowledge), getting a new private key}  
**Jb** -> _JB_ {and that has a public key}  
_JB_ = _JA_ + _JA'_ {and such public key is also the sum of _JA_ and _JA'_; learned about this magic from mimblewimble}  

Then Joe may mine and target the coinbase to an address that comes from _JB_. Even if he doesn't mine in time, he keeps mining it, until he gets enought PoW required by Std. Or, he still keeps his best PoW form each mining round, and stashes it, until it's enought PoW as a folded sum of PoW iterations. Also, if he has many connected peers, he may spend each mining round to one of his peers (since each would have a different _SA_ or **Ja'**).

Assuming Joe fails to mine in time, he can still announce Std that round's header, with his best work proof. Since Std has _SA_ or **Ja'**, he also has _JA'_. If they exchanged both _JA_ and _SA_ among each other, Std may verify that _JB_ is indeed _JA_ + _SA_, so it was indeed a work trying to prove to Std (to himself).  
Joe still has **Jb**, whereas Std doesn't, so Joe's rewards should be safe if he actually mines it.  

So each node may track the peers "dedicated" Proof of Work, recycled from mining, as an anti-spam measure.
