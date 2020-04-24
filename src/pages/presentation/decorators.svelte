<!-- routify:options index=110 -->
<script>
  import Code from "@/components/Code.svelte";

    const structure = [
    [" _layout", ""],
    ["  └─ Mydecorator", ""],
    ["     └─ _layout", ""],
    ["        └─ Mydecorator", ""],
    ["           └─ mypage", ""],

  ];
</script>

<h1>Decorators</h1>
Component wrapper for each descendant layout and page.

<Code language="svelte">
{`
<scri`}{`pt />
  import MyDecorator from './_MyDecorator.svelte'
</script>

<slot decorator={MyDecorator} />`}
</Code>


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
