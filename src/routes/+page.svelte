<script> 
  import Parent from "./Parent.svelte";
  import { blur, fade, slide } from 'svelte/transition';
</script>

<Parent transition={fade} params={{ duration: 700 }}>
  Page content
</Parent>
