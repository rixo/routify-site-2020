<script>
  import Code from "@/components/Code.svelte";
  const structure = [
    [".", ""],
    ["├─ _layouts.svelte", "Top navigation"],
    ["└─ admin/", ""],
    ["   ├─ _layouts.svelte", "Left navigation"],
    ["   └─ index.svelte", "Inherits boths layouts"]
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

<!-- routify:options index=1 -->
<h1>Multi-level layouts</h1>

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
