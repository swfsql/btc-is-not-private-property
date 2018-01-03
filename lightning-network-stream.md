

# draft in progress about Lightning Network

Node bi-directional connections among each other.
Each channel side has a initial quantity locked in the channel.
So the total locked amount is the sum of each side, and each side has a proportion of that total.
Each (/group) Node could represent the same user.
Each user may have a "prefered" proportion for a channel, for a given node, for a given network momentary situation.

For example: if an user expects to receive a lot of money, this user should "prepare" for that receivement.
He could prefer to have a small proportion before receiving the payment, so his channels wouldn't be saturated.
A channel is saturated if one side has the total locked amount. This prevents receivements.
That is, this user should, overall, spend his channeled money.

Another example: if an user expects to both send and receive money of overall in the same ammount, this user could prefer a "balanced" proportion, at half of the total. Because saturation, in this case, tends to be undesired.

With those in mind, flow, flux or stream of payments could facilitate coordination.
If an user want's to have a "balanced" proportion on his channels, he could communicate to his channel-peers that "saturated/empty" (I'm calling "empty" if it's saturated for the opposite side - in a two channels scenario) is undesired, and thus, he's willing to charge zero fees, or even a negative fee rate, over zero-sum (relative to that node) transaction streamming that pushes the proportion closer to the desired amount - in his case, closer to the middle.

With that, an user that wants to stream money to a given destination could be helping other nodes to position themselves, according to their own interests, by looking for the cheapest route, in terms of fee.
It also follows that it's possible for some kind of cyclic routes to form among some nodes, where the route would be zero-sum and beneficial relative to the participant nodes. Mostly, when both sides have a coincidente of lowering the cost for a flow for the same direction.

So I suppose it would work better if everyone's sallaries and consumption payments were streammed.
Just immagine that: you create a payment channel to serve as a "battery" to "store" some savings over a long period of time, by the LN and intended to be spend on the LN, and then "slowly" "upload" some payments from that battery as you use it on your vacation or something. I guess a "right" ammount of sloweness should be cheaper.
