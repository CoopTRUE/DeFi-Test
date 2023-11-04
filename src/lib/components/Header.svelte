<script lang="ts">
  import { browser } from '$app/environment'
  import { Button } from '$lib/components/ui/button'
  import * as DropdownMenu from '$lib/components/ui/dropdown-menu'
  import Wallet from './Wallet.svelte'
  import {
    ChevronDown,
    Briefcase,
    Building2,
    Twitter,
    BookOpen,
    Shield,
    Globe,
  } from 'lucide-svelte'
  import { onMount } from 'svelte'

  let loaded = false
  onMount(async () => {
    await new Promise((resolve) => setTimeout(resolve, 1000))
    loaded = true
  })
</script>

<header class="flex items-center justify-between p-4">
  <div class="">
    <Button href="/" size="sm">Home</Button>
  </div>
  <nav class="flex gap-4">
    <DropdownMenu.Root>
      <DropdownMenu.Trigger asChild let:builder>
        <Button builders={[builder]} variant="ghost" class="group">
          About
          <ChevronDown
            size="1.25em"
            class="ml-2 mt-1 transition-transform duration-150 group-data-[state='open']:-rotate-180"
          />
        </Button>
      </DropdownMenu.Trigger>
      <DropdownMenu.Content>
        <DropdownMenu.Item href="/about">
          <Building2 size="1.25em" class="mr-2" />
          Company
        </DropdownMenu.Item>
        <DropdownMenu.Item href="/careers">
          <Briefcase size="1.25em" class="mr-2" />
          Careers
        </DropdownMenu.Item>
      </DropdownMenu.Content>
    </DropdownMenu.Root>
    <DropdownMenu.Root>
      <DropdownMenu.Trigger asChild let:builder>
        <Button builders={[builder]} variant="ghost" class="group">
          Community
          <ChevronDown
            size="1.25em"
            class="ml-2 mt-1 transition-transform duration-150 group-data-[state='open']:-rotate-180"
          />
        </Button>
      </DropdownMenu.Trigger>
      <DropdownMenu.Content>
        <DropdownMenu.Item>
          <img src="https://cdn.simpleicons.org/discord/FFFFFF" alt="" class="mr-2 w-5" />
          Discord
        </DropdownMenu.Item>
        <DropdownMenu.Item>
          <Twitter size="1.25em" class="mr-2" />
          Twitter
        </DropdownMenu.Item>
      </DropdownMenu.Content>
    </DropdownMenu.Root>
    <DropdownMenu.Root>
      <DropdownMenu.Trigger asChild let:builder>
        <Button builders={[builder]} variant="ghost" class="group">
          Resources
          <ChevronDown
            size="1.25em"
            class="ml-2 mt-1 transition-transform duration-150 group-data-[state='open']:-rotate-180"
          />
        </Button>
      </DropdownMenu.Trigger>
      <DropdownMenu.Content>
        <DropdownMenu.Item href="http://www.google.com">
          <Globe size="1.25em" class="mr-2" />
          Blog
        </DropdownMenu.Item>
        <DropdownMenu.Item href="http://www.google.com">
          <BookOpen size="1.25em" class="mr-2" />
          Documentation
        </DropdownMenu.Item>
        <DropdownMenu.Item href="http://www.google.com">
          <Shield size="1.25em" class="mr-2" />
          Audits
        </DropdownMenu.Item>
      </DropdownMenu.Content>
    </DropdownMenu.Root>
  </nav>
  {#if browser && loaded}
    <Wallet />
  {/if}
</header>
