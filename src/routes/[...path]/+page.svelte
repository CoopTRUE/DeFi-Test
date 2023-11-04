<script lang="ts">
  import { page } from '$app/stores'

  $: ({ pathname } = $page.url)
</script>

<h1 class="mb-4 text-4xl font-medium">404</h1>
<p>
  Huh, looks like <code class="mx-1 rounded bg-muted p-1 text-muted-foreground">{pathname}</code> doesn't
  exist.
</p>
