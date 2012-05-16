# wow-auction-snapshots

This repository contains snapshots of the World of Warcraft auction houses on the **EU-Shadowsong** realm from
**August 2011** to **May 2012**. These were collected for my WoW auction-analytics final year project which will be
published here soon (likely September). All data retrieved from the [Blizzard Community API][blizzdocs].

A few notes on parsing and importing these files:

*   Each is GZ-compressed JSON, in the [format documented][blizzdocs].
*   Each file should be interpreted sequentially (you can't, for example, import multiple files concurrently) as
    auctions persist between files (each file should be perceived as a snapshot of the auctions available at the time).
*   The index file is an SQL dump containing metadata for each snapshot (such as date created, number of auctions).
*   Items are referenced by ID. Blizzard provide the item information from their community API.

The scripts to fetch these are pretty intertwined with the original application and will be released with it. However
it's not hard to write a simple fetcher script (poll `/api/wow/auction/data/realm for updates`, retrieve new files).

[blizzdocs]: http://blizzard.github.com/api-wow-docs/