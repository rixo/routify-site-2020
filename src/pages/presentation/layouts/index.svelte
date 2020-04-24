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
