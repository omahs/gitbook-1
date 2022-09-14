---
description: (BETA)
---

# Ethereum NFT Tables

{% hint style="warning" %}
These legacy Ethereum tables are deprecated. See [Ethereum Core](../../ethereum-core-tables/) for up-to-date Ethereum models.
{% endhint %}

We have two NFT tables, currently in phase 1 of beta: nft\_events (mints, sales, etc) and nft\_metadata (token names, images, attributes, etc.). Check out some sample queries [here](https://velocity-app.flipsidecrypto.com/velocity/collections/4d5f21e4-de97-47db-b3c3-c19c27e847c5).

Our goal with these is to make a unified table of NFT on-chain data that makes it super easy to compare across and within NFT's. To do this we've gone pretty deep into each NFT that is in there, adding one little piece of its ecosystem at a time. That being said, we are building this for our community and we want to make it as useful as possible, so feedback is very welcome.

**What we have:** \
**\*** Metadata and native on-chain events for 8 NFT platforms. \
\* Every Opensea and Rarible sale back to October 2020. \
**\* Use** [**this doc**](https://docs.google.com/spreadsheets/d/1mEyanXGHhYfI2fi65jdhDhUCvp06-ucEnM5y1N5EBVk/edit#gid=0) **to see what NFT's are available, and what's coming next**. _We update this doc religiously._

**What we don't have:** \
Off-chain events. For example, all listings and bids and some mints on Opensea are totally off-chain. We don't have this data. There is a possibility of future api integration. We're not there yet, but if you have ideas we'd love to hear them. Data before October 2020 but we're backfilling every day. Some types of events that are on-chain but are not easily interpretable. Many contracts make the key to decoding their contracts public, but for those that don't, we can often just "figure it out" but not always.

**Why these NFT's?**\
****Opensea had to be included because it's the largest marketplace on Ethereum. For the others we picked them somewhat randomly, aiming for a mix of art NFT's and other platforms.

**What about other NFT's?**\
All NFT data is in the regular tables (`udm_events`, `events_emitted`), it's just not all in these specially formatted tables, yet.

**This data is super BETA! How you can help make this data better:**\
****What tokens are you most interested in? We want to add them! _Let us know the following in_ [_discord_](https://discord.gg/HXZTApG5)  _(@angela) or via email (hello@flipsidecrypto.com):_

_**Good**_**:** Send us the name of the token\
_**Better**_**:** Send us the name, contract address and website of the project\
_**Best**_**:** Send us the name, contract address and website PLUS example transactions (links to etherscan) of the following transaction types (native to the project, i.e not Opensea transactions): \
&#x20;   \- minting \
&#x20;   \- list \
&#x20;   \- unlist \
&#x20;   \- bid \
&#x20;   \- sale \
&#x20;   \- any other special thing you can "do" with this NFT

**Pro Tip 1:**\
We are backfilling the table that makes this data possible BUT we're only back to October 2020. This means that for native events (i.e. not Opensea sales), if the contract was minted before October the native event might not show up. But we have every Opensea sale since October so you might find that you can find a token that was sold through Opensea but then you won't be able to find any metadata for it or any mint event. We're working on it!!

**Pro Tip 2:** \
Start with the `nft_events` table and (`LEFT INNER`) join on `contract_address` AND `token_id` to bring in what you need from `nft_metadata` Why? There is more in the metadata table than you might find in the events table. We cast a wide net for metadata.

****
