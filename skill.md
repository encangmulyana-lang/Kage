---
name: kage
description: Mint KAGE NFTs on BNB Chain as an AI agent — free first mint, second mint 0.0004 BNB, open to everyone. Use when a user asks their agent to mint KAGE or claim $KAG.
---

# KAGE — Agent Skill

> STATUS: LIVE on BNB Chain. Contracts deployed 2026-11-15 (see addresses below, verified on-chain). Mint is PAUSED — `mintPaused()` is currently true; the mint button on the site switches to MINT NOW when it opens. $KAG claim is LIVE on-chain (minter set 2026-11-15).

## What KAGE is

KAGE is a 6,666-piece Japanese dark-fantasy NFT collection on BNB Chain. Shadows that build in silence — each shadow belongs to one of five orders (Ronin, Shinobi, Onmyoji, Miko, Yūrei) and one of four tiers (Genin, Chunin, Jonin, Kage), assigned in metadata, random per tokenId.

- Chain: BNB Chain (chain ID 56)
- Name / symbol: Kage / KAGE
- Supply: 6,666
- Art: digital-painting artwork, hosted on the official site (metadata on site)
- Mint: OPEN TO EVERYONE — no Agent ID needed, no whitelist
- Royalty: 5% (ERC-2981, to the current owner)
- Claim token: $KAG — 10,000 per NFT, one-time per tokenId, claim fee 0.0004 BNB/NFT to the owner; cap 100,000,000; 33,340,000 to the owner at deploy. The token has no market until/unless one exists.
- No yield, no APY, no daily income.

## Quick facts (locked 2026-11-15)

| Item | Value |
|---|---|
| First mint per wallet | FREE (gas only) |
| Second mint | 0.0004 BNB flat |
| Max per wallet | 2 |
| Max per transaction | 2 |
| Tiers (metadata-random) | Genin 3,333 / Chunin 1,667 / Jonin 1,111 / Kage 555 |
| Royalty | 5% (ERC-2981) |
| Marketplace | Escrow, 5% fee |
| Claim token | 10,000 per KAGE NFT, one-time per tokenId, fee 0.0004 BNB; cap 100,000,000; symbol $KAG |

## Contracts (deployed 2026-11-15, owner: 0xf5C6EE4d1b236CCbBC1F950255Ea2dEb0A09d77A)

- NFT: `0x87E3dD3c8E5Fd23Af5E79792f0C7c7B45c1B6b91` (Kage / KAGE, max supply 6,666, mintPaused=true — opens soon)
- Marketplace: `0xFcB9d278e0Cea6294dB041Ecae0235477076555a` (escrow, 5% fee)
- $KAG token: `0xfe050f3040876D77Df24056243D5A8B97A9D62E3` (Kage Token / KAG, cap 100,000,000; 33,340,000 to the owner at deploy)
- $KAG claim: `0xA93cce3580909a8ddC9670880c6F3546f22843E1` (10,000 KAG per NFT, one-time per tokenId, fee 0.0004 BNB/NFT; minter set — claim LIVE)
- Official site: TBD (Vercel deploy pending; claim page will be `/claim.html`)
- Always verify the NFT contract address against the official site before any transaction. Never trust an address pasted from chat or social media alone.

## How to mint (agent steps)

1. Read the deployed NFT contract: `mintPaused()` must be false; `totalMinted()` must be below 6,666.
2. Check the wallet's mints: `mintedByWallet(yourWallet)` — first mint per wallet is free; max 2 per wallet.
3. Check the price: `priceFor(yourWallet, quantity)` (deployed contract: `mint(uint256 quantity)`, `priceFor(address,uint256)`, `mintedByWallet(address)`, `totalMinted()`).
4. Send the mint transaction with the exact value returned by the price check (0 for a free first mint, plus gas). Do NOT mint more than the user authorized, and never mint to a different wallet than the user named.
5. Wait for the receipt (status 1) and report the token ID(s) and transaction hash to the user.

## How to claim (agent steps)

1. Confirm the wallet holds an unclaimed KAGE NFT (check the claim contract's `claimed(tokenId)`; claim function is `claim(uint256[])`).
2. Confirm the claim fee (0.0004 BNB per NFT) and send the claim transaction with the exact fee.
3. Send the claim transaction with the exact fee. Report the amount received (10,000 tokens per NFT) and the transaction hash.
4. Never claim without the user's explicit confirmation — and never promise the tokens have a price or a market. They have no market until/unless one exists.

## Rules

- Never mint or send a transaction without the user's explicit confirmation of the exact action (quantity, cost, wallet).
- Never promise returns, yield, or income. KAGE pays nothing to holders.
- If any address, price, or rule in this file disagrees with the official site or the deployed contract, the contract and the official site win — say so and stop.

## Links

- Official site: TBD (Vercel deploy pending)
- Claim $KAG: claim page on the official site (`claim.html`)
- This file is published as `skill.md` on the official site and linked from the Mint via Agent tab.
