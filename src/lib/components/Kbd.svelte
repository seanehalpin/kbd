<script lang="ts">

  import { fade, fly, blur } from 'svelte/transition'
  import { onMount } from 'svelte'

  let ready = false
  onMount(() => {
    ready = true
  })

  export let title = ""
  export let keys: any[] = []
  export let styles:any[] = []

  let activeStyle = styles[0]

  $: console.log(activeStyle)

  let showStyles = false, showTitle = false

  const hoverIn = () => {
    showStyles = true
    showTitle = true
  }

  const hoverOut = () => {
    showStyles = false
    showTitle = false
  }

  const changeStyle = (value: any) => {
    activeStyle = styles.find(style => style.style === value)
  }

</script>

{#if ready}
  <div class="kbd-holder" on:mouseenter={() => hoverIn()} on:mouseleave={() => hoverOut()} in:fade={{duration:400, delay:600}}>
    {#if showTitle}
    <div class="kbd-title" in:fade|local={{duration:250}} out:fade|local={{duration:150}}>
      <span>{title}</span>
    </div>
    {/if}
    <div class="kbd-content">
      <div class="kbd-inner">
        {#each keys as key} 
        {#key activeStyle}
          <kbd 
            in:fade|local={{duration:250}} 
            class="{title.toLowerCase()} {activeStyle.style}"
          >
          <span>{key}</span>
          </kbd>
        {/key}
        {/each}
      </div>
    </div>
    {#if showStyles}
    {#if styles.length >= 2}
    <div class="styles">
      {#each styles as style, i}
      <!-- <button style="background:{style.color}" in:fade={{duration:300, delay:i*150}} out:fade={{duration:200}}>
        <span>{style.style}</span>
      </button> -->
      <input 
        type="radio" 
        class="radio"
        name={title} 
        value={style.style} 
        checked={style.checked}
        style="background:{style.color}" in:fade={{duration:300}} out:fade={{duration:200}} 
        on:click={() => changeStyle(style.style)}
        >
      {/each}
    </div>
    {/if}
    {/if}
  </div>
{/if}

<style lang="scss">

  @import "../../kbd";

  .kbd-holder {
    width: 100%;
    position: relative;
  }

  .kbd-title {
    position: absolute;
    left: 0;
    top: var(--24px);
    display: flex;
    align-items: center;
    justify-content: center;
    z-index: var(--zindex-2);
    width: 100%;

    span {
      font-size: var(--16px);
      font-weight: 500;
      color: var(--text-primary);
      border: 1px solid var(--bg-secondary);
      background: transparent;
      // box-shadow: 0 0 0 4px var(--bg-primary);
      border-radius: 20px;
      padding: 0px var(--16px);
    }
  }

  .kbd-content {
    border: 1px solid var(--bg-tertiary);
    height: 300px;
    border-radius: var(--radius-base);
    position: relative;
    // top: -14px;
    z-index: var(--zindex-1);
    display: flex;
    align-items: center;
    justify-content: center;
    --_background: var(--background, transparent);
    background: var(--_background);
    // box-shadow: inset 0 0 0 4px var(--bg-primary);
    backdrop-filter: blur(10px);
  }

  kbd {
    display: flex;
    align-items: center;
    justify-content: center;
    --_fontsize: var(--fontsize, var(--16px));
    font-size: var(--_fontsize);
    font-family: var(--systemFont);
    cursor: default;
    position: relative;
    
    span {
      position: relative;
      z-index: var(--zindex-content);
      display: flex;
      justify-content: center;
      align-items: center;
    }

  }

  .kbd-inner {
    display: flex;
    align-items: center;
    justify-content: center;
    --_gap: var(--gap, 3px);
    gap: var(--_gap);
  }

  .styles {
    position: absolute;
    bottom: 40px;
    left: 50%;
    transform: translate3d(-50%, 0, 0);
    display: flex;
    align-items: center;
    justify-content: center;
    gap: var(--16px);
    z-index: var(--zindex-content);

  }

  .radio {
    appearance: none;
    margin: 0;
    border-radius: 50%;
    width: 18px;
    height: 18px;
    border: 0;
    display: grid;
    place-content: center;
    box-shadow: 0 0 0 2px var(--bg-primary), 0 0 0 4px var(--bg-tertiary);
    position: relative;
    cursor: pointer;

    &:active, &:focus {
      box-shadow: 0 0 0 2px var(--bg-primary), 0 0 0 4px var(--bg-tertiary) !important;
    }

    &:focus-visible {
      outline: none !important;
      box-shadow: 0 0 0 2px var(--bg-accent) !important;
    }
    

    // &::before {
    //   content: "";
    //   width: 20px;
    //   height: 20px;
    //   border-radius: 50%;
    //   background: transparent;
    //   box-shadow: 0 0 0 3px var(--bg-primary), 0 0 0 5px var(--bg-accent);
    //   opacity: 0;
    //   transition: all 0.2s ease-in-out;
    // }

    // &:checked {
    //   &::before {
    //     opacity: 1;
    //   }
    // }

  }

</style>