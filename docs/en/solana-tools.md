# Solana Tools

**Entry**: top nav “Solana” → “🧰 Tools” tab

Five on-chain operations tools that handle what you really need to do after launching a token: send tokens to a group of people, see whose hands the supply is in, sweep back wallets scattered around, and check whether a token has a backdoor left in its authorities.

**Fees**: all **free** — the platform charges no service fee (you only pay the network fee and account rent on the chain itself).

---

## 🧾 Batch Send

One list, sending SPL tokens or native SOL to multiple addresses.

**Steps**

1. Choose **“SPL token”** or **“Native SOL”**.
2. When sending tokens, enter the **token mint address** (you can also use the shortcut buttons under “My Tokens” below).
3. Paste the list with **“address,amount” on each row**, or click **“Import CSV”** to read a file directly.
   - Comma / space / tab separated all work; rows starting with `#` and header rows are skipped automatically;
   - duplicate addresses are de-duplicated automatically, and invalid addresses are listed separately (not mixed in with valid rows).
4. Click **“Pre-check token accounts”**: addresses that have never had a token account for this token are reported with the count and the rent required (about 0.002 SOL each, **paid by your wallet**, and created automatically during the transfer).
5. Choose a signing method and click **“Start batch send”**.

**Two signing methods**

| Method | Description |
|---|---|
| **Wallet signing** | Connect Phantom / Solflare / Backpack and confirm each transaction in your wallet. Each transaction is packed as full as possible (a dozen-plus instructions), and the page tells you up front **how many confirmations to expect**. |
| **Private-key local signing** | Paste a private key and sign directly in the browser, **with no wallet confirmation popup**. Use this when there are many addresses. The private key lives only in the current page's memory — never uploaded, never stored, and gone on refresh. |

**Notes**

- “Max per transaction” is only an upper bound; it narrows automatically with the transaction size (instructions that create token accounts take up more room, so a hard-coded count would exceed Solana's per-transaction size limit).
- Failed rows are listed separately with the reason, and you can **copy the failed addresses** or **retry the failed items in one click**.

---

## 🪂 Airdrop

**Your own address list**, with a fixed amount per person.

1. Enter the token mint address.
2. Address list: one wallet address per row, or click **“Import CSV”** to read a file (an `address,amount` format is also accepted, but the amount is ignored — the airdrop sends the same “amount per person” to everyone).
   - Duplicate addresses are de-duplicated automatically; invalid addresses are listed separately.
3. Enter the **“amount per person”**; the page shows the **number of recipients and the total** in real time, plus a distribution preview.
4. Choose a signing method and click “Start airdrop”. The sending process and failure retries are the same as Batch Send.

> 📌 The airdrop sends to **the list you provide**. To distribute by holding share, first export an address list from your own holdings data (or a dedicated holder-analysis tool) and import it here.

## 🔄 Consolidate

Sweep the SOL / tokens in **multiple wallets** back into a single main wallet in one go.

> ⚠️ Consolidate only works with **private-key local signing** — one wallet cannot sign another wallet's transactions.
> The private key is used only in the memory of this page, never uploaded, never stored; **when you're done, click “Clear private keys” and refresh the page**.

1. Enter the **destination address for the sweep** (if a wallet is connected, it defaults to the current wallet).
2. Choose what to sweep: **SOL + tokens** / SOL only / tokens only (tokens only requires the token mint).
3. Paste the **private key list**, one per row, in either format:
   - the JSON array produced by `solana-keygen` (`[12,34,…]`)
   - a base58 private key (64 bytes) or base58 seed (32 bytes)
   - you can also click “Import CSV” to read a file
4. Start after the confirmation dialog. Each wallet gets one transaction, with the result and transaction link shown one by one.

**Trade-offs to know**

- Each source wallet is **swept down to 0 SOL** (leaving only enough for one network fee) so that everything can be taken out.
- So **before running, make sure these wallets won't need to pay fees again**.
- **The rent in empty token accounts (about 0.002 SOL each) is not swept out**: recovering that money requires closing the accounts separately, which this tool doesn't do.
- The order is tokens first, then SOL (the other way round there would be no money left to pay the token transfer fees).

---

## 🔍 Holder Analysis

See a token's **holder structure**, looking only at the **top 20 holders** (one lightweight query, returned in about 1 second).

- **Concentration**: the share of the #1, top 5, top 10 and top 20, plus the **top 10 share after excluding pools** (this figure is the real concentration) and a “highly concentrated / moderately concentrated / fairly distributed” rating.
- **Details of the top 20 holders**, with the **type** of each address marked: `wallet`, or a **pool / contract address** such as `Raydium CPMM` / `Orca Whirlpool` / `Meteora DLMM` / `Pump.fun`.

> 📌 **This only looks at the 20 addresses holding the most**, returning results in seconds — enough to judge whether “the supply is in a few hands”. **The full holder distribution (including the total number of holders) is not provided on this page**; it needs a dedicated holdings-data source.
>
> The “type” column distinguishes ordinary wallets from pool / contract addresses: pool vaults are held by each DEX's program, ordinary wallets are not. **No insider / bundle analysis is done** — that would need historical trades and transfer relationships.

## 🔐 Authority Check

Judge whether a token **has a backdoor left in**, by its two most critical authorities:

| Check | Meaning |
|---|---|
| **Mint authority** | Not revoked = someone can still mint more and dilute your share to almost 0. |
| **Freeze authority** | Not revoked = someone can freeze any token-holding account and stop your tokens from moving. |

- If the authority holder is an **ordinary wallet**, the risk note says so plainly: “ordinary wallet: can mint / freeze at any time”;
- If it is a **program account (PDA)**, it means the authority sits with a contract (for example a bonding curve or a mining contract), and the page will say so;
- It also tells you whether the token is **SPL Token** or **Token-2022**, plus its decimals, total supply, and whether the supply is 0.

---

## Common notes

- **Queries occasionally fail**: on-chain data comes from public nodes, which can be busy or time out at peak times. The page retries automatically and shows a message if it still fails — **wait a few seconds and click again** and it usually works.
- **Mainnet actions are irreversible**: batch send, airdrop and consolidate all go on-chain for real. **We suggest switching to Devnet first** (top of the page) and rehearsing the whole flow with test funds until it's right, then going to Mainnet.
- **You pay the rent**: sending/airdropping to addresses that don't have a token account yet creates the account along the way, and about 0.002 SOL of rent each is deducted from your wallet; the page shows the count and total before sending.
- **Private key safety**: batch signing and consolidate need a private key. The private key is used only in browser memory; the platform never touches or stores it. But always do this **on your own computer**, and clear the input and refresh the page when you're done.

---

## Common messages

| Message | Description |
|---|---|
| `Too many requests, please try again later` / `Service temporarily unavailable, please try again later` | The service is busy — wait a few seconds and retry once |
| `Query timed out, please try again later` | Slow network or busy node — just retry |
| `N addresses don't have a token account yet; they will be created automatically on send` | A normal notice; you pay the rent, and you can try a small transaction first |
| `You cancelled the signature in your wallet` | You clicked reject in your wallet; just click send again |
| `Insufficient balance (not enough SOL for fees, or not enough for token account rent)` | Top up the main wallet with a bit of SOL |
| `This transaction doesn't fit (too many instructions)` | Lower the “max per transaction” |
| `No balance to sweep` | That wallet has no assets to consolidate and is counted as “skipped” |
