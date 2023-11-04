<script>
  import Header from '$lib/components/Header.svelte'
  import ProgressBar from '$lib/components/ProgressBar.svelte'
  import '../app.css'
</script>

<ProgressBar />
<div class="container flex min-h-screen flex-col">
  <Header />
  <div class="flex-1">
    <slot />
  </div>
</div>
