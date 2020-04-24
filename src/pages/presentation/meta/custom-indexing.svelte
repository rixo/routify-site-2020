<script>
  import Code from "@/components/Code.svelte";
</script>

<!-- routify:options index=25 -->

<div class="c-content">

  <h3>Custom indexing</h3>

  <strong>blog/announcing-1.5.svelte</strong>
  <Code language="svelte">
    {`
      <!-`}{`- routify:options blogpost={
        "published": "2020-04-20T11:45:06.574Z",
        "author": "jakobrosenberg",
        "title": "Announcing v1.5",
        "summary": \`Welcome to the brand-new Routify blog. This is not just the
          first post on Routify, but also my first ever blog post. Scary...\` -->
    `}
  </Code>

  <strong>blog/index.svelte</strong>
  <Code language="javascript">
    {`
      /** List and sort posts, without preloading the components */
      const posts = $layout.parent.children.filter(c => c.meta["blogpost"])
        .sort((a, b) => {
          const dateA = new Date (a.meta["blogpost"].published)
          const dateB = new Date (b.meta["blogpost"].published)
          return dateA - dateB });
  `}
  </Code>
</div>
