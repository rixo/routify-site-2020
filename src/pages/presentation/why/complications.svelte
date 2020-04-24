<script>
  import { beforeUrlChange, url, route, layout } from "@sveltech/routify";
  $: hash = $layout && location.hash;
  $: index = $layout.meta.children.map(c => c.path).indexOf(hash);
</script>

<!-- routify:options index=30 -->
<!-- routify:options children=[
  {path:"#a",  title: "Answer"},
  {path:"#b",  title: "Gee,  thanks"},
  {path:"#c",  title: "No :("},
  {path:"#d",  title: "No :("},
  {path:"#e",  title: "No :("},
] -->
<article class="c-content">
  <h1>Where is my file?</h1>
  {#if index >= 0}
    <h1>Where you left it</h1>
  {/if}

  {#if index > 0}
    <h3>
      Dumped in root?
      <code>src/GetStarted.svelte</code>
    </h3>
  {/if}

  {#if index > 1}
    <h3>
      Using old name?
      <code>src/pages/Intro.svelte</code>
    </h3>
  {/if}

  {#if index > 2}
    <h3>
      Inlined?
      <code>src/Guide.svelte</code>
    </h3>
  {/if}
  {#if index > 3}
    <h3>No, it's somewhere else :(</h3>
  {/if}
</article>
