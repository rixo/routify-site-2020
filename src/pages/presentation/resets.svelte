<script>
  import Note from "@/components/Note.svelte";

  const structure = [
    [".", ""],
    ["├─ _layouts.svelte", "Left navigation"],
    ["├─ index.svelte", ""],
    ["└─ [shop]/", ""],
    ["   ├─ _reset.svelte", "Top navigation."],
    ["   └─ index.svelte", "Only has top navigation"]
  ];
</script>

<style>
  tr:last-of-type td {
    padding: 0 12px 12px 0
  }
</style>

<!-- routify:options index=45 -->
<h1>Reset layouts and scope</h1>
<h5>Get rid of inherited layouts and props. Apps in apps, Inception style.</h5>
<table class="invert">
  {#each structure as [path, text]}
    <tr>
      <td>
        <pre>{path}</pre>
      </td>
      <td>{text}</td>
    </tr>
  {/each}
</table>

<Note>
  <p>This presentation is in a reset on our website</p>
</Note>
