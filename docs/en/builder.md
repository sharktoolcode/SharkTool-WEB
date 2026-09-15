# Modular Launchpad

**Entry**: top nav "Modular Launchpad"

Assemble a token like building blocks: a module library on the left, drag modules onto the canvas on the right to combine them, with real-time conflict checking, then compile and deploy in one click. **23 built-in modules**.

**Prerequisites**:

- Pick a network in the top-right.
- **You must compile before deploying; deploying requires a connected wallet**.
- **Fee**: a platform service fee is charged, paid once together with the deploy transaction (a single signature); free while your Membership is active.

---

![Modular Launchpad page: drag modules from the "Gene Module Library" on the left onto the canvas on the right](images/builder.png)

## Steps

1. **Drag modules from the "Gene Module Library" on the left onto the canvas on the right**. There's a dashed ring in the middle of the canvas; drop when it's highlighted to add the module, and you'll see "Added "XXX"".
2. Modules on the canvas **can be dragged to reorder**, and you can remove one by clicking the trash icon in the top-right corner of its card.
3. **Fill in the parameters in each module card** (see the module list below).
4. Modules are **validated in real time** as you add them: missing dependencies, tax rates over the limit, or conflicting mechanics trigger an immediate alert.
5. Click **"Compile contract"**; on success you'll see "✅ Contract compiled! Ready to deploy".
6. Click **"Deploy token (owner = your wallet)"** and confirm the signature in your wallet.
7. On success: **"🎉 Modular token deployed! Added to Console"**. The page offers "View on block explorer", "Go to Console to manage", and "Deploy another".
8. If you used a tax module, you also need to **register the AMM trading pair** (see below).

---

## Module list (23)

| Category | Modules |
|---|---|
| **Basics** | Basic info (required, cannot be removed), address prefix, address suffix |
| **Trading tax** | AMM trading pair, marketing tax, burn tax, liquidity tax, dividend tax, foreign-currency tax (collect & convert) |
| **Wallet** | Referral reward (multi-level) |
| **Supply** | Mint more, burn, auto airdrop, black-hole dividend, holding compound interest, pool burn, LP mining, 314 protocol |
| **Switches & limits** | Trading switch, max transaction, max wallet, blacklist, KillBlock (anti-snipe) |

### Common parameter examples

- **Basic info**: token name, token symbol, decimals, total supply
- **Marketing tax / burn tax / liquidity tax / dividend tax**: buy tax rate, sell tax rate (percentage; entering `2` means 2%), plus the corresponding wallet address
- **Foreign-currency tax (collect & convert)**: tax base currency (native / USDT / USDC / custom token), foreign-currency buy and sell tax rates, receiving wallet, foreign-currency pair address, DEX router address, etc.
- **Max transaction / Max wallet**: enter a token amount; `0` means no limit
- **KillBlock**: monitored block count n, router address
- **Address prefix / address suffix**: specify the prefix or suffix of the deployed contract address, with EIP-55 case-exact matching supported

---

## Custom contract address (prefix / suffix)

This is a signature Modular Launchpad feature: you can make the deployed contract address **start or end with characters you specify**.

- Searching 1–2 characters is fast; 3–4 is slower, and **beyond 4 characters may take a long time or never be found**.
- During the search you'll see a "Tried XXX times" progress counter.
- Enabling "Case-sensitive" makes matching stricter and roughly doubles the search time.
- Prefix/suffix only accepts hexadecimal characters (0–9, a–f).

---

## Tax modules require registering an AMM trading pair

⚠️ **Tax only applies to "registered real trading pools".** If you add a tax module without binding a trading pair, the tax will never be collected.

After deployment:

1. In the **"Register AMM trading pair (required for buy/sell tax to take effect)"** block, paste your trading pair address.
2. Click **"✅ Register (enable tax)"**. Once done, buy/sell tax takes effect and is routed by direction to marketing / burn / liquidity / dividend.
3. To turn it off, click "Unregister".

---

## Common messages

| Message | What it means |
|---|---|
| `⚠️ Connect a wallet before deploying (top-right "Connect Wallet")` | Wallet not connected |
| `Please compile the contract first` | You clicked deploy directly |
| `The "Basic info" module is required` | Basic info is mandatory |
| `"XXX" depends on "YYY"; please add it first` | Modules have dependencies |
| `"Marketing tax" requires a marketing wallet address` | Parameters incomplete |
| `Total buy tax rate XX% must be less than 25%` | Total buy/sell tax rate has a cap |
| `Missing module: tax modules are enabled but the "AMM trading pair" module is missing…` | Add the AMM trading pair module |
| `Prefix/suffix can only contain hexadecimal characters (0-9, a-f)` | Address prefix/suffix format error |
| `⚠️ Tax modules are enabled but there is no "AMM trading pair" module on the canvas…` | A warning; deployment is unaffected but tax won't work |

---

## After deployment

- The token is **automatically added to "Console"**, where you can change tax rates, adjust switches, add blacklists, and more.
- See [Token Console](console.md).
