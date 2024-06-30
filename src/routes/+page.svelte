<script> 
  import Parent from "./Parent.svelte";
  import { blur, fade, slide } from 'svelte/transition';
</script>

<Parent transition={slide} params={{ duration: 700 }}>
  <h1>Page content</h1>
</Parent>
