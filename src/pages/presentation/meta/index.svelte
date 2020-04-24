<script>
  import Code from "@/components/Code.svelte";
</script>

<style>
  td {
    vertical-align: middle;
    padding-left: 12px;
    padding-right: 12px;
  }

</style>

<!-- routify:options index=10 -->
<h3>Access page and layout data without loading the components.</h3>

<h5>Common usecases</h5>

<table>
  <tr>
    <td>
      <strong>Precaching/bundling of individual fils</strong>
      <p>All nested files and folders will be bundled with the layout.</p>
    </td>
    <td>
      <Code language="svelte">
        {`
  <!-`}{`- routify:options bundle=true -->
`}
      </Code>
    </td>
  </tr>
  <tr>
    <td>
      <strong>File indexing</strong>
      <p>Useful for programatic navigation and links ordering.</p>
    </td>
    <td>
      <Code language="svelte">
        {`
  <!-`}{`- routify:options index=4 -->
`}
      </Code>
    </td>
  </tr>
  <tr>
    <td>
      <strong>Route naming</strong>
      <p>Create a page that you can route to by name.</p>
    </td>
    <td>
      <Code language="svelte">
        {`
  <!-`}{`- routify:options name="get-started" -->
`}
      </Code>
    </td>
  </tr>
</table>
