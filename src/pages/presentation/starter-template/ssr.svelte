<script>
  import Prism from 'svelte-prism'
  import Note from "@/components/Note.svelte";
  import { ready, layout } from "@sveltech/routify";
  $: hash = $layout && location.hash;
  $: index = $layout.meta.children.map(c => c.path).indexOf(hash);

  $:  rdy = index < 0 ? "" : "$ready(); ";
  $:  comment = index < 0 ? "dehydrated" : "hydrated. \n    //If $ready is present, the file won't be redered till $ready() is called";
</script>

<!-- routify:options index=60 -->
<!-- routify:options children=[
  {path:"#with-ready",  title: "With $ready"},
] -->

<h3>SSR with or without synchronized data</h3>

<Prism source={`
  import { params, ready } from "@sveltech/routify";
  let data = {};
  getData();

  async function getData() {
    const res = await fetch("//jsonplaceholder.typicode.com/todos/1");
    data = await res.json();
    ${rdy}//${comment}
  }

`} />

