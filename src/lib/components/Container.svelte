<script lang="ts">
  
</script>

<section class="container">
  <div class="content">
    <slot />
  </div>
</section>

<style lang="scss">

  .container {
    display: flex;
    flex-direction: column;
    padding: 0 var(--16px);
    position: relative;
    z-index: var(--zindex-content);
  }

  .content {
    display: flex;
    max-width: var(--width);
    width: 100%;
    flex-direction: column;
    -webkit-box-orient: vertical;
    -webkit-box-direction: normal;
    flex-direction: column;
    -webkit-box-align: start;
    align-items: flex-start;
    align-self: center;
    flex: 1;
    margin: 0 auto;
  }

</style>