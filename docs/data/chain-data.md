# Chain Data

# Chain Data

On-chain data fetching using Alchemy Enhanced APIs.

## Features

- **token-balances**: Enabled
- **nft-data**: Enabled

## Usage

```tsx
import { useTokenBalances, useNFTs, useTransactionHistory } from '@/hooks/useChainData';

function Portfolio() {
  const { data: tokens } = useTokenBalances();
  const { data: nfts } = useNFTs();
  
  return (
    <div>
      <TokenList tokens={tokens} />
      <NFTGallery nfts={nfts} />
    </div>
  );
}
```
