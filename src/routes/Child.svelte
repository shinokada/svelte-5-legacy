<script lang="ts">
  import { type TransitionConfig } from 'svelte/transition';
  type TransitionFunc = (node: HTMLElement, params: any) => TransitionConfig;
	let visible = true;

  export let transition: TransitionFunc | undefined = undefined;
  export let params: object = {};
  export let tag: string = 'div';
</script>

<label>
	<input type="checkbox" bind:checked={visible} />
	visible
</label>

{#if visible && transition}
<svelte:element this={tag} transition:transition={params} >
  <slot />
</svelte:element>
{/if}

