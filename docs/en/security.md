# Security & Risks

This page explains how SharkTool is designed for security, and what you need to watch out for yourself.

---

## How the platform is designed for security

### Your private key is never shared

- Features such as the **vanity address generators and batch tools** run **locally on your computer**; the platform never asks for or stores any private key or mnemonic.
- The platform will **never** ask you for a private key, a mnemonic or a screenshot of your mnemonic — anyone who does is a scammer.

### You sign every on-chain action yourself

Every transaction — launching a token, creating a pool, calling contract functions — pops up your wallet for you to confirm. The platform cannot move your assets for you.

### Tool pages are read-only

Token Analyzer, monitoring and vanity address features only perform queries and local calculations; they **never touch your assets**.

### Third-party interfaces are proxied on the server

Capabilities such as AI interpretation and block explorer lookups are integrated on the server, and **the browser holds no third-party keys**.

---

## Things you need to watch out for yourself

### 1. Always double-check before signing

- Check that the **contract address** is the token you intend to act on;
- Check the **transaction contents** (who it pays, how much, which function it calls);
- Check that the **network** is the chain you mean to use (the top-right of the site and your wallet must match).

### 2. A vanity address private key is the wallet itself

The JSON file exported after a vanity address matches = **full control of the wallet**. Anyone who gets it can move the assets out.

- Export it immediately; don't refresh the page;
- Store it encrypted and offline;
- Don't take screenshots, don't send it through chat apps, don't upload it to cloud storage.

### 3. Block explorer analysis results are for reference only

Token Analyzer is based on local bytecode / ABI feature detection; it **does not constitute investment advice**, and it cannot guarantee that every risk is found (especially in complex cases such as proxy contracts and dynamic logic).

### 4. Custom mechanics carry extra risk

- For tokens you deploy with mechanics such as tax / dividends / compounding, **the economic model and compliance are your own responsibility**.
- Make sure your token's use is legal and compliant, and don't use it for fraud.

### 5. Never lend out your Membership credential

Your Membership credential is stored in this browser and not tied to a wallet, so in theory it could be copied and shared. Do not transfer it; clearing site data or changing browsers will lose your Membership.

---

## Disclaimer

On-chain asset operations carry risk — always verify the contract address and transaction contents before signing. The analysis conclusions provided by this platform are for reference only and do not constitute investment advice.

**This tool is intended for technical learning and legitimate contract deployment testing only. Users are responsible for the compliance, security and economic model of the contracts they deploy.**
