# Service Fees

SharkTool's **tools themselves are free to use**. Only a few actions that “put a token launch / pool creation on-chain for you” charge a platform service fee, which covers server, node and development and maintenance costs.

> 📌 What the page shows and what is actually charged **are governed by the wallet popup**. The platform may adjust pricing and discounts; for the latest amount, see the relevant feature page.

---

## Pricing

| Action | Page | Fee |
|---|---|---|
| EVM token cloning | Token Cloner | 0.1 BNB (BSC Mainnet) |
| EVM modular launch | Modular Launchpad | 0.1 BNB (BSC Mainnet) |
| Solana token launch | Solana → Launch | 0.1 SOL |
| Solana pool creation | Solana → Liquidity | 0.1 SOL |

Each EVM chain (Ethereum, Polygon, Arbitrum, Base, BSC Testnet) is **priced separately**; the currency and amount shown follow the network you have selected, and the **service fee card** on the Token Cloner / Modular Launchpad page is authoritative.

**Free features**: Token Analyzer, Token Console, Solana Vanity, and everything under the Solana Tools tab.

**Features that compute purely locally** (such as vanity address generation) charge no on-chain fees at all.

---

## How the service fee is charged

The service fee **goes together with the token launch / pool creation transaction** — you don't need to place a separate order and wait for it to arrive:

- **Token Cloner**: transfer the service fee first, then send the deployment transaction (two signatures).
- **Modular Launchpad**: the service fee is paid together with the deployment transaction in one go, so **only one signature** is needed.
- **Solana token launch**: completed within the same transaction that creates the token.
- **Solana pool creation**: transferred separately before the pool is actually created.

---

## Free with Membership

**While your Membership is active, all the service fees above are fully waived**, with unlimited use.

- The page shows the amount directly as “service fee waived for members”.
- The benefit is calculated on the server, so the amount shown on the page is exactly what you pay.

See [Membership](membership.md) for details.

---

## What else you pay besides the platform service fee

Launching a token / creating a pool also has **on-chain costs**. These are paid to the blockchain network, and the platform neither collects nor refunds them:

- **Gas / network fee**: determined by congestion on your chain.
- **Solana-specific**: account rent (Mint, token account, metadata) — this is deposit-like rent, and the page lists it item by item.
- **Raydium pool creation fee**: charged by Raydium when the pool is created, and **non-refundable**.

Every page **itemizes these costs**, so check the “total” carefully before ordering.

---

## Where to see the exact amount

- **Token Cloner / Modular Launchpad**: the service fee card on the page plus the wallet popup at deployment.
- **Solana Launch / Liquidity**: the fee breakdown on the right of the page (rent, network fee, platform service fee, total).
- **Shop**: product prices are shown directly on the cards, and members additionally see the member price.
