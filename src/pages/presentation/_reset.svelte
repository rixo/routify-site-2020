<script>
  import Navigator from "./_navigator.svelte";
  import Code from "@/components/Code.svelte";
  import decorator from "./_decorator.svelte";
  import { layout } from "@sveltech/routify";

  const scoped = { Code };
</script>

<style>

  * :global(h1) {
    font-size: 4em;
  }
  * :global(h2) {
    font-size: 2.6em;
  }
  * :global(h3) {
    font-size: 1.8em;
  }
  * :global(h4) {
    font-size: 1.6em;
  }
  * :global(h5) {
    font-size: 1.3em;
  }
  * :global(h6) {
    font-size: 1em;
  }
  * :global(table tr td) {
    padding-left: 12px;
    padding-right: 12px;
  }
  * :global(table tr:last-of-type td) {
    padding-bottom: 12px;
  }


  main {
    position: fixed;
    left: 0;
    right: 0;
    top: 0;
    bottom: 0;
    font-size: 18px;
    /* font-family: "Overpass", sans-serif */
  }
  @media screen and (max-width: 600px) {}
  * :global(pre) {
    font-family: monospace;
    font-size: 18px;
    font-weight: bold;
    padding-left: 12px;
  }

  * :global(code){
    font-size: 1em;
  }

  * :global(.invert) {
    background: #4C5567;
    color: white
  }
  * :global(strong) {
    font-weight: bold
  }

</style>

<main>
  <!-- <div class="container-wrapper"> -->

  <slot {decorator} />

  <!-- </div> -->
</main>

<Navigator {scoped} />

<!-- routify:options transitionRoot=true -->
<!-- routify:options bundle=true -->
<!-- routify:options precache=false -->
