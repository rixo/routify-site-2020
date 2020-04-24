<script>
  import Code from "@/components/Code.svelte";
  import Note from "@/components/Note.svelte";
</script>

<!-- routify:options index=20 -->
<Code language="none">
  {`
  $ npm run dev
    Serving spa on http://localhost:5000
    Serving ssr on http://localhost:5005
`}
</Code>

<Note>
  <p>
    You could use this server for production, but our instant deployments are
    easier.
  </p>
</Note>
