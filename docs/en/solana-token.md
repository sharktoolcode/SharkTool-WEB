# Solana Launch

**Entry**: top nav “Solana” → “🚀 Launch” tab

Create a real SPL token on Solana: **a single signature** creates the mint, initializes it, creates the token account, mints, and writes on-chain metadata — with optional authority revocation.

**Prerequisites**:

- Connect a **Solana wallet** (Phantom / Solflare / Backpack) — Solana uses its own wallets, separate from the EVM set.
- Switch **Mainnet** or **Devnet** at the top of the page. We suggest practising on **Devnet** first, where you can claim 1 SOL of free test funds.
- **Fees**: platform service fee + on-chain rent and network fee. The platform service fee is waived while your Membership is active.

---

![Solana Suite “Launch” tab: token details on the left, live preview and fee breakdown on the right](images/solana-launch.png)

## Steps

### 1. Fill in the token details

| Field | Description |
|---|---|
| **Token name** | Written to on-chain metadata |
| **Token symbol** | e.g. SHARK |
| **Decimals** | SPL tokens usually use 9 |
| **Total supply** | Keep the mint authority if you want to mint more later |
| **Description** | Written to on-chain metadata |
| **Token icon** | 512×512 square PNG/JPG recommended, ≤512KB |

### 2. Choose authorities

- **Revoke mint authority** — recommended; once revoked, no one can mint more.
- **Revoke freeze authority** — once revoked, no one can freeze your token-holding addresses.

### 3. Check the fee breakdown

The right side of the page lists the full cost of this transaction, item by item:

- Account rent (mint)
- Account rent (token account ATA)
- Account rent (Metaplex metadata)
- Network transaction fee
- **Platform service fee** (shows “Free for members” with Membership)
- **Total**, plus your **wallet balance**

> The storage cost for the token icon and metadata is paid by your wallet (a very small amount); the page lists it as well.

### 4. Create

Click **“🚀 Create token”** (subtext: create in one signature · automatic rollback on failure), and you'll see in turn:

`Connecting to the storage service…` → `Uploading icon and metadata…` → `Submitting the creation transaction, please confirm in your wallet…`

On success you'll see **“🎉 Token created, metadata is on-chain”**, along with the mint address, transaction link and metadata link.

> 💡 After creation, wallets like Phantom may take a moment to index the name/icon — just wait a little.

---

## 📦 My Tokens

**Entry**: Solana page → “📦 My Tokens” tab

This lists the tokens you've created on this platform. **Supply and authorities are queried live from the chain**:

- Table columns: token, mint address, on-chain supply, authorities, actions.
- Authority badges: `Can mint` / `Mint authority revoked`, `Can freeze` / `Freeze authority revoked`.
- Actions: “Trade” opens the block explorer; “Remove” only deletes the entry from your local list and **does not affect the on-chain token**.

---

## Common messages

| Message | Description |
|---|---|
| `Please connect a Solana wallet first` | Connect your wallet first |
| `Please enter a token name and symbol` | A required field is empty |
| `Total supply must be greater than 0` | The amount is wrong |
| `Insufficient balance: switch to Devnet to claim test funds` | Your wallet balance doesn't cover rent and fees |
| `You cancelled the signature in your wallet` | You cancelled normally — just retry |

---

## Related

- Want a nicer address? → [Solana Vanity Address](solana-vanity.md)
- Want to create a pool for your token? → [Solana Liquidity](solana-liquidity.md)
