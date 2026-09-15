# Token Console

**Entry**: top nav "Console"

Manage all the tokens you've launched in one place: view their real-time on-chain status and directly call the contract's admin functions online (change tax rate, add blacklist, pause trading, mint more, burn, renounce ownership...).

**Cost**: Free (calling functions only costs on-chain gas; the platform charges nothing extra).

**Prerequisites**:

- Pick a network in the top-right.
- **Viewing status doesn't require a wallet**; **executing admin functions requires a connected wallet**.

---

![Token Console: paste a contract address, then click "Add"](images/console.png)

## Steps

### Add a token

There are two ways:

- **Auto-added**: any token deployed on this platform automatically appears in the list (marked "My deployment").
- **Add manually**: paste a contract address into the field at the top, click **"Add"**, and you'll see "Added to Console".

> A manually added contract **must be open-source**; otherwise the ABI can't be retrieved and management features are unavailable.

### View real-time on-chain status

Click a token in the list to open its detail page:

- **Basic info card**: name, symbol, chain, address. You can jump to the block explorer, or "Remove" it from the Console (this only affects your local list, not the on-chain contract).
- **Real-time on-chain status**: automatically reads the contract's public getters to show live values such as current tax, limits, and authorities.

### Call admin functions

1. Expand a function under **"Admin functions (callable contract functions)"**. Only admin functions that actually change state are listed here (change tax, change wallet, switches, blacklist, etc.); standard transfer functions are excluded.
2. Fill in parameters as prompted (addresses use `0x...`; arrays follow the example format; watch the units for numeric values — tax-rate values are usually per mille, i.e. parts per thousand).
3. Click **"Execute functionName()"** and confirm the signature in your wallet.
4. The page shows "Calling..." → "Waiting for transaction confirmation..." → "✅ Transaction confirmed", and gives a transaction link.

### AI function explanations

Each function has a **"🤖 Explain"** button next to it — click it to see what the function does, what the risks of calling it are, and how to fill in its parameters.

---

## Common messages

| Message | What it means |
|---|---|
| `Please enter a valid contract address` | Address format is wrong |
| `Unable to get contract info (not open-source or invalid address)` | Contract isn't open-source, or the address doesn't exist |
| `No deployed tokens yet` | List is empty; launch a token or add one manually |
| `No writable functions found (requires contract ABI; unavailable if not open-source)` | Contract is not open-source |
| `⚠️ Wallet not connected; connect before executing (top-right)` | Connect your wallet before executing functions |
| `Contract ABI not retrieved (not open-source?); management features unavailable` | Same as above |

> 💡 The Console only exposes "admin" functions and will **not** execute transfer operations on your behalf; every call still requires your confirmation in your wallet.
