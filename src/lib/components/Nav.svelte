<script lang="ts">

  import { fade, fly, blur } from 'svelte/transition'
  import { onMount } from 'svelte'
  import Controls from './Controls.svelte';

  let ready = false
  onMount(() => {
    ready = true
  })

</script>

{#if ready}
<!-- <h1 in:fade={{duration:600, delay:200}}><span>&lt;</span>kbd<span>&gt;</span></h1> -->
<nav in:fade|local={{duration:250, delay:500}}>
  <div class="logo">
    <img src="/logo.svg" alt="">
  </div>

  <Controls />

  <!-- <div class="details">
    Stylish, minimalist <kbd>kbd</kbd> component for Svelte apps
  </div> -->

  <a href="#">
    <svg width="14" height="14" viewBox="0 0 14 14" fill="none" xmlns="http://www.w3.org/2000/svg"><path d="M7 0.175049C3.128 0.175049 0 3.30305 0 7.17505C0 10.259 2.013 12.885 4.79 13.825C5.14 13.891 5.272 13.672 5.272 13.497V12.316C3.325 12.731 2.909 11.375 2.909 11.375C2.581 10.565 2.122 10.347 2.122 10.347C1.488 9.90905 2.166 9.93105 2.166 9.93105C2.866 9.97505 3.237 10.653 3.237 10.653C3.872 11.725 4.878 11.419 5.272 11.243C5.338 10.784 5.512 10.478 5.709 10.303C4.156 10.128 2.516 9.51605 2.516 6.84705C2.516 6.08105 2.778 5.46905 3.237 4.96605C3.172 4.79105 2.931 4.06905 3.303 3.10605C3.303 3.10605 3.893 2.90905 5.228 3.82805C5.79831 3.67179 6.38668 3.5911 6.978 3.58805C7.568 3.58805 8.181 3.67505 8.728 3.82805C10.063 2.93105 10.653 3.10605 10.653 3.10605C11.025 4.06905 10.784 4.79105 10.719 4.96605C11.179 5.44605 11.441 6.08105 11.441 6.84605C11.441 9.53705 9.8 10.128 8.247 10.303C8.487 10.522 8.728 10.937 8.728 11.593V13.519C8.728 13.716 8.859 13.934 9.209 13.847C11.988 12.884 14 10.259 14 7.17505C14 3.30305 10.872 0.175049 7 0.175049V0.175049Z"></path>
    </svg>
    <span>seanehalpin/kbd</span>
  </a>
</nav>

{/if}

<style lang="scss">

  @import "../../mixins";

  nav {
    width: 100%;
    display: flex;
    justify-content: space-between;
    align-items: center;
    gap: var(--24px);
    padding: 0 var(--24px);
    height: var(--top-height);
    box-shadow: inset 0 -1px 0 0 var(--bg-secondary);
    background: var(--color-violetbg);

    @include md {
      background: transparent;
    }
  }

  .logo {
    display: flex;
    height: var(--top-height);
    align-items: center;
    justify-content: space-between;
    position: relative;
    z-index: var(--zindex-2);
  }

  a {
    opacity: 1;
    display: flex;
    font-size: var(--font-sd);
    color: var(--color-white);
    align-items: center;
    gap: 6px;
    text-decoration: none;
    border-radius: var(--radius-base);
    transition: all 0.2s linear;
    padding: 4px 12px;
    border-radius: var(--radius-base);
    position: relative;
    z-index: var(--zindex-2);

    &:hover {
      background: var(--color-white100);
    }

    svg {
      path {
        fill: var(--color-white);
      }
    }
  }

</style>

