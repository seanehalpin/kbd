<script lang="ts">

  import { fade, fly, blur } from 'svelte/transition'
  import { onMount } from 'svelte'
  import Container from "$lib/components/Container.svelte"
  import Hero from '$lib/components/Hero.svelte'

  // imprort dev
  import { dev } from '$app/environment';
    import Search from '$lib/components/Search.svelte';

  let ready = false
  onMount(() => {
    ready = true
  })

</script>

<svelte:head><title>KBD.</title></svelte:head>


{#if ready}
  {#if dev}
    <div class="dev">dev mode</div>
  {/if}
  <Container>
    <Hero />
  </Container>
  <Container sticky={true} --left="0" --top="0">
    <Search />
  </Container>
  <div class="padded">
    
  </div>
{/if}

<style lang="scss">

  .padded {
    position: relative;
    padding-bottom: 100vh;
  }

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
    pointer-events: none;
  }

</style>