<script lang="ts">

  import Container from "$lib/components/Container.svelte"
  import Aura from "$lib/components/Aura.svelte"
  import Hero from '$lib/components/Hero.svelte'

  // import dev
  import { dev } from '$app/environment'

</script>

{#if dev}
  <div class="dev">dev mode</div>
{/if}

<div class="grid">
  <div class="info">
    <Container --max-width="600px">
      <Hero />
    </Container>
  </div>

  <main>
    <slot />
  </main>
</div>


<Aura />

<style lang="scss">

  .dev {
    background: var(--bg-accent);
    color: var(--bg-primary);
    position: fixed;
    left: 16px;
    bottom: 16px;
    border-radius: 8px;
    padding: 5px 10px;
    font-weight: 500;
    z-index: 9999999;
    pointer-events: none;
  }

  .grid {
    display: grid;
    grid-template-columns: var(--colwidth) 1fr;
  }

  .info {
    display: flex;
    flex-direction: column;
    position: relative;
    max-height: 100vh;
    overflow-y: scroll;
    z-index: var(--zindex-top);
    align-items: center;
    // justify-content: center;
    padding: 0 var(--16px);
    background: var(--bg-primary);
    backdrop-filter: blur(10px);
    box-shadow: 1px 0 0 var(--bg-tertiary);
  }

  main {
    display: flex;
    flex-direction: column;
    height: 100vh;
    max-height: 100vh;
    position: relative;
    overflow-y: auto;
  }

</style>