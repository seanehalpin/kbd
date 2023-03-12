<script lang="ts">

  import { fade, fly, blur } from 'svelte/transition'
  import { onMount } from 'svelte'
  import Container from "$lib/components/Container.svelte"
  import Hero from '$lib/components/Hero.svelte'

  // imprort dev
  import { dev } from '$app/environment';

  let ready = false
  onMount(() => {
    ready = true
  })

</script>

{#if ready}
{#if dev}
<div class="dev">dev mode</div>
{/if}
<Container>
  <Hero />
</Container>
{/if}

<style lang="scss">

.dev {
  background: var(--bg-accent);
  color: var(--bg-primary);
  position: fixed;
  left: 16px;
  top: 16px;
  border-radius: 8px;
  padding: 5px 10px;
  font-weight: 500;
  z-index: 9999999;
}

</style>