<script module>
  import type { Snippet } from 'svelte';

  type Props = {
    bgColor?: string;
    bgGradient?: string;
    bgImage?: string;
    bgSize?: string;
    bgPosition?: string;
    bgRepeat?: string;
    bgOpacity?: string;
    animate?: boolean;
    animateId?: string;
    animateRestart?: boolean;
    children?: Snippet<[]>;
  };
</script>

<script lang="ts">
  let {
    animate,
    animateId,
    animateRestart,
    bgColor,
    bgGradient,
    bgImage,
    bgSize,
    bgPosition,
    bgRepeat,
    bgOpacity,
    children
  }: Props = $props();
</script>

<section
  data-auto-animate={animate || null}
  data-auto-animate-id={animateId || null}
  data-auto-animate-restart={animateRestart || null}
  data-background-color={bgColor || null}
  data-background-gradient={bgGradient || null}
  data-background-image={bgImage || null}
  data-background-size={bgSize || null}
  data-background-position={bgPosition || null}
  data-background-repeat={bgRepeat || null}
  data-background-opacity={bgOpacity || null}
>
  {@render children?.()}
</section>
