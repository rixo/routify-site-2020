<script>
  import Code from "@/components/Code.svelte";
  const structure = [
    [".", ""],
    ["├─ _layouts.svelte", "Left navigation"],
    ["├─ index.svelte", ""],
    ["└─ [shop]/", ""],
    ["   ├─ _reset.svelte", "Top navigation."],
    ["   └─ index.svelte", "Only has top navigation"],

  ];
</script>

<style>
  pre {
    font-family: monospace;
    font-size: 18px;
    font-weight: bold;
    margin: 0 64px 0 12px;
  }
</style>

<!-- routify:options index=45 -->
<h1>Reset layouts and scope</h1>

<table>
  {#each structure as [path, text]}
    <tr>
      <td>
        <pre>{path}</pre>
      </td>
      <td>{text}</td>
    </tr>
  {/each}
</table>
