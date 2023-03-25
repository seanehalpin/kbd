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
        {style: "dark", color: "var(--bg-secondary)", checked: true, background: ""},
        // {style: "", color: "#fff", checked: false},
      ],
      fontsize: "",
      gap: ""
    },
    {
    title: "Arc", 
    keys: currentKeys,
    styles: [
      {style: "", color: "#EFC6CD", checked: true, background: ""},
      {style: "light", color: "#fff", checked: false, background: ""},
    ],
    fontsize: "",
    gap: "5px" 
    },
    {
      title: "Scanner", 
      keys: currentKeys,
      styles: [
        {style: "dark", color: "var(--bg-secondary)", checked: true, background: "#222"},
        // {style: "", color: "#fff", checked: false},
      ],
      fontsize: "",
      gap: ""
    },


    {
      title: "Linear", 
      keys: currentKeys,
      styles: [
        {style: "dark", color: "var(--bg-secondary)", checked: true, background: ""},
        // {style: "", color: "#fff", checked: false},
      ],
      fontsize: "",
      gap: ""
    },
    {
    title: "Arc", 
    keys: currentKeys,
    styles: [
      {style: "", color: "#EFC6CD", checked: true, background: ""},
      {style: "light", color: "#fff", checked: false, background: ""},
    ],
    fontsize: "",
    gap: "5px" 
    },
    {
      title: "Scanner", 
      keys: currentKeys,
      styles: [
        {style: "dark", color: "var(--bg-secondary)", checked: true, background: "#222"},
        // {style: "", color: "#fff", checked: false},
      ],
      fontsize: "",
      gap: ""
    },

    {
      title: "Linear", 
      keys: currentKeys,
      styles: [
        {style: "dark", color: "var(--bg-secondary)", checked: true, background: ""},
        // {style: "", color: "#fff", checked: false},
      ],
      fontsize: "",
      gap: ""
    },
    {
    title: "Arc", 
    keys: currentKeys,
    styles: [
      {style: "", color: "#EFC6CD", checked: true, background: ""},
      {style: "light", color: "#fff", checked: false, background: ""},
    ],
    fontsize: "",
    gap: "5px" 
    },
    {
      title: "Scanner", 
      keys: currentKeys,
      styles: [
        {style: "dark", color: "var(--bg-secondary)", checked: true, background: "#222"},
        // {style: "", color: "#fff", checked: false},
      ],
      fontsize: "",
      gap: ""
    },

    {
      title: "Linear", 
      keys: currentKeys,
      styles: [
        {style: "dark", color: "var(--bg-secondary)", checked: true, background: ""},
        // {style: "", color: "#fff", checked: false},
      ],
      fontsize: "",
      gap: ""
    },
    {
    title: "Arc", 
    keys: currentKeys,
    styles: [
      {style: "", color: "#EFC6CD", checked: true, background: ""},
      {style: "light", color: "#fff", checked: false, background: ""},
    ],
    fontsize: "",
    gap: "5px" 
    },
    {
      title: "Scanner", 
      keys: currentKeys,
      styles: [
        {style: "dark", color: "var(--bg-secondary)", checked: true, background: "#222"},
        // {style: "", color: "#fff", checked: false},
      ],
      fontsize: "",
      gap: ""
    },

    {
      title: "Linear", 
      keys: currentKeys,
      styles: [
        {style: "dark", color: "var(--bg-secondary)", checked: true, background: ""},
        // {style: "", color: "#fff", checked: false},
      ],
      fontsize: "",
      gap: ""
    },
    {
    title: "Arc", 
    keys: currentKeys,
    styles: [
      {style: "", color: "#EFC6CD", checked: true, background: ""},
      {style: "light", color: "#fff", checked: false, background: ""},
    ],
    fontsize: "",
    gap: "5px" 
    },
    {
      title: "Scanner", 
      keys: currentKeys,
      styles: [
        {style: "dark", color: "var(--bg-secondary)", checked: true, background: "#222"},
        // {style: "", color: "#fff", checked: false},
      ],
      fontsize: "",
      gap: ""
    },

    {
      title: "Linear", 
      keys: currentKeys,
      styles: [
        {style: "dark", color: "var(--bg-secondary)", checked: true, background: ""},
        // {style: "", color: "#fff", checked: false},
      ],
      fontsize: "",
      gap: ""
    },
    {
    title: "Arc", 
    keys: currentKeys,
    styles: [
      {style: "", color: "#EFC6CD", checked: true, background: ""},
      {style: "light", color: "#fff", checked: false, background: ""},
    ],
    fontsize: "",
    gap: "5px" 
    },
    {
      title: "Scanner", 
      keys: currentKeys,
      styles: [
        {style: "dark", color: "var(--bg-secondary)", checked: true, background: "#222"},
        // {style: "", color: "#fff", checked: false},
      ],
      fontsize: "",
      gap: ""
    },

    {
      title: "Linear", 
      keys: currentKeys,
      styles: [
        {style: "dark", color: "var(--bg-secondary)", checked: true, background: ""},
        // {style: "", color: "#fff", checked: false},
      ],
      fontsize: "",
      gap: ""
    },
    {
    title: "Arc", 
    keys: currentKeys,
    styles: [
      {style: "", color: "#EFC6CD", checked: true, background: ""},
      {style: "light", color: "#fff", checked: false, background: ""},
    ],
    fontsize: "",
    gap: "5px" 
    },
    {
      title: "Scanner", 
      keys: currentKeys,
      styles: [
        {style: "dark", color: "var(--bg-secondary)", checked: true, background: "#222"},
        // {style: "", color: "#fff", checked: false},
      ],
      fontsize: "",
      gap: ""
    },

    {
      title: "Linear", 
      keys: currentKeys,
      styles: [
        {style: "dark", color: "var(--bg-secondary)", checked: true, background: ""},
        // {style: "", color: "#fff", checked: false},
      ],
      fontsize: "",
      gap: ""
    },
    {
    title: "Arc", 
    keys: currentKeys,
    styles: [
      {style: "", color: "#EFC6CD", checked: true, background: ""},
      {style: "light", color: "#fff", checked: false, background: ""},
    ],
    fontsize: "",
    gap: "5px" 
    },
    {
      title: "Scanner", 
      keys: currentKeys,
      styles: [
        {style: "dark", color: "var(--bg-secondary)", checked: true, background: "#222"},
        // {style: "", color: "#fff", checked: false},
      ],
      fontsize: "",
      gap: ""
    },
    

  ]

</script>

<svelte:head><title>&lt;kbd&gt;</title></svelte:head>

{#if ready}
<!-- <Container sticky={true} --left="0" --top="0">
  <Controls />
</Container> -->
<Container>
  <div class="key-holder">
    {#each kbd as item}
      <Kbd 
        title={item.title} 
        bind:keys={item.keys} 
        styles={item.styles}
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
    // grid-template-columns: repeat(6, 1fr);
    grid-template-columns: repeat(auto-fill, minmax(350px, 1fr));
    padding: var(--24px) var(--24px) 10vh;
    // padding-bottom: 10vh;
    width: 100%;
    gap: var(--24px);
  }

</style>