<script lang="ts">

  import { fade, fly, blur } from 'svelte/transition'
  import { onMount } from 'svelte'

  let ready = false
  onMount(() => {
    ready = true
  })

</script>

{#if ready}
<!-- <h1 in:fade={{duration:600, delay:200}}><span>&lt;</span>kbd<span>&gt;</span></h1> -->
<div class="info">

  <div class="logo">
    <img src="/logo.svg" alt="">
    <a href="#">
      <svg width="14" height="14" viewBox="0 0 14 14" fill="none" xmlns="http://www.w3.org/2000/svg"><path d="M7 0.175049C3.128 0.175049 0 3.30305 0 7.17505C0 10.259 2.013 12.885 4.79 13.825C5.14 13.891 5.272 13.672 5.272 13.497V12.316C3.325 12.731 2.909 11.375 2.909 11.375C2.581 10.565 2.122 10.347 2.122 10.347C1.488 9.90905 2.166 9.93105 2.166 9.93105C2.866 9.97505 3.237 10.653 3.237 10.653C3.872 11.725 4.878 11.419 5.272 11.243C5.338 10.784 5.512 10.478 5.709 10.303C4.156 10.128 2.516 9.51605 2.516 6.84705C2.516 6.08105 2.778 5.46905 3.237 4.96605C3.172 4.79105 2.931 4.06905 3.303 3.10605C3.303 3.10605 3.893 2.90905 5.228 3.82805C5.79831 3.67179 6.38668 3.5911 6.978 3.58805C7.568 3.58805 8.181 3.67505 8.728 3.82805C10.063 2.93105 10.653 3.10605 10.653 3.10605C11.025 4.06905 10.784 4.79105 10.719 4.96605C11.179 5.44605 11.441 6.08105 11.441 6.84605C11.441 9.53705 9.8 10.128 8.247 10.303C8.487 10.522 8.728 10.937 8.728 11.593V13.519C8.728 13.716 8.859 13.934 9.209 13.847C11.988 12.884 14 10.259 14 7.17505C14 3.30305 10.872 0.175049 7 0.175049V0.175049Z"></path>
      </svg>
      <span>seanehalpin/kbd</span>
    </a>
  </div>

  <div class="text-holder">
    <p in:fade={{duration:600, delay:400}}>Stylish, minimalist <kbd>kbd</kbd> component for Svelte apps.</p>
    <p in:fade={{duration:600, delay:600}}>
      Inspired by the elegant design of industry leaders and custom made mechanical keyboards.
    </p>
  </div>
  <div class="button-holder-wrap" in:fade={{duration:600, delay:800}}>
    <div class="button-holder">
      <button>
        npm install kbd-svelte
        <span>
          <svg xmlns="http://www.w3.org/2000/svg" width="16" height="16" viewBox="0 0 24 24" fill="none" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round"><rect x="9" y="9" width="13" height="13" rx="2" ry="2"></rect><path d="M5 15H4a2 2 0 0 1-2-2V4a2 2 0 0 1 2-2h9a2 2 0 0 1 2 2v1"></path></svg>
        </span>
      </button>
    </div>
  </div>
</div>

{/if}

<style lang="scss">

  @import "../../mixins";

  .info {
    display: flex;
    flex-direction: column;
    gap: var(--24px);
  }

  .logo {
    display: flex;
    height: var(--top-height);
    align-items: center;
    box-shadow: 0 1px 0 var(--bg-tertiary);
    // padding: 0 var(--16px);
    justify-content: space-between;

    a {
      opacity: 1;
      display: flex;
      font-size: var(--14px);
      color: var(--text-primary);
      align-items: center;
      gap: 4px;
      text-decoration: none;
      padding: 4px 8px;
      border-radius: var(--radius-base);
      transition: all 0.2s linear;

      &:hover {
        background: var(--bg-tertiary);
      }

      svg {
        path {
          fill: var(--text-primary);
        }
      }
    }
  }

  p {
    color: var(--text-secondary); 

    & + & {
      margin-top: var(--spacing-xxs);
    }
  }

  kbd {
    background: var(--color-white100);
    backdrop-filter: blur(10px);
    padding: 2px 8px;
    border-radius: 4px;
    box-shadow: 0 0 0 1px var(--bg-outline);
    color: var(--text-primary);
    font-family: var(--systemFont);
    font-size: var(--font-sm);
    text-shadow: 0 1px var(--color-outline);
    box-shadow:  inset 0 1px 0 var(--bg-tertiary), 0 0 0 1px var(--bg-outline);
    font-weight: 500;
  }

  button {
    // background: var(--bg-secondary);
    background: var(--bg-tertiary);
    // backdrop-filter: blur(10px);
    border: 0;
    border-radius: 30px;
    padding: 8px 8px 8px var(--20px);
    display: flex;
    align-items: center;
    gap: 8px;
    // cursor: copy;
    cursor: pointer;
    font-weight: 400;
    color: var(--text-primary);
    transition: all 0.2s linear;
    font-weight: 500;
    font-size: var(--font-sm);
    // box-shadow: inset 0 1px 0 0 var(--bg-tertiary);
    width: 100%;

    svg {
      transition: all 0.4s ease-in-out;
    }

    &:hover {
      span {
        opacity: 1;
        background: transparent;
        // box-shadow: 0 0 0 2px var(--bg-tertiary);
      }

      svg {
        stroke: var(--color-white);
        transform: translate3d(-2px, 0, 0);
      }
    }

    span {
      width: 28px;
      height: 28px;
      display: flex;
      align-items: center;
      justify-content: center;
      margin-left: auto;
      background: var(--color-white200);
      border-radius: 50%;
      transition: all 0.2s linear;
      opacity: 0.5;
    }

    svg {
      stroke: var(--color-white500);
    }
  }

  .text-holder {
    flex: 1;
  }

  .button-holder-wrap {
    display: flex;
    overflow: hidden;
    width: 100%;

  }

  .button-holder {
    display: flex;
    align-items: flex-start;
    position: relative;
    overflow: hidden;
    border-radius: 30px;
    width: 100%;
    // box-shadow: 0 0 0 1px var(--bg-outline);

    &:before {
      content: "";
      display: block;
      position: absolute;
      background: var(--bg-secondary);
      width: 60px;
      height: 120%;
      left: 0;
      top: -10%;
      opacity: 0.2;
      filter: blur(4px);
      transform: translate(-70px) skew(-15deg);
      z-index: 20;
      pointer-events: none;
    }

    &:hover {
      &:before {
        transform: translate(300px) skew(-15deg);
        transition: 0.7s;
      }
    }
  }

</style>

