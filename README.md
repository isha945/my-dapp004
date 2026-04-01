# My Dapp

A Web3 application - composed with [N]skills

## Blueprint: selected nodes

These components were included in this generation:

- **ERC-721 Stylus NFT** — Deploy and interact with ERC-721 NFTs on Arbitrum Stylus
- **SmartCache Caching** — Enable contract caching for cheaper gas - mycontracts (original) + cached-contracts (with caching)
- **Wallet Authentication** — Wallet connection with RainbowKit and WalletConnect
- **Chain Data** — Token/NFT data fetching with Moralis or Alchemy Enhanced APIs
- **Auditware Analyzer** — Security analysis with Radar for Rust smart contracts

## Project structure

```
my-dapp/
├── package.json                # Workspace root (pnpm)
├── contracts/                  # Rust/Stylus smart contracts
│   ├── mycontract/            # Original contract (no caching)
│   │   └── src/lib.rs
│   └── cached-contract/       # Contract with is_cacheable helper
│       └── src/lib.rs
├── docs/                       # Documentation
├── scripts/                     # Deploy / utility scripts (if generated)
├── .gitignore
└── README.md
```

## Quick start

### Prerequisites

- **Node.js** 18+ and a package manager (**pnpm** recommended; npm/yarn work if you adapt commands)
- **Rust** toolchain and **cargo-stylus** for building/deploying Stylus contracts (see `docs/` and [Stylus SDK](https://github.com/OffchainLabs/stylus-sdk-rs))

### Step-by-step

1. **Clone and enter the project**

   ```bash
   git clone <your-repo-url>
   cd my-dapp
   ```

2. **Install dependencies** (workspace root — uses [pnpm](https://pnpm.io) workspaces):

   ```bash
   pnpm install
   ```

   This installs all workspace packages (including `apps/web` when present).

3. **Environment variables**

   ```bash
   cp .env.example .env
   ```

   Edit `.env` and set:

   - `PRIVATE_KEY`: Private key for deployment and transactions
   - `NEXT_PUBLIC_WALLETCONNECT_PROJECT_ID`: WalletConnect Cloud project ID
   - `NEXT_PUBLIC_ALCHEMY_API_KEY`: Alchemy API key for data fetching

### Smart contracts (build / deploy)

Use the Stylus / Rust workflow for folders under `contracts/`. See `docs/` for node-specific steps and any `scripts/` helpers.


### Line endings (Windows)

If shell scripts fail with `\r` errors, normalize line endings (e.g. `dos2unix scripts/*.sh`) or configure Git to check out LF on Windows.

## Generated scripts

Run these from the **repository root** (root `package.json`).

| Command | Description |
|---------|-------------|
| `deploy:erc721` | Deploy ERC721 collection |
| `nft:info` | Get NFT collection information |
| `fix-scripts` | command -v dos2unix >/dev/null && dos2unix scripts/*.sh 2>/dev/null \|\| echo "Run: dos2unix scripts/*.sh (install with: apt install dos2unix / brew install dos2unix)" |
| `wallet:setup` | Instructions for wallet setup |
| `security:install` | bash scripts/install-radar.sh |
| `security:analyze` | bash scripts/run-radar.sh |
| `deploy:sepolia` | bash scripts/deploy-sepolia.sh |
| `deploy:mainnet` | bash scripts/deploy-mainnet.sh |

## Documentation

Check the `docs/` folder for guides that match your blueprint (e.g. frontend setup, contract deployment, API routes).

## License

MIT

---

Generated with [[N]skills](https://www.nskills.xyz)
