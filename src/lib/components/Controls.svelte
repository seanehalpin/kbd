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
<div class="search-holder">
  <div class="search">
    {#if inputValue.length > 0}
    <div class="icon" in:fade|local={{duration:100}} out:fade|local={{duration:100}}>
      <svg xmlns="http://www.w3.org/2000/svg" width="20" height="20" viewBox="0 0 24 24" fill="none"  stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round"><path d="M21 4H8l-7 8 7 8h13a2 2 0 0 0 2-2V6a2 2 0 0 0-2-2z"></path><line x1="18" y1="9" x2="12" y2="15"></line><line x1="12" y1="9" x2="18" y2="15"></line></svg>
    </div>
    {/if}
    <input type="text" bind:value={inputValue} placeholder="Focus and type keys">
  </div>
</div>
{/if}

<style lang="scss">

  @import "../../mixins";

  .search-holder {
    flex:1;
    display: flex;
    align-items: flex-start;
    justify-content: center;
    // padding: 1px 0 0;
    // height: var(--top-height);
    width: 100%;
    position: relative;
    // backdrop-filter: blur(5px);
    // box-shadow: 0 1px 0 0 var(--bg-secondary);
    z-index: var(--zindex-top);
    // padding: 0 var(--24px) var(--24px);
  
    @include lg {
      position: absolute;
      left: 0;
      z-index: var(--zindex-1);
    }
  
  }

  .search {
    display: flex;
    align-items: center;
    justify-content: center;
    width: 100%;
    max-width: 600px;
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

    svg {
      stroke: var(--color-white);
    }
  }

  input {
    display: flex;
    height: 40px;
    width: 100%;
    padding: 0 calc(var(--16px));
    font-size: var(--font-sd);
    border-radius: var(--radius-base);
    border: 0;
    // background: var(--color-white100);
    background: transparent;
    transition: all 0.2s ease-in-out;
    color: var(--color-white);
    box-shadow: inset 0 0 0 1px var(--color-white200);
    backdrop-filter: blur(10px) saturate(130%);
    position: relative;
    z-index: var(--zindex-1);
    font-weight: 600;

    &:focus {
      outline: none !important;
      background: var(--color-white200);
      box-shadow: inset 0 0 0 1px var(--color-white400) !important;
      backdrop-filter: blur(10px);

      &::placeholder {
        color: var(--color-white300);
        text-align: left;
      }

    }

    &::placeholder {
      font-weight: 400;
      transition: all 0.2s linear;
      color: var(--color-white700);
      text-align: center;
    }
  }


</style>