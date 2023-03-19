<script lang="ts">

  import { fade, fly, blur } from 'svelte/transition'
  import { onMount } from 'svelte'

  let ready = false
  $: inputValue = ''
  onMount(() => {
    ready = true
  })

</script>

{#if ready}
<div class="search-holder" in:fade={{duration:600, delay:800}}>
  <div class="search">
    {#if inputValue.length > 0}
    <div class="icon" in:fade|local={{duration:250}} out:fade|local={{duration:250}}>
      <svg xmlns="http://www.w3.org/2000/svg" width="20" height="20" viewBox="0 0 24 24" fill="none"  stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round"><path d="M21 4H8l-7 8 7 8h13a2 2 0 0 0 2-2V6a2 2 0 0 0-2-2z"></path><line x1="18" y1="9" x2="12" y2="15"></line><line x1="12" y1="9" x2="18" y2="15"></line></svg>
    </div>
    {/if}
    <input type="text" bind:value={inputValue} placeholder="Focus and type keys">
  </div>
</div>
{/if}

<style lang="scss">

  .search-holder {
    display: flex;
    align-items: center;
    justify-content: center;
    padding: 0;
    height: var(--top-height);
    width: 100%;
    position: relative;
    // backdrop-filter: blur(5px);
  }

  .search {
    display: flex;
    align-items: center;
    justify-content: center;
    width: 100%;
    position: relative;
  }

  .icon {
    display: flex;
    position: absolute;
    right: var(--16px);
    top: 50%;
    transform: translate3d(0, -50%, 0);
    stroke: var(--text-primary);
    font-size: var(--20px);
    z-index: var(--zindex-2);
  }

  input {
    display: flex;
    height: 50px;
    width: 100%;
    padding: 0 calc(var(--16px));
    font-size: var(--16px);
    border-radius: var(--radius-sm);
    border: 0;
    background: var(--bg-tertiary);
    // background: transparent;
    transition: all 0.2s ease-in-out;
    color: var(--text-primary);
    box-shadow: 0 0 0 1px var(--bg-secondary);
    backdrop-filter: blur(10px);
    position: relative;
    z-index: var(--zindex-1);

    &:focus {
      outline: none !important;
      box-shadow: 0 0 0 2px var(--bg-invert) !important;
    }

    &::placeholder {
      color: var(--text-secondary);
    }
  }


</style>