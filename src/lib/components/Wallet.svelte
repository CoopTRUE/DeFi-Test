<script lang="ts">
  import { PUBLIC_WALLET_CONNECT_PROJECT_ID } from '$env/static/public'
  import { Button } from '$lib/components/ui/button'
  import { mainnet, arbitrum } from '@wagmi/core/chains'
  import { createWeb3Modal, defaultWagmiConfig } from '@web3modal/wagmi'
  import { Wallet } from 'lucide-svelte'
  import { onMount } from 'svelte'

  const chains = [mainnet, arbitrum]
  const wagmiConfig = defaultWagmiConfig({
    chains,
    projectId: PUBLIC_WALLET_CONNECT_PROJECT_ID,
    metadata: {
      name: 'Web3Modal',
      description: 'Web3Modal Example',
      url: 'https://web3modal.com',
      icons: ['https://avatars.githubusercontent.com/u/37784886'],
    },
  })
  const modal = createWeb3Modal({
    wagmiConfig,
    projectId: PUBLIC_WALLET_CONNECT_PROJECT_ID,
    chains,
  })
</script>

<w3m-button />
