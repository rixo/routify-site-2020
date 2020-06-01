<script>
  import { meta } from '@sveltech/routify'
  meta.title = 'Structure'

  import Note from "@/components/Note.svelte";
  import Hr from "@/components/Hr.svelte";
  import RichText from "@/components/RichText.svelte";

</script>
  
<!-- routify:options index=20 -->

<h1 class="c-h1">File structure</h1>

<RichText>
  <p>Routify is a file based router. To create a new route, create a new file.</p>

  <p>Files and folders correspond to URLs.</p>

  <ul>
    <li><code>about.svelte</code> corresponds to <code>/about</code></li>
    <li>
      <code>recipes/cupcakes.svelte</code> corresponds to <code>/recipes/cupcakes</code>.
      In this example, recipes is a folder.
    </li>
    <li><code>recipes/index.svelte</code> corresponds to <code>/recipes</code> (and <code>/recipes/index</code>)</li>
  </ul>

  <h3>Parameters</h3>

  <p><code>src/pages/admin/[business].svelte</code> corresponds to <code>/admin/:business</code>, where :business is a parameter.</p>

  <h3>Excluding files</h3>

  <p>Files and folders prefixed with underscore will <strong>not</strong> be picked up by Routify. (except for <code>_layout.svelte</code> and <code>_reset.svelte</code>)</p>

  <h3>Layouts and resets</h3>

  <p>Layout files are named <code>_layout.svelte</code> and apply to all adjacent and nested Svelte files. A file can have multiple layouts if multiple layouts are recursively present in parent folders.</p>

  <p>Reset files are named <code>_reset.svelte</code>. They function like layout files, but do not inherit the parent scope (layouts, props, etc.).</p>

  <h3>404 and fallbacks</h3>

  <p>404s can be caught with <code>_fallback.svelte</code>. The first <code>_fallback.svelte</code> that's found while traversing back through parent folders will be used.</p>

  <p>Fallback inherits layout.</p>

</RichText>
