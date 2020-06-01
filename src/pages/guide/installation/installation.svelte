<script>
  import { url, meta, metatags } from "@sveltech/routify";
  import Prism from "svelte-prism";

  import Hr from "@/components/Hr.svelte";
  import RichText from "@/components/RichText.svelte";

  import { Tabs, TabsLink, TabsPage } from "@sveltech/bricks";

  let title = "Creating an app"
  meta.title = title;
  metatags.description = title;

  import Note from "@/components/Note.svelte";
</script>

<!-- routify:options index=10 -->

<RichText>
  <h1 class="c-h1">{title}</h1>

  <p>To create your first Routify app, open an empty folder and type</p>

  <Prism>{`npx @sveltech/routify init`}</Prism>

  <p>
    This will install the
    <a href="https://github.com/sveltech/routify-starter">
      Routify starter template
    </a>
    .
  </p>
  
  <p>The starter template features the following - all are optional.</p>

  <ul>
    <li>Dynamic Imports</li>
    <li>Prerendering</li>
    <li>SSR</li>
    <li>Quick deployments</li>
  </ul>

  <Hr />

  <h3>Bundled examples</h3>

  <p>
    The Routify starter comes with an example folder (
    <code>src/pages/examples</code>
    ). You can experiment with these examples or just keep them as references.
  </p>

  <p>
    When you're ready to get started on your app, simply delete the contents
    of
    <code>src/pages/index.svelte</code>
    and add your own. You will still be able to access the examples on
    <code>http://localhost:5000/examples</code>
    .
  </p>

  <p>
    When you don't need the examples anymore you can simply delete the
    examples folder.
  </p>
</RichText>