<script>
  import { url, isActive, layout, page, goto } from "@sveltech/routify";
  import Icon from "@/components/Icon.svelte";
  import Button from "@/components/Button.svelte";

  let next, prev;
  function findNextPrev(node, traversing) {
    //reset
    if (!traversing) next = prev = false;

    // anchors
    if (!traversing && node.children.length) {
      console.log("hello");
      const currentHash = location.hash;
      const currentIndex = node.children.map(c => c.path).indexOf(currentHash);
      next = node.children[currentIndex + 1];

      if (currentIndex === 0) prev = node;
      else prev = node.children[currentIndex-1]
    }

    // links
    if (node !== $layout.parent) {
      prev = prev || node.prev;
      next = next || node.next;
      if (node.parent) findNextPrev(node.parent, true);
    }
  }
  $: findNextPrev($page);

  function handleKeydown({ key }) {
    if (key === "ArrowRight" && next) $goto(next.path);
    if (key === "ArrowLeft" && prev) $goto(prev.path);
  }
</script>

<style>
  section.menu {
    position: absolute;
    bottom: 50px;
  }
  nav {
    visibility: hidden;
  }
  section:hover nav {
    visibility: visible;
    background: rgba(255, 255, 255, 0.8);
  }
  a {
    display: block;
  }
  .child {
    padding-left: 3rem;
  }
  .actions {
    position: absolute;
    bottom: 0;
    width: 100%;
  }
  a.active {
    background: black;
  }
</style>

<section class="menu">
  <nav>
    <a href={$url('./')}>Home</a>
    {#each $layout.children as child}
      <a href={$url(child.path)} class:active={$isActive(child.path)}>
        {child.meta.index || 'NA'} - {child.title}
      </a>
      {#each child.children as child}
        <a
          class="child"
          href={$url(child.path)}
          class:active={$isActive(child.path)}>
          {child.meta.index || 'NA'} - {child.title}
        </a>
      {/each}
    {/each}
  </nav>
</section>

<section class="actions">
  <div class="c-pagination">
    <!-- @todo we should change these to use the Button component, but I had a problem doing that -Wolfr -->
    {#if prev}
      <Button icon="chevron-left" layout="icon" href={$url(prev.path)}>
        Previous: {prev.title}
      </Button>
    {:else}
      <div />
    {/if}

    {#if next}
      <Button icon="chevron-right" layout="text-icon" href={$url(next.path)}>
        Next: {next.title}
      </Button>
    {/if}
  </div>
</section>

<svelte:window on:keydown={handleKeydown} />
