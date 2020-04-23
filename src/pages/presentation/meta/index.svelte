<script>
  import Code from "@/components/Code.svelte";
</script>

<!-- routify:options index=10 -->

<div class="c-content">

  <h3>Access page and layout data without loading the components.</h3>

  <h5>Common usecases</h5>
  <strong>Individual file precaching/bundling</strong>
  <p>All nested files and folders will be bundled with this layout.</p>
  <Code language="svelte">
    {`
  <!-`}{`- routify:options bundle=true -->
`}
  </Code>

  <strong>File indexing</strong>
  <p>
    The index position of a page or layout. Useful when using programatic navigation.
  </p>
  <Code language="svelte">
    {`
  <!-`}{`- routify:options index=4 -->
`}
  </Code>

</div>
