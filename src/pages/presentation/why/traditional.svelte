<script>
  import { beforeUrlChange, url, route, layout } from "@sveltech/routify";
  $: hash = $layout && location.hash;
  $: index = $layout.meta.children.map(c => c.path).indexOf(hash);

  $: confPath = index > -1 ? "/get-started" : "";
  $: othersPath = index > 0 ? "/get-started" : "";
</script>

<style>
  .broken {
    visibility: hidden;
    transform: rotate(5deg) translateY(20px);
    /* text-decoration: line-through; */
  }
  .broken.show {
    visibility: visible;
  }

  .fresh :not(.broken) code {
    color: #53ce2f;
    background: #f7fff6;
  }
</style>

<!-- routify:options index=20 -->
<!-- routify:options children=[
  {path:"#change-a-path",  title: "Let's Change a path"},
  {path:"#update-dependents",  title: "Update dependencies"},
  {path:"#now-what",  title: "Now What"},
] -->
<article class="c-content">
  <h2>Interdependencies</h2>
  <h3>of a traditional router</h3>
  <ul class="fresh">
    <li>
      One or multiple configurations
      <code>{confPath}</code>
    </li>
    <li>Filesystem</li>
    <li>
      Navigation
      <code>{othersPath}</code>
    </li>
    <li>
      Mobile navigation
      <code>{othersPath}</code>
    </li>
    <li>
      Sitemap
      <code>{othersPath}</code>
    </li>
    <li class="broken" class:show={index > 1}>
      Cross links
      <code>/guide/getting-started</code>
    </li>
  </ul>

</article>
