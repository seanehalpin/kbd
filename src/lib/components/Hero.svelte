<script lang="ts">

  import { fade, fly, blur } from 'svelte/transition'
  import { onMount } from 'svelte'

</script>


<h1>Kbd.</h1>
<div class="info">
  <div class="text-holder">
    <p>Stylish, minimalist <kbd>kbd</kbd> component for Svelte apps.</p>
    <p>
      Inspired by the elegant design of industry leaders and custom made mechanical keyboards.
    </p>
  </div>
  <div class="button-holder-wrap">
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

  <style lang="scss">

    @import "../../mixins";
  
    h1 {
      text-transform: uppercase;
      margin-top: var(--spacing-xxl);
    }
  
    p {
      color: var(--text-secondary); 
  
      & + & {
        margin-top: var(--spacing-xxs);
      }
    }
  
    kbd {
      // border: 1px solid var(--color-light-200);
      background: var(--bg-secondary);
      padding: 2px 8px;
      border-radius: 4px;
      box-shadow: inset 0 1px 0 0 rgba(255,255,255,0.1), 0 0 0 2px rgba(0,0,0,0.1);
      // box-shadow: inset 0 0 0 1px var(--color-white), 0 3px 5px 0 rgba(0,0,0,0.1);
      color: var(--text-accent);
      font-family: var(--systemFont);
      font-size: var(--20px);
      text-shadow: 0 1px rgba(0,0,0,1);
      font-weight: 500;
    }
  
    button {
      background: var(--bg-secondary);
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
      transition: all 0.2s ease-in-out;
      font-weight: 500;
      font-size: var(--18px);
      box-shadow: inset 0 1px 0 0 rgba(255,255,255,0.1);
  
      &:hover {
        span {
          opacity: 1;
          background: var(--bg-primary);
          // box-shadow: 0 0 0 2px var(--bg-tertiary);
        }
      }
  
      span {
        width: 28px;
        height: 28px;
        display: flex;
        align-items: center;
        justify-content: center;
        margin-left: auto;
        background: var(--bg-tertiary);
        border-radius: 50%;
        transition: all 0.2s ease-in-out;
        opacity: 0.5;
      }
  
      svg {
        stroke: var(--text-tertiary);
      }
    }
  
    .info {
      margin-top: var(--spacing-xs);
      display: flex;
    }
  
    .text-holder {
      flex: 1;
      padding: 8px var(--42px) 0 0;
    }
  
    .button-holder {
      display: flex;
      align-items: flex-start;
      overflow: hidden;
      position: relative;
      overflow: hidden;
      border-radius: 30px;
      box-shadow: 0 0 0 2px rgba(0,0,0,0.1);
  
      &:before {
        content: "";
        display: block;
        position: absolute;
        background: var(--color-white500);
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