<script>
  import Prism from "svelte-prism";
  import Note from "@/components/Note.svelte";
  import { url } from "@sveltech/routify";

  import Hr from "@/components/Hr.svelte";
  import RichText from "@/components/RichText.svelte";

  const structure = [
    [".", ""],
    ["├─ src/", "Source. This is for all your handcrafted code."],
    ["│  └─ pages/", "Layouts and pages."],
    ["├─ static/", "Files that don't change. Images, CSS, etc."],
    ["│  └─ __index.html", "Entry file. Edit to your needs."],
    ["├─ dist/", "Distributables. This is where your built files are output."],
    ["└─ script/", "Scripts for deployments"]
  ];
</script>

<style>
  pre {
    font-family: monospace;
    font-size: 1.8rem;
    font-weight: bold;
    margin: 0 6.4rem 0 1.2rem;
  }
</style>

<!-- routify:options index=10 -->

<h1 class="c-h1">Overview</h1>

<h3 class="c-h3">Starter template structure</h3>

<table>
  {#each structure as [path, text]}
    <tr>
      <td>
        <pre style="font-family: monospace; margin-right: 2.4rem;">{path}</pre>
      </td>
      <td>{text}</td>
    </tr>
  {/each}
</table>

<Hr />

<h3 class="c-h3">Build and deploy</h3>
<Prism>
  {`
npm run build
npm run deploy:now
`}
</Prism>

<RichText>
  <p>
    This is a great way to get started, but in the long run a CI approach
    might be better suited and we recommend having a look at the
    <a href={$url('../deployment')}>deployment section.</a>
  </p>

  <p>
    To tweak your build or find out what's included, have a look at the
    <a href={$url('../build')}>Build section.</a>
  </p>
</RichText>