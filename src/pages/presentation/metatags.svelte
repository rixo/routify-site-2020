<script>
  import Code from "@/components/Code.svelte";
  import Prism from "svelte-prism";
</script>

<!-- routify:options index=100 -->

<h1>Metatags and Open Graph</h1>

<Code language="javascript">
  {`
// import metatags
import { metatags} from "@sveltech/routify";

// set a metatag
$: metatags.title = "My app - home";
`}
</Code>
will output the following:
<Code language="html">
  {`
  <title>My app - home</title>
  <meta name="title" content="My app - home" data-origin="routify" />
  <meta property="og:title" content="My app - home" data-origin="routify" />
`}
</Code>

  That is all there is to it.
