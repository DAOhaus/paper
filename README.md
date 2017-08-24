# Daohaus

John D. Storey [✉️](mailto:johndangerstorey@gmail.com)

V0.6 - August 6th, 2017

## Table of Contents

[Abstract](#abstract)

[Overview](#overview)

[Definitions](#definitions)

[Token Sale](#token-sale-contract)

[Registrar](#registrar-contract)

[Non Resource Proposal](#non-resource-proposal-contract)

[Resource Proposal](#resource-proposal-contract)

[Member Management](#member-management-contract)

[Secondary Market](#secondary-market-contract)

[Scheduling & Rental](#scheduling-and-rental-contract)

[Version 2 Ideas](#version-2-ideas)

### **Afterword**

[Finances](#finances)

[Policy](#policy)

[Enforcement](#enforcement)

[Footnotes](#footnotes)

---

## Abstract

Daohaus is a social experiment to test pure democratic governance.  The aim is to purchase, manage, and enjoy a single real estate property.  The hope is to use this specific scope to expand and grow the idea into governance of a community, and even a nation.  Hopefully bringing us closer to a more pure, accountable, and representative government.  One that is truly of the people, by the people, for the people. 


    I shall be asked if I am a prince or a legislature to write on politics. 
    I answer that I am neither, and that is why I do so 
    
    -- Rousseau, Social Contract

3 large similarities exist between managing a real estate property, and governing a nation. Namely the creation of rules called laws,the enforcement of those rules, and the management of an escrow account that we all fund through our taxes.

Creating the framework for a property on a much smaller and simpler scale and through basic mechanisms holds an important advantage which is flexibility.  We start small so that we can learn from flaws in the design, build it incrementally, and test our hypothesis as it grows following an Agile <sup id="a1">[1](#f1)</sup> mentality.

Daohaus is essentially built on the idea of it's members submitting proposals to use public funds, and gaining approval from the rest of it's members.  The group is brought together around a specific idea or project, in which they hold a "token launch" allowing others to come onboard and to provide the startup costs needed to purchase the land, house, or whatever shared asset that is bringing them together.  This token is then registered and members are made public along with how much interest they hold in the project.

From there it is up to the community to propose projects, rules, or the removal of bad actors in the system.  In essence, this is pure democratic governance -- but also allows for alternative forms of governance **as long as the people give their consent** and enhances participation, education, and accountability in the way the group is goverened.

Daohaus is a proving ground for the advantages of a "proposal" governance over our current "charasmatic representative" based system. Up to this point it has been a relatively good way to govern, but one that is now becoming outdated and unnecessary with the maturity of certain technologies such as the internet and blockchain.  

Geed, corruption and incompetence cannot be solved by purely technical solutions, but I hope Daohaus will grow into a tool used to combat such evils.  If you'd like to read more of my thoughts on the subject, please see the afterword where I briefly address the implications of this project on our coutries [financial](#financial), [policy](#policy) and [enforcement](#enforcement) practices.

In the same way that the Bauhaus <sup id="a2">[2](#f2)</sup> movement was characterized by a minimalist type of design, we also hope to simplify and minimize governance of shared community assets.

## Overview

In the example below a group of people have already held a token launch for 365 tokens (one for each night of the year) and have already purchased the property.  

Member A proposes to paint the house blue.  The group passes the proposal with a 75% success, the chairman recieves a fee for preparing the proposal and orchstrating the work to be done with the worker doing the actual labor involved in painting the house.

![Bad Actor Diagram](/diagrams/resource-proposal/single.png)

Related, if the proposal doesn't pass and Member A continues to act in way contrary to the group's decesion, then anyone in the group can be put up for review in which the group votes weather to allow them to stay in, pay a fee, or get voted out.  The group then submits a new proposal to fix the issue the previous member created, but has been paid for by the sale of his interest in the group by selling his tokens to Member C. 

![Bad Actor Diagram](/diagrams/overview/bad-actor.png)


## Definitions

**The DAO:**

The group of people that own voting rights within a group. Typically required to pay yearly taxes which will be spent as proposals are received and approved by the members.

**Shared Asset:**

For this particular use case, shared asset will correspond to a single real estate property.

**Member:**

Someone that has registered as a member by sending their tokens to the Registry Contract allowing participation in voting and message boards.


**Registrar Contract:**

The contract where members send their token in order to vote. In order to withdraw member must notify 2 weeks prior, be in good standing, and not have any interest, votes or Chairman responsibilities, in any outstanding proposals.

**Non Resource Proposal Contract:**

A very open ended contract that is used to set "rules" or change variables on the registry contract itself. It's an internal governance tool that is part technical -- for changing of variables -- and part societal in setting common rules that can be referenced by the group when electing to force withdraw someone from the DAO.

**Resource Proposal Contract:**

A separate contract that has set parameters that need to be met in order for proposal to be successful and the transfer of funds to the specified proposal chairman. Contains Description of the proposal, relays votes and tracks progress -- typically of a management task such as "fixing the leaky sink" or "replacing the roof".

**Resource Escrow Proposal Contract:**

This contract allows the creation of a special escrow account in the registrar that holds funds designated for it's future execution.  That way money that has been raised incrementally for a larger community purchase can't be used for another purpose.  For example, the community raises taxes for the building of a school that requires 5 years of payments from it's members.  This structure protects those funds from general resource proposal contracts that take money from the general escrow.

**Member Management Contract:**

The contract in which people nominate others to be "force withdrawn" in cases where the member has been malicious or unsavory to the other members for whatever reason.

**Chairman:**

In most cases this is the address that initialized a specific contract. This responsibility typically denotes setting parameters for a proposal, receiving and distributing funds upon proposal success and can be transferred or voided via popular vote.

**Popular Vote Ratio or PVR:**

The ratio in which a proposal is deemed as accepted. Popular or passing is 4/7ths approval of total votes cast. Meaning if 7 total votes cast, needs at least 4 to be approval, receiving above 58%.  This is a variable that can be changed upon the consent of the members.

**Optional -- The Benevolent Dictator:**

This is an optional position that exists to make sure the group being created is living up to it's purpose.  It has the power to automatically pass or kill any proposal.  This is intended to be used in a system where the BD actually owns the underlying asset and is letting a group of trusted members guide it accordingly. Once satisfied with the organization or dies without assigning an heir, the role ends.

**v2 -- Proxy Member:**

Someone that has been extended the ability to control the token from a different address than from whom the token is registered on the Registry Contract. This will be a nice feature to have but not part of version 1.

## **Token Sale Contract**

The creation of The DAO is the initial step, and probably the most important for the longevity of the group. It is important that the DAO's Chairman clearly communicate what the DAO forming will be centered around or the group will could be divided upon creation and nothing will get done<sup id="a6">[6](#f6)</sup>.

Also important to communicate that the token sale price is not based solely in the underlying asset, but in the experience, the community, the efficiency of the group. Basically the value in going to Harvard is not based solely in the building, coursework, and text books… it’s the network and community you’re introduced to — so although the house might only be worth physically $500,000 - it sells for a $750,000 because everyone likes the group and people want in for social or other reasons.

After a successful funding the Chairman should only have the amount of interest or involvement as their token percentage mandates. This means none of the tokens will be reserved for the development team, and the Chairman should include a fee in the payment structure for orchestrating the creation for compensation.

Each token will be the same across ALL users, both as a symbol of ownership percentage and a right to vote proportionately. This token is not absolutely necessary to hold a position such as chairman, as that role can be specified on creation by whoever is publishing the contract. However, only token holders can nominate, vote for, or remove such people from those positions.

While the landscape of token sales is expanding, and new models are continually being developed and tested, here are a few characteristics and models to consider such as:

**Open Vs Restrictive:**

Open meaning anyone can participate at any level. Restrictive meaning to put limitations on things such as requiring an identification confirmation of some sort and limit each confirmed addresses total amount possible to donate. Anyone trying to remove political factions or immediate majority shareholders would want to employ this method because essentially 1 individual could own 75% of the tokens and practically controll the entire asset.

**Our Model:**

Set bottom price but allow for "bids" to occur rather than outright “sales”.

Each new bid adds 1 additional day -- or other time variable -- each time a new bid is placed. This is the mechanism that penny bids use to protects against “coil and pounce” bidders to place bids right as auction ends.

As soon as all tokens are bid upon, they are not actually sold and higher bids replace the claim on a lower bid. If there is a pool of bids with exact same value, the tokens with the most recent bids are knocked off first in FILO fashion, incentivizing people to act fast.

To counteract the possibility of a never ending project, the Chairman is appointed on launch to enable the contract to execute or close when they feel a general consensus has been reached, but must give 24 hour notification — this requires a solid off chain notification system like sms or email. The Chairman will typically be the team or developer hosting the token sale because they are incentivized to let it grow as high as possible without trolls making it last forever by bidding 1 Wei every 24 hours.

With all that being said, there are many other token sale models, and in the future each new DAO will be able to employ different token sale models as the Chairman sees fit<sup id="a7">[7](#f7)</sup>.

It's variables and functions are:

* **Minimum Price:** The initial price of each token

* **Active:** Default to true, false when Chairman signals close.

* **Total Supply:** Initial supply of tokens, in this case 365

* **Maximum Ownership Share:** The maximum amount that any one address can bid on. This is to prevent against attackers that through purchasing 3/4 of the tokens, now effectively control the asset as if they owned 100% of it.

* **Token Array:** representational array of all 365 tokens. Custom schema to keep track of which address is currently highest bidder, their bid, and the timestamp of when they bid for FILO calculations.

**Withdraw Chairman Fee:** Sends predetermined amount to chairman. Could be a set fee, a percentage, or really any payment schedule that would want to be created.

**Check Eligibility:** if public, this automatically passes. If private, checks to make sure the sender meets defined requirements. In this case it will be if they have been added to a white list after verifying their number or possibly just verifying with uport.

**Bid:** Takes 3 parameters, first is how many tokens they are bidding on and second what they're bid is, third is their contact info (email and/or phone #). Checks to make sure amount is equal to or more than the minimum price. Records the order of the bid (for use in FILO incase higher bids come in) as well as checks that this wouldn't put them over the top established by the maximum ownership share value.

**Execute Sale:** Registers tokens and their percentages with the Registrar Contract. Sends the chairman fee to the chairman, and set's the remainder onto the registrar contract in order to be used as seen fit by the members.

**Signal Close:** Allows chairman to signal that sale will close in 24 hours, believes a consensus has been reached on price of tokens. Set's active to false.

**Refund:** Allows chairman to refund certain addresses should a problem arise.

**Set Deadline:** Called each time a successful bid goes through. Modifier looking to see if still active.

## **Registrar Contract**

The contract where members send their tokens in order to have the right to vote.  Also receives yearly taxes in order to be used towards proposed projects. In order to withdraw their tokens, a member must:

* Give 2 weeks notice
* Be in good standing
* Not be the Chairman on any outstanding proposals. 

The Registry contract is also the enforcer of the law in selling off bad actor's tokens when a member management contract is passed to do so.

Taxing is done on an annual basis per token owned. Taxes need to be paid before the taxation date. If not paid user receives a notification warning them that they are at risk of being forced to withdraw, and then on that date any delinquent addresses are force transferred and the proceeds go into the Registrar Contract to cover taxes.

The reason that the default tax date is at the end of the year is to allow for changes to the tax throughout the year as volatility dictates. If taxes run out because of falling prices, users must propose to change taxes higher, and everyone has till the end of the year to comply. In the other direction, if prices soar then a proposal can be drafted to redistribute taxes back to their owners proportionate to their token holdings.

It's variables and functions are:

* **Popular Vote Ratio:** ratio needed for a vote to pass

* **Yearly Tax:** How many Ether each member is expected to pay yearly in order to maintain their token

* **Taxation date:** What day tax is due yearly, default to Dec 31st.

* **Tax Balance:** Tax available to use towards resource project or be refunded back to members

* **Available Tax Balance:** Tax balance minus any outstanding proposal's costs that might get passed. This is used when a new proposal registers in order to check that there are sufficient funds to achieve it.

* **Rental Price:** The price in Ether that is required to be sent in order to book 1 night

* **Proposal Length:** How long proposals are active to recieve votes.  Since users can change their vote, this is also a time to campaign for or against the proposal off-chain.  This variable is used in all proposals:
  * resource
  * non-resource
  * member management

  Also it's important to note that this get's paused if the chairman is nominated for a force withdrawal.  This prevents an attack against a proposal by nominating the chairman for a force withdrawal.  That way a proposal may be delayed, but not blocked.

* **Member Withdrawal Frequency:** How long between member being nominated to force withdraw. This is to prevent attacker from repeatedly requesting that a chairman be removed, hence putting their proposal on hold and blocking there proposals from ever being voted on. Default set to once a year.

* **Withdrawal Notification Length:** How long a member must wait in order to withdraw their tokens to ensure they don't commit a "hit and run" against the DAO

* **Secondary Market Decrease Rate:** The rate in Wei that the token listed on the exchange is depreciated each day in order to find a buyer.

* **Maximum Number of Proposals:** The overall number of proposals is naturally restricted by how much Ether is in the escrow balance, because the total of proposed funds to be used can't be more than what is available in the tax balance. However, this would protect against if a malicious member sends a thousand proposals at 0 Ether, in order to flood the space with "distraction" proposals in order to sneak something by.

* **Map:** Addresses => Balances

* **Token Array:** Finalized token array from the token sale. Needed for secondary market info when forcing a withdrawal.

* **Amendments:** This is a mapping of rules that act as a type of "constitution". However, these are unenforceable by the contract itself and are here for the purpose that other's read to align their vision together, or have common understandings of what will cause a member to be nominated to for a force withdrawal. It's up the members themselves to read them and take them into consideration, essentially each member becoming a member of the “supreme court” and interpreting the articles as they are written in cases where a member is being forced to withdraw.

* **v2 — whitelist of approved tokens:** Can be basic, like via proof of phone number - but some identification check in order to verify each person controls their own tokens. Is "version 2" at this point because simple solutions can be gamed fairly easily, and complex solutions are not readily known to me, or accessible.

* **v2 — mint more tokens:** In case somehow the asset can be divided into smaller parts — ie they add a mother in law studio that can act as its own unit, but is still tied to the underlying assets and was paid for with the DAOs resources, determining how to create new tokens, how to differentiate their value and privileges seems beyond the scope of this initial project.

**Register Members:** Limited to being called only by the token sale contract. Map's sent address as the registered member and set's appropriate token amount to however much they've bid. Also sets info on the token array.

**Register Force Withdrawal:** Receives the address of the member in question - pauses the contracts that they happen to be chairman of.

**Register Proposal:** Proposals need to register with the Registry Contract in order for the Registry Contract to check that an address in question is not chairman or involved in any outstanding force withdrawal proposals before withdrawal. Also starts the timer for when it will accept votes and opinions.

**Check Eligibility:** Sent from a proposal contract, this checks to see if the address casting a vote is indeed registered to this DAO. ** Some thought has been given to if all votes should just be held on this contract itself or on the proposal contract, I'm still not sure of the technical merits of either approach, but going ahead with the assumption that all will be stored on the proposal.

**Archive Contract:** Because the registry contract will be checking votes associated with each proposal we could keep everything there indefinitely, but think it might be cleaner and easier to allow it to clear it's memory, push a "summary" to the individual contract, noting whether it passed or failed with the corresponding votes and just have a pointer to it for record keeping purposes. This would be triggered after an execution.

**Execute Proposal Contract**: Would request information such as chairman, and the proposal cost and distribute the funds from the "tax account" as specified.

**Set Rule:** Executed with PVR from a non-resource contract, can change as often as a new proposal is passed. Changes any and all of the variables listed above such as PVR, Yearly Tax, Maximum # of proposals, etc...

**Set Amendment:** Executed with PVR from a non-resource contract, can change as often as a new proposal is passed. Changes any and all of the amendments — and allows for creation of a new one if index is not found.

**Pay Tax:** Ether amount, records the amount paid for that calendar year for that user.

**Distribute Tax:** Takes the yes / no votes, and the amount to be distributed. Must be executed from a resource contract to re-distribute some amount of Ether back to the token holders proportionate to their holdings.

**Check for Delinquent Addresses:** Checks 1 month prior to taxation date... how can you do timed functions... like solidity equivalent to setTimeout()

**Request Tax Amount:** Takes an address, return how much tax is owed for particular user. True is returned if paid in full, amount is returned if have withstanding balance.

**Force Withdrawal:** Called from the registered member management contract, sending with the "yes" and “no” votes (addresses) creating a Marketplace Contract to sell.

**Withdrawal:** Member transfers ownership to another address -- most likely to sell on secondary market. Must first pass a "quiet period" to ensure member is not performing a “hit and run”. Is just a waiting period for the typical ERC20 spec transfer function.

**v2 — Set Proxy:** Set's another token holder's address as the proxy. Any amount of proxies can be given. You can give a proxy out to your son, daughter, cousin, neighbor, etc... allowing them to act on your behalf. It's important that proxies can vote independently on different proposals.

## **Non Resource Proposal Contract**

This proposal is the most basic of the proposals, but allows for variables and amendments on the Registrar Contract to be changed.

It's variables and functions are:

* **Status:** Set to "true" if passing, “false” if failing. (Maybe this should be codes, to denote multiple states such as “passing but still has time”, “passed”, “failing but still has time”, “failing”, “paused via force withdrawal”, “killed”, etc... depending on multiple factors.

* **Registry Contract Address:** The address of it's parent Registrar Contract. For security checks, and knowing where to send commands to change rules / amendments.

* **Chairman address:** The ability for whoever publishes the proposal to set a chairman, it's by default the person that submitted the proposal, but this allows only for someone to be responsible to kill contract.

* **Map of Addresses** => Opinions

* **Map of Addresses** => Votes

* **Active:** Default is set to true, flipped to false when contract is executed. A modifier is present on all functions that doesn't allow them to be run if is not active.

* **Variable to Change:** Name of the variable to change

* **Amendment to Change:** # of the amendment to change.

* **Value:** New value to be set to the variable / amendment in question.

**Init**: Registers itself with the Registrar Contract

**Cast Vote**: Can take parameters of "yes", “no”, or “withdraw” — Checks to make sure the address that sent the vote is registered. Then maps it to either “yes” or “no” options multiplied by how many tokens the sender has in the registry — or withdraws their vote completely. You have the ability to change before contract is executed by sending another transaction. Their address is then public, which is used to validate to make sure they can't withdraw their escrow

**Add Opinion**: Checks to make sure the address that sent the opinion is registered. Then maps it to the user's address. If Only way to change it is to send a completely new transaction. The message will completely override what your current opinion is. Takes a parameter to point to a duplicate contract if they want to propose something similar but slightly different.

**Get Opinions**: Returns opinions, most likely to show on a UI, or gauge how heated or opinionated people are on this particular thing.

**Kill Proposal**: Only executable by it's parent registry contract or the chairman. In case of a chairman being voted to force withdraw by the other members, it would nullify all proposals they have in question.

**Execute Proposal**: Sends the votes to the registry contract to be "archived" as a record of who voted for what. If PVR is met then sets the new value to the public variable in question

## **Resource Proposal Contract**

This is probably the contract that will be used most. It needs to be tied to a parent "registry" contract in order to pull resources from it, and in order to ensure the participants have registered their tokens on it. It will ensure proposals comply with its parent's rules such as the determined PVR.

If someone likes a proposal but wants to make one small adjustment they can "duplicate" the proposal and pass along the variables they want to change, however the timeline will stay the same and will close along with it's parent.

It's variables and functions are:

* **Chairman Fee:** How much work is this person going to need to put in to oversee this task, payable on completion of milestones.

* **Status:** Set to "true" if passing, “false” if failing. (Maybe this should be codes, to denote multiple states such as “passing but still has time”, “passed”, “failing but still has time”, “failing”, “paused via force withdrawal”, “killed”, etc... depending on multiple factors.

* **Parent Contract:** The contract that was duplicated to create this particular contract.

* **Is Dependent on Parent:** Regardless of if it passes PVR, will only pass as long as parent also passes.

* **Proposal Cost:** How much is going to be released to the chairman in order to pay for completion.

* **Registry Contract Address:** The address of the Registry Contract is at. For security check reasons.

* **Chairman address:** The ability for whoever publishes the proposal to set a chairman, it's by default the person that submitted the proposal, but this allows for people to nominate others into positions of power. Also allows array of addresses incase this is being used to redistribute taxes to all members. In which case, paid out according to their portion of owned tokens.

* **Map of Addresses** => Opinions

* **Map of Addresses** => Votes

* **Active:** Default is set to true, flipped to false when contract is executed. A modifier is present on all functions that doesn't allow them to be run if is not active.

* **v2 — Project Timeline:** A proposed length that this project should take. Initially thought of breaking 1 project into multiple milestones and breaking the tax payout accordingly, but think that it should be done proposal by proposal. For instance, one proposal might be to get an architect to draw up plans for a deck. After that proposal is finished, and there is a solid understanding of cost based off the drawings, then a NEW proposal would be submitted for construction. This is instead of having 1 proposal for the entire project.

* This could *POSSIBLY* be used in the future to penalize the chairman going forward if they don't meet the timeline. For now just as a marker for transparency so everyone voting can gauge how long it'll take. Or for people to point to as "proof"

**Init**: Registers itself with the Registrar Contract

**Cast Vote**: Can take parameters of "yes", “no”, or “withdraw” — Checks to make sure the address that sent the vote is registered. Then maps it to either “yes” or “no” options multiplied by how many tokens the sender has in the registry — or withdraws their vote completely. You have the ability to change before contract is executed by sending another transaction. Their address is then public, which is used to validate to make sure they can't withdraw their escrow

**Add Opinion**: Checks to make sure the address that sent the opinion is registered. Then maps it to the user's address. If Only way to change it is to send a completely new transaction. The message will completely override what your current opinion is. Takes a parameter to point to a duplicate contract if they want to propose something similar but slightly different.

**Get Opinions**: Returns opinions, most likely to show on a UI, or gauge how heated or opinionated people are on this particular thing.

**Kill Proposal**: Only executable by it's parent registry contract or the chairman. Incase of a chairman being voted to force withdraw by the other members, it would nullify all proposals they have in question.

**Execute Proposal**: Sends the votes to the registry contract to be "archived" as a record of who voted for what. If PVR is met then sends the amount specified to the chairman specified in the contract.

**Accept Chairman**: Is called by suggested chairman if not the author of the proposal.  Upon acceptance the funds are sent to Chairman. If chairman does not accept, the funds will not be withdrawn.

**Duplicate / Add-on Proposal**: Duplicate enables a person to copy the contract info and variables, (minus the votes & opinions) — and make any changes you want to it. Leaves a pointer back to the parent, so that people can view similar contracts as viable options, or as possible additions.

Duplicates of duplicates are not allowed, and there is nothing stopping a parent from being passed successfully along with it's child. They could both be valid proposals, and in some cases could be "amendments" or “add ons” to the original proposal.

Note: I'm tempted to allow the group to change proposal variables such as who the chairman is, the registry contract, chairman fee, etc... but I feel like creating a NEW contract is a better route, because the truly important things (votes & opinions) need to start from scratch anyways.  So an emphasis should to put on creating "small, step by step proposals rather than large proposals that take a long time"

## **Member Management Contract**

This contract behaves very similar to how the resource contracts work. However, there would be no chairperson, and they would not be "duplicatable" as the resource contracts are.

As little as 1 person could nominate someone that should be voted "off the island" so to speak. They would then need to meet the PVR of members confirming or 'yes' voting the nomination to kick a someone out. The person in question would have a character limit of 2,000 words in which to defend themselves, and each member would have a 500 word area vouch for or against the member in question and allows links to other places online.

It's variables and functions are:

* **Registry Contract Address:** The address of the Registry Contract is at. For security check reasons.

* **Member to Withdraw:** The address of whoever they are wanting to force withdraw from the DAO.

* **Accusation:** The 2000 character reason that they are wanting the member to be force withdrawn

* **Good Standing Fee:** When specified, the member to withdraw can pay the amount required (to go into Registrar Contract) and the contract is then killed. If set to false, then member can not pay their way out.

* **Map of Addresses** => Opinions (500 character limit)

* **Map of Addresses** => Votes

* **Active:** Default is set to true, flipped to false when contract is executed. A modifier is present on all functions that doesn't allow them to be run if is not active.

**Init**: Registers itself with the Registrar Contract

**Cast Vote**: Can take parameters of "yes", “no”, or “withdraw” — Checks to make sure the address that sent the vote is registered. Then maps it to either “yes” or “no” options multiplied by how many tokens the sender has in the registry — or withdraws their vote completely. You have the ability to change before contract is executed by sending another transaction. Their address is then public, which is used to validate to make sure they can't withdraw their escrow

**Add Opinion**: Checks to make sure the address that sent the opinion is registered. Then maps it to the user's address. If Only way to change it is to send a completely new transaction. The message will completely override what your current opinion is. Takes a parameter to point to a duplicate contract if they want to propose something similar but slightly different.

**Get Opinions**: Returns opinions, most likely to show on a UI, or gauge how heated or opinionated people are on this particular thing.

**Execute Proposal**: Sends the votes to the registry contract to be "archived" as a record of who voted for what. If PVR is met then sends the amount specified to the chairman specified in the contract.

**Pay Fee**: receives payments and when Good Standing Fee is reached, kills the contract.

Note: I've removed the ability for the chairman to "kill proposal" because want to eliminate desire to artificially nominate someone to withdraw in hopes that they will “pay off” or bribe or blackmail or whatever. Want to try to avoid anything that might not make these sincere.

## **Secondary Market Contract**

If somebody doesn’t pay taxes or breaks fundamental rules of the DAO they are kicked out. This contract sets fair rules for compensation and auctioning their token. First it's important to understand that users can be kicked out for two reasons:

1. On principal — broke rules, or loss of favor in the group — in which they should be compensated for their token at whatever the sale price is.

2. Because of Money — didn't pay taxes, or have Nomination of Force Withdrawal held against them in which they could resolve if they paid a Good Standing Fee. — in which case the sale goes to compensate first the Good Standing Fee, and then are compensated with whatever is left over (if anything)

The contract receives the address in question, checks the amount that was paid for it originally, recorded on the Registrar Contract, and starts the bid there. It then has 5 days in order to receive a bid and treat it the same as in the original token sale with whoever nominated the force withdrawal acting as the Chairman.

The Chairman does have a few responsibilities with this sale, so to compensate he get's 2% fee for initiating the process, verifying that the new person and is responsible to close the auction in case of trolling.

But if 5 days passes and nobody bids (for some reason the token has lost value) it starts a reverse dutch auction, decreasing price by the determined Secondary Market Decrease Rate each day until it becomes 0 and waits for someone to claim it.

Independent of if the member has 1 token or 10 tokens, all are offered up when a force withdrawal occurs, and the bid must be for the entire lot. When a bid is won, the forced member's address is replaced on the Registrar Contract with the winning bidder's address.

It's variables and functions are:

* **Price:** The initial price per token, is re-calculated each time a bid occurs

* **Active:** Default to true, false when chairman signals close.

* **Deadline:** Date the sale started

* **Good Standing Fee Needed:** Fee needed in order to self-destruct the contract

* **Chairman Fee:** Percentage that is given to the Chairman as compensation for nomination, watching for "trolls", and executing the contract.

**Init:** No need to registers itself with the Registrar Contract, because it was instantiated by it, so already knows the address, the fee needed, etc. Just set's the "Deadline" in order to indicate the line between fixed token bid sale and reverse dutch auction.

**Bid:** Takes 2 parameters, what they're bid is and second is a means for communication. Checks to make sure amount is equal to or more than the price and acts accordingly (if past the 5 day mark then calculates what the price should be by retrieving the "**Secondary Market Decrease Rate"** and multiplying it by the days, and rewards instantly)

**Execute Contract:** Only accessible to the Chairman. His responsibility is to verify that the new address owner is not like the wife of the forced out user that is bidding on behalf of the forced out member. This could easily be thwarted, so I question putting it in at all, but figure I might as well make a note of it for the Chairman. On execution the contract sends the chairman fee, and signals to the Registrar Contract to transfer the token.

**Signal Close:** Allows chairman to signal that sale will close in 24 hours, believes a consensus has been reached on price of tokens. Set's active to false.

**Set Deadline:** Called each time a successful bid goes through. Modifier looking to see if it's pass that day in order to start reverse dutch auction rather than fixed token style bid.

## **Scheduling and Rental Contract:**

Proportionate to holdings, you have different windows of time that are open to scheduling your uses. Scheduling is an ongoing process, with no blackout dates except for construction or other allotted dates approved through a proposal. Slockit is used to allow or restrict access.

Each day becomes available 1 year in the future. The first year, with AirBNB scheduling becoming available 6 months in advance.

Each token you hold represents an entire night from 12pm till 12pm the next day. Locks on the door make a query each day for who it allows to use its location. Holders of that day can manually add "approved" addresses that can access. That way you can gift your “token use" to friends or family, but ultimately you are responsible for their behavior and only you have voting rights.

Upon arrival the member should submit a report noting if things are broken or not left was they should be. If they fail to do so, they will be held accountable for whatever things are already broken that they did not record.

If something's not right with the condition of the house they file a proposal - either to cover it with community funds or to fine the previous member directly. This goes through the designated process. A member is nominated to force withdraw with a price they can pay in order to not be foreced out. If the group passes the proposal -- and member does not pay within 1 month -- their token is automatically sent through the secondary market in order to pay for damages they incurred. Obviously a proposal can be raised to direct funds towards a further lawsuit on behalf of the DAO - or can be pursued privately if damages are significant.

It's variables and functions are:

* **Map of Dates:** => Each date in a year (not sure what to do about leap year) mapped to a dictionary of address, amount paid, and their "check in" report

**Init:** No need to register itself with the Registrar Contract.

**Reserve - Payable:** Takes parameter of night requested. Checks to make sure it is under 1 year in future. Checks to make sure not already booked. If member, check if they have available uses still (each token they own is 1 night per year) and no Ether is needed, if not member or if already used up their token, must send amount required by the registry contract.

**Cancel Reservation:** Only available if further out than 1 month prior to their reservation. Returns Ether paid.

**Check In:** Takes parameter of a message detailing the condition in which they found the space. Free to leave a message about "windows broken" or “kitchen is a mess, no washed dishes” — in order to either look at the record of a problematic tenant, or trace the origins of some broken appliance / furniture.

## **Version 2 Ideas**

**Marketing:**

Incentivize members to share with others during the token sale. They get some sort of multiplier if include data in their bid transaction that points to a user that also wins a bid.

**Stablecoin:**

This project is begging for some sort of stable coin, but for now just depends on the group self managing the money by raising Ether taxes when needed, and re-distributing taxes back to token holders when exists excess.

**Education:**

Education is possibly the single most important aspect of this democracy because each member has such power in the decesion making processs.  The longevity of it's existance is dependent on all of it's members succesfully understanding issues, and looking past mob mentality, prejudice, witch-hunts, and the many other ignorances that plauge human thought.  That being said, it'd be good to have a "proof of knowledge" system that enforces a user to be mildly educated on the issues before voting.

**Certifications:**

Along the same lines as education, it'd be good to verify people that are recieving funds are qualified to use them.  For instance a proposal might like to provide an authenticated "general contractors" license to show that they actually know a general contractor that will be carrying through with the project.

**Member Communication:**

Chat and community forum, notification system. This should be done off chain but would be nice to verify that they have a token in order to participate. Most likely the "chat" functionality is just something like slack. Only conversations that are relevant to the contract are ones that go along with opinions for official blockchain voting.

One thing that does seem necessary is to allow notifications, because a member shouldn't be visiting the contract daily. Rather things should be running smoothly and a member should receive an email / sms saying "New Proposal Submitted" with the details right there in the email. If the member responds “yes” or “no” it casts the vote as such. Is this technically possible to integrate SMTP protocol into Ethereum natively? Or would we just use a trusted and reliable 3rd party? Can contracts make API calls?

Even if we had a simplistic approach — we could possibly have a "log" that logs out each kind of transaction, and an off chain site that is watching for changes and notifying users independently.

Actions that should trigger notification:

* New proposal submitted (resource, non-resource, and member management)

* Proposal timeline near finishing (reminder to vote)

* Proposal finished with results

* Token(s) available on secondary market

* Tax due (with 1 month warning before expiration)

* *Optional* new votes, opinions

* *Optional* Token sale triggered for ending (24 hour notice)

* *Optional* Token sale bid has been outbid

* *Optional* Asset is rented and receiving your portion of proceeds

# Afterward

3 large similarities exist between managing a real estate property, and governing a nation. Namely the creation of rules called laws,the enforcement of those rules, and the management of an escrow account that we all fund through our taxes.

Creating the framework for a property on a much smaller and simpler scale and through basic mechanisms holds an important advantage which is flexibility.  We start small so that we can learn from flaws in the design, build it incrementally, and test our hypothesis as it grows following an Agile <sup id="a1">[1](#f1)</sup> mentality.

## **Finances**

 

    The difference between death and taxes is death doesn’t get worse every time Congress meets. 
    
    -- Will Rogers



Our country's finances are in shambles.  When writing this, we are nearly 20 Trillion in debt<sup id="a3">[3](#f3)</sup>, and our political leaders continue to throw money into a seemingly black hole.  We vote for the politician that is "the lesser of two evils" with absolutely NO indication of how much of our money is going into which projects.

Up to now this "trusted representative" form of governance is the best that we’ve been able to collectively decide upon as a society.  When countries such as the United States were created they didn’t have enhanced communication technology and a representative government was badly needed.  It was a great step forward to giving smaller groups of people power and thrived because it was logistically impossible to coordinate the collection of the voices of an entire nation.  

The longer those people stay in a position of power, the longer the people they represent are exposed to the risk of corruption.  This need of middlemen for logistical reasons <sup id="a4">[4](#f4)</sup> is no longer the case; the internet revolutionized communication and we’re ready to represent ourselves.

We — through our government — continue to throw money into corporate bailouts, leaders that can divert public funds into their own accounts or aligned businesses, special interest programs and failing institutions.  Recently 100 Billion dollars were just "lost" <sup id="a5">[5](#f5)</sup>**.**  This is either massive corruption or massive incompetence.  

    Power tends to corrupt 
    
    -- Lord Acton


I believe we continue in this system not because we want to, but because our system is setup in a way that allows these things to easily exist.  I’m not saying our current system is the worst in the world, or has not achieved impressive things, but when our taxes are managed with smart contracts on a public blockchain we will be delivering a blow to corrupt and incompetent politicians everywhere.  The blockchain will revolutionize our tax system for the better.  

Daohaus aims at solving this issue through the allotment of funds tied directly to the reason they are being released.  Everything is transparent and leaders will be held directly responsible for the funds released to them.

In the past "policy" and “finances” have been separate issues.  You voted for a politician because of what they stood for, not because of their financial plan of how to implement their vision.  Now with Daohaus we are combining those two aspects into one by requiring the person to propose a plan to also get approved for the amount of money they need to fulfill on their promises, and also how much they will be paid for seeing the project through.

## **Policy**

With the advent of blockchain systems, smart contracts, and cryptocurrencies we have enhanced our current monetary instruments, and need to also update our outdated political system for one that is more transparent and better represents not just the "black and white" views of any given political party or representative, but the mixed beliefs of a truly diverse group.

    If the general will is to be able to express itself, 
    that there should be no partial Society within the state 
    and that each citizen should think only his own thoughts 
    
    -- Rousseau, Social Contract

Currently we vote for the person that will make decisions, and not the decisions themselves.  For example, when someone votes for the next president of the United States, this person is free to appoint to different high ranking positions in our government anyone he chooses.  Positions such as secretary of state, education, etc… go to people that have spent millions of dollars in campaign finances, people with political clout, alliances, or other factors that don’t necessarily contribute to an effective leader or project manager.

Daohaus allows multiple people to run for each position and it’s members to choose the best plan rather than them being appointed via political alignment.  This allows whoever has the clearest, most convincing vision for any particular objective within our government to be chosen and not just whoever is better friends with a particular party leader.

Now sometimes it is good to have "representation" because if the group had to make every decision, it would be a long and time intensive process.  We account for this by introducing proposals that aren’t intrinsically any size — each proposal can be as small or large as the person submitting it can convince its members it needs to be.  This allows for the group to collectively decide if they want a 100% pure democracy, small representation, or even a king.

Technically Daohaus is being built in a way that the community behind it could build and vote for alternative governance models on a project by project basis.  The education of it’s members could be all entrusted to one person that has full control of the "education" escrow tax account — essentially making them a “king”.  While at the same time all community improvement proposals could all be voted on separately, with each proposal being aimed at a specific road improvement, park creation, or community celebration project.  Then if one of the patterns or systems is viewed as advantageous, someone could internally propose to switch over if the community approves, will instantly be upgraded.

## **Enforcement**



    Strictly speaking, there is no such thing as a simple government  
    
    -- Rousseau, Social Contract



The subjects outlined are big and complex problems that a mere change in technology alone will not solve.  In the same fashion that a journey of a thousand miles begins with a single step — the journey towards a more pure democratic society begins with small and simple proof of concept such as this.  

Things also become more complex when physical geography and broad society come into play.  For example, in today’s world where people join not from a conscious "buy in" decision but that of a “born in” decision of others, in order to suspend someone from taking part in a community they literally have to be locked behind bars. 

At our size and intended scope we do not have the resources or right to enact such a punishment.  However, if we build our community around something of real value, like that of a property that needs collective buy in from it’s members, a bad actor in the system — like someone who breaks a window and refuses to pay for it — can and should be removed from the group with their portion of the shared asset being resold in order to recoup the damage done.

That is why Daohaus makes sense.  It’s a small, self-selected group of people, brought together around a common asset. 

It’s a small step forward towards a better democracy.

## **Footnotes**

<b id="f1">1</b> This [Wiki Article](https://en.wikipedia.org/wiki/Agile_software_development) describes Agile software development as a set of values and principles for software development under which requirements and solutions evolve through the collaborative effort of self-organizing cross functional teams. It advocates adaptive planning, evolutionary development, early delivery, and continuous improvement, and it encourages rapid and flexible response to change. [↩](#a1)

<b id="f2">2</b> Generally, Bauhas design attempts to solve functional issues with a minimum of decorative embellishment. This is not to be confused with a minimalist aesthetic which may actually impinge on functionality for the sake of appearance promoting a "less is more" mentality. [Bauhaus Wiki](https://en.wikipedia.org/wiki/Bauhaus) for more info.[↩](#a2)

<b id="f3">3</b> This number is visually and interestingly represented via [this website](http://www.usdebtclock.org/) but is a common estimate.[↩](#a3)

<b id="f4">4</b> Middlemen for logictial reasons may not be needed, however there is still a place for representation for efficiency of time, and depth of subject knowledge.  For example I don’t have the time or experience to become an expert in the complexities of how to build a skyscraper, so on a particular project I’d like to proxy my vote to someone I know with that experience.  However, I don’t want them making decisions on my behalf about other things like health care. [↩](#a4)

<b id="f5">5</b>  The [Washington Post](https://www.washingtonpost.com/investigations/pentagon-buries-evidence-of-125-billion-in-bureaucratic-waste/2016/12/05/e0668c76-9af6-11e6-a0ed-ab0774c1eaa5_story.html?utm_term=.e18a99003420) wrote an interesting article with some nice graphs. [↩](#a5)

<b id="f6">6</b> If the Chairman only advertises the DAO as a shared home ownership, the group may never actually gain a PVR (popular vote ratio) on which home to buy because everyone wants it in a different city. So the more specific the Chairman can be in attracting members, the more unified and effective The DAO will be.  [↩](#a6)

<b id="f7">7</b>  The following are some models, but new models are continually being created and modified [↩](#a7)

* [Gnosis]([https://blog.gnosis.pm/introducing-the-gnosis-token-launch-3cc4cffb5098) did a Reverse Dutch Auction which is a bid on how much are willing to pay for it starting from the top 

* [Bancor](https://cointelegraph.com/news/bancor-an-innovative-token-sale)
 employed a general idea where there is a minimum amount of time available, with a hidden cap and fixed price.
* [EOS](https://steemit.com/eos/@eosio/draft-eos-token-sale-smart-contract) essentially did a distributed auction, where a fixed # of tokens were released each day, allowing there to be a secondary market immediately while continuing to release tokens for an entire year. 

