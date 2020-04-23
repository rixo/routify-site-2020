<script>
  import Navigator from "./_navigator.svelte";
  import Code from "@/components/Code.svelte";
  import decorator from "./_decorator.svelte";
  import { layout } from "@sveltech/routify";

  const scoped = { Code };
</script>

<style>
  main {
    position: fixed;
    left: 0;
    right: 0;
    top: 0;
    bottom: 0;
  }
  .container-wrapper {
    position: absolute;
    width: 100%;
    height: 100%;
  }
  .container {
    position: absolute;
    left: 50%;
    top: 50%;
    transform: translate(-50%, -50%);
  }
  .father {
    display: flex;
    justify-content: center;
    align-items: center;
    width: 100%;
    height: 100%;
  }
</style>

<main>
  <!-- <div class="container-wrapper"> -->

      <slot {decorator} />

  <!-- </div> -->
</main>

<Navigator {scoped} />

<!-- routify:options transitionRoot=true -->
