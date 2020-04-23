<script>
  import { BaseTransition } from "@sveltech/routify/decorators";
  import { fly } from "svelte/transition";
  import { writable, get } from "svelte/store";
  export let rootParent;

  let width = writable(window.innerWidth);
  let height = writable(window.innerHeight);

  function isInRoot(pages) {
    return pages.find(page => page.parent.meta.transitionRoot);
  }

  const configs = [
    {
      // New and old route are identical, do nothing
      condition: ({ routes }) => routes[0] === routes[1],
      transition: () => {}
    },
    {
      condition: c => isInRoot(c.pages) && c.toHigherIndex,
      transition: fly,
      inParams: { y: $height, duration: 500 },
      outParams: { y: -$height, duration: 500 }
    },
    {
      condition: c => isInRoot(c.pages) && c.toLowerIndex,
      transition: fly,
      inParams: { y: -$height, duration: 500 },
      outParams: { y: $height, duration: 500 }
    },
    {
      condition: c => c.toHigherIndex,
      transition: fly,
      inParams: { x: $width, duration: 500 },
      outParams: { x: -$width, duration: 500 }
    },
    {
      condition: c => c.toLowerIndex,
      transition: fly,
      inParams: { x: -$width, duration: 500 },
      outParams: { x: $width, duration: 500 }
    },
    {
      // No matching config. We don't want a transition
      condition: () => true,
      transition: () => {}
    }
  ];
</script>

<style>
  div.outer {
    display: flex;
    justify-content: center;
    align-items: center;
    height: 100%;
  }
  div.inner {
    position: relative;
  }
</style>

<BaseTransition {configs}>
  <div class="outer">
    <div class="inner">
      <slot />
    </div>
  </div>
</BaseTransition>

<svelte:window bind:innerHeight={$height} bind:innerWidth={$width} />
