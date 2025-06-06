<script lang="ts">
  import Code from './deck/code.svelte';
  import Slide from './deck/slide.svelte';
  import Slides from './deck/slides.svelte';
</script>

<Slides>
  <Slide>Horizontal Slide</Slide>

  <Slide>
    <Slide>Vertical Slide 1</Slide>
    <Slide>Vertical Slide 2</Slide>
  </Slide>

  <Slide animate animateId="list">
    <ul>
      <li>React</li>
      <li>Solid</li>
      <li data-id="svelte">Svelte</li>
      <li>Vue</li>
    </ul>
  </Slide>

  <Slide animate animateId="list">
    <ul>
      <li data-id="svelte">Svelte ❤️</li>
      <li>React</li>
      <li>Solid</li>
      <li>Vue</li>
    </ul>
  </Slide>

  <Slide>
    <Code language="ts" lineNumbers="1|8-10|18|">
      <script type="text/template">
        import type { MyClass } from './my-class';

        class LocalClass extends MyClass {
          constructor() {
            console.log('LocalClass initialized');
          }

          build(): string {
            return '<button onclick={handleClick}>Click me</button>';
          }
        }

        function app(): LocalClass {
          console.log('Hello, Svelte!');
          return new LocalClass();
        }

        export default app;
      </script>
    </Code>
  </Slide>
</Slides>
