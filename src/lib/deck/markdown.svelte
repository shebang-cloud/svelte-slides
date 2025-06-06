<script module>
  import type { Snippet } from 'svelte';

  type Props = {
    name?: string;
    children?: Snippet<[]>;
  };
</script>

<script lang="ts">
  let { name, children }: Props = $props();
</script>

{#if name}
  <section data-markdown={name}></section>
{:else}
  <section data-markdown>
    <div data-template>
      {@render children?.()}
    </div>
  </section>
{/if}
