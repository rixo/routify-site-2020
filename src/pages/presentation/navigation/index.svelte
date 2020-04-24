<script>
  import Code from "@/components/Code.svelte";
</script>

<!-- routify:options index=10 -->

<h1>Easy navigation with helpers</h1>
<Code language="svelte">
  {`
  <!-- relative -->
  <a href={$url('../../ingredients/sugar')}>Info about sugar</a>

  <!-- absolute -->
  <a href={$url('/ingredients/sugar')}>Info about sugar</a>

  <!-- named -->
  <a href={$url('sugar')}>Info about sugar</a>

  <!-- params -->
  <a href={$url('/users/:id', { id: '123' })}>Info author</a>
`}
</Code>
