<script>
  import { url, isActive, route, layout, page } from "@sveltech/routify";
  import Icon from "@/components/Icon.svelte";
  import Button from "@/components/Button.svelte";
  let next, prev;

  $: if ($page) next = prev = false; //reset
  $: findSiblings($page); //update buttons on page change

  function findSiblings(node) {
    prev = prev || node.prev;
    next = next || node.next;
    // make sure we have a parent and that we're not travelling past our layout
    if (node.parent && node.parent !== $layout.parent) findSiblings(node.parent);
  }
</script>

<!-- routify:options index=10 -->

<slot />

<div class="c-pagination">
  {#if prev}
    <Button icon="chevron-left" layout="icon" href={$url(prev.path)}>
      Previous: {prev.title}
    </Button>
  {/if}

  {#if next}
    <Button icon="chevron-right" layout="text-icon" href={$url(next.path)}>
      Next: {next.title}
    </Button>
  {/if}
</div>
