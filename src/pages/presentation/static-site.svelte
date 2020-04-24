<script>
  import Code from "@/components/Code.svelte";
  import Note from "@/components/Note.svelte";
</script>

<!-- routify:options index=120 -->
<h1>Export a static site</h1>

<Code language="shell-session">
  {`
    $ npx routify export
  `}
</Code>

<Note>
  Static sites can be hydrated with a SPA and handle dynamic content with SSR.
</Note>
