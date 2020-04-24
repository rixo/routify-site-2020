<script>
  import { beforeUrlChange, url, route, layout } from "@sveltech/routify";
  $: hash = $layout && location.hash;
  $: index = $layout.meta.children.map(c => c.path).indexOf(hash);
</script>

<!-- routify:options index=10 -->
<!-- routify:options title="Complications" -->
<!-- routify:options children=[
  {path:"#a",  title: "Answer"},
  {path:"#b",  title: "Gee,  thanks"},
  {path:"#c",  title: "No :("},
  {path:"#d",  title: "No :("},
  {path:"#e",  title: "No :("},
  {path:"#f",  title: "No :("},
] -->

  <h3>
    I need to update
    <code>/get-started</code>
  </h3>
  {#if index >= 0}
    <h3>Where is my file?</h3>
  {/if}
  {#if index >= 1}
    <h3>Where you left it</h3>
  {/if}

  {#if index > 1}
    <h3>
      Dumped in root?
      <code>src/GetStarted.svelte</code>
    </h3>
  {/if}

  {#if index > 2}
    <h3>
      Using old name?
      <code>src/pages/Intro.svelte</code>
    </h3>
  {/if}

  {#if index > 3}
    <h3>
      Multiple routes in one file?
      <code>src/Guide.svelte</code>
    </h3>
  {/if}
  {#if index > 4}
    <h3>No, it's somewhere else :(</h3>
  {/if}
