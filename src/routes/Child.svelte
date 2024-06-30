<script lang="ts">
  import { type TransitionConfig } from 'svelte/transition';
  import type { Action } from 'svelte/action';
  type TransitionFunc = (node: HTMLElement, params: any) => TransitionConfig;
	let visible = true;

  export let transition: TransitionFunc | undefined = undefined;
  export let params: object = {};
  export let tag: string = 'div';
  export let role: string | undefined = undefined;
  export let options: object = {};
  export let divClass: string = '';
  export let node: HTMLElement | undefined = undefined;
  const noop = () => {};
  export let use: Action<HTMLElement, any> = noop;
</script>

<label>
	<input type="checkbox" bind:checked={visible} />
	visible
</label>

{#if visible && transition}
<svelte:element this={tag} transition:transition={params} use:use={options}  bind:this={node} {role} {...$$restProps} class={divClass} on:click on:mouseenter on:mouseleave on:focusin on:focusout>
  <slot />
</svelte:element>
{/if}

