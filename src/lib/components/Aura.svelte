<script lang="ts">

  import { onMount } from 'svelte'
  import { fade, fly } from 'svelte/transition'

  let canvas:any, ctx:any
  let width = 32
  let height = 32
  $: show = true

  
  const draw = () => {
    canvas = document.getElementById("canvas") as HTMLCanvasElement
    ctx = canvas.getContext("2d")
    let time = 0
    
    const color = function (x, y, r, g, b) {
      ctx.fillStyle = `rgb(${r}, ${g}, ${b})`
      ctx.fillRect(x, y, 5, 5);
    }

    const R = function (x, y, time) {
      return (Math.floor(200 + 64 * Math.cos((x * x - y * y) / 300 + time)))
    }

    const G = function (x, y, time) {
      return (Math.floor(10 + 64 * Math.sin((x * x * Math.cos(time / 4) + y * y * Math.sin(time / 3)) / 300)))
    }

    const B = function (x, y, time) {
      return (Math.floor(250 + 64 * Math.sin(5 * Math.sin(time / 9) + ((x - 100) * (x - 100) + (y - 100) * (y - 100)) / 1100)))
    }

    const startAnimation = function () {
      let x,y
      for (x = 0; x <= 30; x++) {
        for (y = 0; y <= 30; y++) {
          color(x, y, R(x, y, time), G(x, y, time), B(x, y, time))
        }
      }
      time = time + 0.015;
      // time = time + 0.025
      // time = time + 0.04
      window.requestAnimationFrame(startAnimation)
    }
    startAnimation()
  }

  function init(el: HTMLCanvasElement) {
    draw()
  }

  let ready = false
  onMount(() => {
    ready = true
  })


</script>

{#if show}
  {#if ready}
  <div class="canvas" in:fade={{duration: 1200, delay:200}}>
    <div class="mask"></div>
    <div class="canvas-holder">
      <canvas id="canvas" width={width} height={height} use:init></canvas>
    </div>
  </div>
  {/if}
{/if}

<style lang="scss">

  @import '../../mixins';

  canvas {
    width: 100%;
    height: 100%;
    position: absolute;
    left: 0;
    top: 0;
    z-index: 1;
  }

  .canvas-holder {
    width: 100%;
    height: 100%;
    position: absolute;
    left: 0;
    top: 0;
    z-index: 1;
    overflow: hidden;

    &::before {
      content: "";
      position: absolute;
      z-index: 10;
      left: 0;
      top: 0;
      width: 100%;
      height: 100%;
      opacity: 0.1;
      // background: url("/grid.svg") center center;
      filter: saturate(2);
      // filter: invert(1);
    }
  }

  .canvas {
    width: 100vw;
    height: 600px;
    // height: 50vh;
    position: absolute;
    z-index: 1;
    left: 0;
    right: 0;
    bottom: 0;
    top: 0;
    overflow: hidden;
    display: none;
    // opacity: 0.2;
    opacity: 0.7;
    filter: saturate(1);
    pointer-events: none;

    @include md {
      display: block;
    }

    .mask {
      position: absolute;
      z-index: var(--zindex-2);
      background: var(--color-gradient-dark);
      left: 0;
      top: 0;
      width: 100%;
      height: 100%;
    }
  }

</style>