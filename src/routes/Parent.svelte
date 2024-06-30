<script>
  import Child from "./Child.svelte";
</script>

<div>
<Child  {...$$restProps}>
  <slot />
</Child>
</div>