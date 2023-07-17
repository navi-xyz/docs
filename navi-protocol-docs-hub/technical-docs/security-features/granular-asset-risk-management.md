# Granular Asset Risk Management

### **Supply Limits**

These are limits to how much of the collateral asset can be used in the money market. This parameter is designed to protect the pool against specific, long-tail volatile assets to damage the pool integrity.

For a variety of smaller capitalisation tokens with high fully-diluted valuations that are traded with thin liquidity, having the ability to supply an infinite amount of such token poses structural risks. Were the capitalisation of such token to vary significantly, it is likely that positions backed by such assets could no longer be liquidate-able, posing the risk of bad debt being incurred in the system.

### Debt Ceilings

These are limits on the total borrow amount of a market that is collaterized by another specific asset in the pool. The cap is measured as an amount of the borrowed markets underlying tokens.

Similarly to Supply Limits, debt ceilings enable further granular risk management of certain collateral assets, by making sure that certain tail assets cannot be used to collateralise positions that are too large.&#x20;

### **Asset Blacklisting**

You can blacklist specific collateral assets from borrowing individual borrow assets in a pool. This decreases risk and reflexivity, enabling further isolation modes in pool.&#x20;

For all intents and purposes, this is an extension of the Debt Ceiling: It essentially sets a Debt Ceiling to zero.

### Borrow Limits

The platform enforces borrow limits for each user, calculated as a percentage of their collateral value. Borrow limits ensure users maintain a safe collateralization ratio and protect the lending pool from defaults.
