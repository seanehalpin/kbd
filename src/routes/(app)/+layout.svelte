<script lang="ts">

  import Container from "$lib/components/Container.svelte"
  import Aura from "$lib/components/Aura.svelte"
  import Nav from '$lib/components/Nav.svelte'

  // import dev
  import { dev } from '$app/environment'

</script>

{#if dev}
  <div class="dev">dev mode</div>
{/if}

<div class="holder">
  <div class="info">
    <Nav />
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

  .holder {
    display: flex;
    flex-direction: column;
    // grid-template-columns: var(--colwidth) 1fr;
  }

  .info {
    // display: flex;
    // flex-direction: column;
    position: relative;
    z-index: var(--zindex-top);
    // align-items: center;
    // justify-content: center;
    // background: var(--bg-primary);
    // box-shadow: 1px 0 0 var(--bg-tertiary);
  }

  main {
    display: flex;
    flex-direction: column;
    height: 100vh;
    max-height: 100vh;
    position: relative;
    overflow-y: auto;
    // margin: 0 var(--24px);
    // padding: var(--24px);
    // border-radius: 14px 14px 0 0;
    background: var(--bg-base);
    z-index: var(--zindex-top);
  }

</style>