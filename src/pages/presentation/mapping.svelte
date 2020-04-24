<script>
// @ts-check
  import Tree from "@/components/home/_HeroTree.svelte";
  import { url, page } from '@sveltech/routify'

</script>

<style>
  div {
    width: 600px;
  }
</style>

<!-- routify:options index=20 -->

<h1 class="c-h1">Easy mapping</h1>

<div>
  <Tree width="460" />
</div>
