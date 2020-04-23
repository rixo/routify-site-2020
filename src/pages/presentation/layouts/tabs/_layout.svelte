<script>
  import { url, isActive, layout } from "@sveltech/routify";
</script>

<style>
  a {
    padding: 0 12px;
    text-transform: uppercase;
    font-weight: bold;
    font-size: 5rem;
    text-decoration: none;
  }
  a.active {
    background: gray;
    color: white;
  }
  * :global(main) {
    font-size: 10rem
  }
</style>

<!-- routify:options index=40 -->
<section>
  <div>
    {#each $layout.children as node}
      <a href={$url(node.path)} class:active={$isActive(node.path)}>
        {node.title}
      </a>
    {/each}
  </div>
  <main>
    <slot />
  </main>
</section>
