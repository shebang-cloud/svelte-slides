<script module>
  import { type Snippet } from 'svelte';

  type Props = {
    id?: string;
    language?: string;
    lineNumbers?: string | boolean;
    lineStartFrom?: number;
    trim?: boolean;
    html?: boolean;
    children?: Snippet<[]>;
  };
</script>

<script lang="ts">
  let {
    html = false,
    id,
    language,
    lineNumbers,
    lineStartFrom,
    trim = true,
    children
  }: Props = $props();
</script>

<pre data-id={id || null}><code
    class={language ? `language-${language}` : null}
    data-trim={trim || null}
    data-line-numbers={lineNumbers || null}
    data-ln-start-from={lineStartFrom || null}
    data-noescape={html ? null : true}>
    {@render children?.()}
  </code>
</pre>
