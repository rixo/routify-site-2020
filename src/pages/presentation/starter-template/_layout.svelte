<script>
  import { layout, isActive, url } from "@sveltech/routify";

  const features = [
    "SSR",
    "Code-splitting",
    "Prerendering",
    "SPA + SSR dev server",
    "Instant deployments"
  ];
</script>

<style>
  li {
    float: left;
    padding: 0 32px;
  }
  a {
    text-decoration: none;
    color: #4c5567;
  }
  a.active {
    border-bottom: #4c5567 3px solid;
  }
  main {
    padding-top: 96px;
    min-height: 70vh;
  }
</style>

<!-- routify:options index=140 -->
<div>
  <h1>Starter Template</h1>

  <ul>
    {#each $layout.children as node}
      <li>
        <a href={$url(node.path)} class:active={$isActive(node.path)}>
          {node.title}
        </a>
      </li>
    {/each}
  </ul>

  <main>

    <slot />

  </main>
</div>
