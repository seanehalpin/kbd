<script lang="ts">
  
  // imports
  import { onMount } from 'svelte'
  import '../reset.scss'
  import '../app.scss'

  let ready:any
  // functions
  onMount(() => {
    ready = true 
  })

</script>

<slot />
