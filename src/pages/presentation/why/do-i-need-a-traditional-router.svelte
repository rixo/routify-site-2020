<script>
  import { beforeUrlChange, url, route, layout } from "@sveltech/routify";
  $: hash = $layout && location.hash;
  $: index = $layout.meta.children.map(c => c.path).indexOf(hash);

</script>

<style>

</style>

<!-- routify:options index=40 -->
<!-- routify:options children=[
  {path:"#no",  title: "Do I?"},
] -->
<article class="c-content" style="height: 400px">
  <h1>Do I need a traditional router?</h1>
  {#if index > -1}
    <h3>Not if you have to ask</h3>
  {/if}
</article>
