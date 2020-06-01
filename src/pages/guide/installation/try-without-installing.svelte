<script>

  import { url, meta } from "@sveltech/routify";
  import Prism from "svelte-prism";
  import { Tabs, TabsLink, TabsPage } from "@sveltech/bricks";
  import Hr from "@/components/Hr.svelte";
  import RichText from "@/components/RichText.svelte";

  meta.title = "Getting started";
  import Note from "@/components/Note.svelte";

</script>

<!-- routify:options index=1 -->


<h1 class="c-h1">Try without installing</h1>

<RichText>
  <p>
    You can give Routify a try without installing anything.
    The easiest way to do so is to visit our
    <a
      href="https://codesandbox.io/s/github/sveltech/routify-example-tvshow/tree/6-navigation">
      TV Shows app
    </a>
    on Codesandbox. If you feel like playing with the code, you just click the
    fork button.
  </p>
  <p>
    The TV Shows app has a few steps
    <a
      href="https://github.com/sveltech/routify-example-tvshow/branches/active">
      (branches)
    </a>
    - each of which can be imported, using Codesandbox's "Import from Github"
    feature. In fact, any Routify project can be imported to Codesandbox.
  </p>
</RichText>
