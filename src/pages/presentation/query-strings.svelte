<script>
  import Code from "@/components/Code.svelte";
  import Prism from "svelte-prism";
  import { beforeUrlChange, url, route, layout } from "@sveltech/routify";
  $: hash = $layout && location.hash;
  $: index = $layout.meta.children.map(c => c.path).indexOf(hash);

  const params = {
    "-1": "{id: 123}",
    "0": "{id: 123, theme: 'dark'}",
    "1": "{id: 123, theme: 'dark', lang: 'de'}",
    "2": "{id: 123, theme: 'dark', lang: 'de'}"
  };
  const paths = {
    "-1": "blog/123",
    "0": "blog/123?theme=dark",
    "1": "blog/123?theme=dark&lang=de",
    "2": "blog/123?theme=dark&lang=de"
  };
</script>

<!-- routify:options index=90 -->
<!-- routify:options children=[
  {path:"#overload",  title: "Overload"},
  {path:"#overload-again",  title: "Overload again"},
  {path:"#show-params",  title: "Show params"},
] -->

<style>
  .parse {visibility: hidden;}
  .parse.show {visibility: visible;}
</style>

<h1>Query strings</h1>
<Prism language="javascript" source="$url('/blog/:id', {params[index]})" />
<strong>{paths[index]}</strong>

<div class="parse" class:show={index >= 2}>
  <Code language="javascript">
    {`
    console.log($params)
    // ${params[index]}`}
  </Code>
</div>
