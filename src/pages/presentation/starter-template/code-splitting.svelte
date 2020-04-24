<script>
  import Code from "@/components/Code.svelte";
  import Note from "@/components/Note.svelte";

  const table = [
    [
      "Bundle this folder",
      "Bundles all nested files and folders in one file.",
      "<!" + "-- routify:options bundle=true -->"
    ],
    [
      "Preload this file or folder",
      "Preloads file or folder recursively.",
      "<!" + "-- routify:options preload=true -->"
    ]
  ];
</script>

<style>
  td {
    vertical-align: middle;
    padding-left: 12px;
    padding-right: 12px;
  }
</style>

<!-- routify:options index=30 -->

<h3>Fine grained control of dynamic imports</h3>
<table>
  {#each table as [name, text, code]}
    <tr>
      <td>
        <strong>{name}</strong>
        <p>{text}</p>
      </td>
      <td>
        <Code language="svelte">{code}</Code>
      </td>
    </tr>
  {/each}
</table>
