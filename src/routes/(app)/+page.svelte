<script lang="ts">

  import { onMount } from 'svelte'
  import Container from "$lib/components/Container.svelte"
  import Controls from '$lib/components/Controls.svelte';
  import Kbd from '$lib/components/Kbd.svelte';

  let ready = false
  onMount(() => {
    ready = true
  })

  let currentKeys = ["⌘", "⇧", "k"]

  let kbd = [
    {
      title: "Linear", 
      keys: currentKeys,
      styles: [
        {style: "dark", color: "var(--bg-secondary)", checked: true},
        // {style: "", color: "#fff", checked: false},
      ],
      background: "", 
      fontsize: "",
      gap: ""
    },
    {
    title: "Arc", 
    keys: currentKeys,
    styles: [
      {style: "", color: "#EFC6CD", checked: true},
      {style: "light", color: "#fff", checked: false},
    ],
    background: "", 
    fontsize: "",
    gap: "5px" 
    },

    {
      title: "Linear", 
      keys: currentKeys,
      styles: [
        {style: "dark", color: "var(--bg-secondary)", checked: true},
        // {style: "", color: "#fff", checked: false},
      ],
      background: "", 
      fontsize: "",
      gap: ""
    },
    {
    title: "Arc", 
    keys: currentKeys,
    styles: [
      {style: "", color: "#EFC6CD", checked: true},
      {style: "light", color: "#fff", checked: false},
    ],
    background: "", 
    fontsize: "",
    gap: "5px" 
    },
    {
      title: "Scanner", 
      keys: currentKeys,
      styles: [
        {style: "dark", color: "var(--bg-secondary)", checked: true},
        // {style: "", color: "#fff", checked: false},
      ],
      background: "#222222", 
      fontsize: "",
      gap: ""
    },
    {
    title: "Arc", 
    keys: currentKeys,
    styles: [
      {style: "", color: "#EFC6CD", checked: true},
      {style: "light", color: "#fff", checked: false},
    ],
    background: "", 
    fontsize: "",
    gap: "5px" 
    },
    {
      title: "Linear", 
      keys: currentKeys,
      styles: [
        {style: "dark", color: "var(--bg-secondary)", checked: true},
        // {style: "", color: "#fff", checked: false},
      ],
      background: "", 
      fontsize: "",
      gap: ""
    },
    {
    title: "Arc", 
    keys: currentKeys,
    styles: [
      {style: "", color: "#EFC6CD", checked: true},
      {style: "light", color: "#fff", checked: false},
    ],
    background: "", 
    fontsize: "",
    gap: "5px" 
    },
    {
      title: "Linear", 
      keys: currentKeys,
      styles: [
        {style: "dark", color: "var(--bg-secondary)", checked: true},
        // {style: "", color: "#fff", checked: false},
      ],
      background: "", 
      fontsize: "",
      gap: ""
    },
    {
    title: "Arc", 
    keys: currentKeys,
    styles: [
      {style: "", color: "#EFC6CD", checked: true},
      {style: "light", color: "#fff", checked: false},
    ],
    background: "", 
    fontsize: "",
    gap: "5px" 
    },
    {
      title: "Linear", 
      keys: currentKeys,
      styles: [
        {style: "dark", color: "var(--bg-secondary)", checked: true},
        // {style: "", color: "#fff", checked: false},
      ],
      background: "", 
      fontsize: "",
      gap: ""
    },
    {
    title: "Arc", 
    keys: currentKeys,
    styles: [
      {style: "", color: "#EFC6CD", checked: true},
      {style: "light", color: "#fff", checked: false},
    ],
    background: "", 
    fontsize: "",
    gap: "5px" 
    },
    {
      title: "Linear", 
      keys: currentKeys,
      styles: [
        {style: "dark", color: "var(--bg-secondary)", checked: true},
        // {style: "", color: "#fff", checked: false},
      ],
      background: "", 
      fontsize: "",
      gap: ""
    },
    {
    title: "Arc", 
    keys: currentKeys,
    styles: [
      {style: "", color: "#EFC6CD", checked: true},
      {style: "light", color: "#fff", checked: false},
    ],
    background: "", 
    fontsize: "",
    gap: "5px" 
    },
    {
      title: "Linear", 
      keys: currentKeys,
      styles: [
        {style: "dark", color: "var(--bg-secondary)", checked: true},
        // {style: "", color: "#fff", checked: false},
      ],
      background: "", 
      fontsize: "",
      gap: ""
    },
    {
    title: "Arc", 
    keys: currentKeys,
    styles: [
      {style: "", color: "#EFC6CD", checked: true},
      {style: "light", color: "#fff", checked: false},
    ],
    background: "", 
    fontsize: "",
    gap: "5px" 
    },
    {
      title: "Linear", 
      keys: currentKeys,
      styles: [
        {style: "dark", color: "var(--bg-secondary)", checked: true},
        // {style: "", color: "#fff", checked: false},
      ],
      background: "", 
      fontsize: "",
      gap: ""
    },
    {
    title: "Arc", 
    keys: currentKeys,
    styles: [
      {style: "", color: "#EFC6CD", checked: true},
      {style: "light", color: "#fff", checked: false},
    ],
    background: "", 
    fontsize: "",
    gap: "5px" 
    },
    {
      title: "Linear", 
      keys: currentKeys,
      styles: [
        {style: "dark", color: "var(--bg-secondary)", checked: true},
        // {style: "", color: "#fff", checked: false},
      ],
      background: "", 
      fontsize: "",
      gap: ""
    },
    {
    title: "Arc", 
    keys: currentKeys,
    styles: [
      {style: "", color: "#EFC6CD", checked: true},
      {style: "light", color: "#fff", checked: false},
    ],
    background: "", 
    fontsize: "",
    gap: "5px" 
    },

  ]

</script>

<svelte:head><title>&lt;kbd&gt;</title></svelte:head>

{#if ready}
<Container sticky={true} --left="0" --top="0" --padding="var(--24px)">
  <Controls />
</Container>
<Container --padding="var(--24px)">
  <div class="key-holder">
    {#each kbd as item}
      <Kbd 
        title={item.title} 
        bind:keys={item.keys} 
        styles={item.styles}
        --background={item.background} 
        --fontsize={item.fontsize} 
        --gap={item.gap} 
      />
    {/each}
  </div>
</Container>
{/if}

<style lang="scss">

  .key-holder {
    position: relative;
    display: grid;
    grid-template-columns: repeat(6, 1fr);
    padding-bottom: 20vh;
    width: 100%;
    gap: var(--24px);
  }

</style>