<script module>
  import { type Snippet } from 'svelte';
  export type Props = {
    controls?: boolean;
    progress?: boolean;
    scroll?: boolean;
    children: Snippet<[]>;
  };
</script>

<script lang="ts">
  import { onMount } from 'svelte';

  import Reveal from 'reveal.js';
  import Highlight from 'reveal.js/plugin/highlight/highlight';
  import Markdown from 'reveal.js/plugin/markdown/markdown';
  import Notes from 'reveal.js/plugin/notes/notes';

  import 'reveal.js/plugin/highlight/monokai.css';
  import 'reveal.js/dist/reveal.css';
  import 'reveal.js/dist/theme/black.css';

  let { controls = true, progress = false, scroll = false, children }: Props = $props();

  onMount(() => {
    const deck = new Reveal({
      plugins: [Markdown, Highlight, Notes],

      autoAnimateEasing: 'ease',
      autoAnimateDuration: 1,
      hash: true,

      controls: controls,
      controlsTutorial: false,

      progress: progress,
      scrollProgress: scroll,

      view: scroll ? 'scroll' : null
    });

    deck.initialize();
  });
</script>

<div class="reveal">
  <div class="slides">
    {@render children?.()}
  </div>
</div>
