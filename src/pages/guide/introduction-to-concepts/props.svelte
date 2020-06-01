<script>
  import Prism from "svelte-prism";
  import { meta } from "@sveltech/routify";
  meta.title = "Props";

  import Note from "@/components/Note.svelte";
  import Hr from "@/components/Hr.svelte";
  import RichText from "@/components/RichText.svelte";

</script>
<!-- routify:options index=40 -->

<h1 class="c-h1">Props</h1>

<RichText>

  <p>Props can be passed by using the <code>scoped</code> prop.</p>

  <Prism language="html">{`<slot scoped={{user: 'jimbo'}} />`}</Prism>

  <p>Props are available to all descendant layouts and pages.</p>

  <Prism>
      {`
          export let scoped
          $: {user} = scoped
      `}
  </Prism>

</RichText>
