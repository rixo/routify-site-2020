<script>
  import Code from "@/components/Code.svelte";
  import Note from "@/components/Note.svelte";
  import { layout } from "@sveltech/routify";
  $: hash = $layout && location.hash;
  $: index = $layout.meta.children.map(c => c.path).indexOf(hash);

</script>


<!-- routify:options index=40 -->
<!-- routify:options children=[
  {path:"#netlify",  title: "Deploy to Netlify"},
] -->

{#if index < 0}
<h3>Deploy in terminal</h3>
<Code>{`$ npm run deploy:now`}</Code>
{:else}
<h3>Deploy with GitHub repo on Netlify</h3>
<img src="/images/gifs/deploy-netlify.gif" alt="">
{/if}
