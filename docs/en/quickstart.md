# Quick start

Before you use any feature, there are only three things you need: **connect your wallet**, **pick the right network**, and **get to know the buttons in the top-right corner**.

![Top-right of the page: language EN, light/dark theme, network switcher, Connect Wallet](images/quickstart-navbar.png)

---

## 1. Connect Wallet

Find the **“👛 Connect Wallet”** button in the top-right corner. Click it and you'll see two options:

| Option | When to use it |
|---|---|
| **🦊 MetaMask / browser wallet** | On desktop. Supports browser extension wallets such as MetaMask, OKX, Trust and Coinbase |
| **📱 QR code (WalletConnect)** | On mobile. Scan the QR code with your mobile wallet to connect to the site on your computer |

- Once connected, the top-right corner shows your shortened address (e.g. `0x1234...abcd`).
- **Connect once, use everywhere**: you won't need to reconnect for any other feature.
- Refreshing the page restores your previous connection, so you don't get repeated popups.

> 🔐 **Your private key always stays in your wallet; this website can never access it.** Every action that costs money or changes on-chain state pops up your wallet for you to confirm.

### Disconnect

Click your own address in the top-right corner. The menu has **“🔌 Disconnect”** and **“📋 Copy address”**.

---

## 2. Choose a network

The dropdown in the top-right corner shows the current network, for example **“🟡 BSC Mainnet (56)”**. Click it to switch:

| Network | Description |
|---|---|
| 🟡 BSC Mainnet | BNB Smart Chain, the most commonly used |
| 🧪 BSC Testnet | For practice; free test tokens |
| 💎 Ethereum | Ethereum Mainnet |
| 🟣 Polygon | Polygon Mainnet |
| 🔵 Arbitrum | Arbitrum One |
| 🔷 Base | Base Mainnet |

A connected Solana wallet is a **separate setup** and does not use the chain selector here — see “4. Solana wallet” below.

### Switching networks syncs your wallet automatically

After you switch networks on the site, the site asks your wallet to switch along with it and shows a message:

- `Switching your wallet to XXX automatically...`
- `Wallet switched to XXX automatically`
- If your wallet does not support automatic switching, it will tell you to switch manually in your wallet.

> ⚠️ Before actions such as launching a token or creating a pool, make sure the **network in the top-right of the site** and the **network in your wallet** are the same, otherwise the transaction will fail.

---

## 3. Language and theme

There are two more small buttons in the top-right corner:

- **Language**: the Chinese interface shows `🌐 EN` — click it to switch to English; the English interface shows `🌐 中文`.
- **Theme**: dark theme shows `☀️`, light theme shows `🌙`.

Both settings are remembered, and the next time you open the site they stay as you left them.

---

## 4. Solana wallet

Solana features (launching a token, vanity addresses, creating a pool) are on the **“Solana”** page and need a separate Solana wallet connection.

Go to the **Solana** page and click **“Connect Wallet”**. Three wallets are supported:

| Wallet | Description |
|---|---|
| **Phantom** | The most popular Solana wallet |
| **Solflare** | Supports staking and hardware wallets |
| **Backpack** | xNFT ecosystem wallet |

- Wallets you have not installed show as “Not installed”; clicking opens the matching install page.
- Once connected, the button shows the address and balance; click it again to disconnect.
- At the top of the page you can switch between **Mainnet** and **Devnet**. After switching to Devnet, a **“💧 Get test SOL”** button appears so you can claim 1 SOL free for practice.

> ⚠️ Remember to **switch your wallet to the same cluster** (Mainnet/Testnet) too, otherwise the balance and transactions won't line up.

---

## 5. Feedback in the bottom-right corner

There is a floating button in the bottom-right corner; click it to leave feedback for the site owner. No sign-up and no wallet connection is needed to submit.

---

## Next steps

- Want to check a token? → [Token Analyzer](analyze.md)
- Want to launch a token? → [Token Cloner](launch.md) or [Modular Launchpad](builder.md)
- Want to save money? → [Membership](membership.md)
