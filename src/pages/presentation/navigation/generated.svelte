<script>
  import Code from "@/components/Code.svelte";
</script>

<!-- routify:options index=20 -->
<h1>Automatic links</h1>

<Code language="svelte">
  {`
      <!-- _layout.svelte -->
      <script>
        import { isActive, url, layout } from "@sveltech/routify";
      </script>

      <ul>
        <!-- iterate the layout's children -->
        {#each $layout.children as { path, title }}
          <li class:active={$isActive(path)}>
              <a href={$url(path)}>{title}</a>
          </li>
        {/each}
      </ul>
`}
</Code>
