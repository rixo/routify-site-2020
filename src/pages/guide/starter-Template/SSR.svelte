<script>
  import Code from "@/components/Code.svelte";
  import { ready } from "@sveltech/routify";

  import Note from "@/components/Note.svelte";  
  import Hr from "@/components/Hr.svelte";
  import RichText from "@/components/RichText.svelte";

</script>

<h1 class="c-h1">SSR</h1>

<RichText>
  <p>
    Our Starter template comes with SSR (Server Side Rendering) included. SSR
    renders your HTML on the server instead of sending an empty HTML template.
  </p>

  <h3>Benefits vs SPA only</h3>

  <ul>
    <li>
      First visit shows a rendered page without having to wait for javascript
      to load
    </li>
    <li>Better SEO - search engines can crawl your page</li>
    <li>
      External references to your site become rich objects when using Open
      Graph
    </li>
  </ul>


  <h3>Highlights</h3>
  <ul>
    <li>Serverless</li>
    <li>Optional and enabled by default</li>
    <li>No need to write separate SSR code</li>
    <li>Code isn't limited to a Node environment</li>
    <li>No tight coupling with arbitrary framework paradigms</li>
    <li>Painless async handling</li>
    <li>Easy build & deployments</li>
  </ul>


  <h3>Limitations</h3>
  <ul>
    <li>
      Requires a host with functions support (Now, Netlify, etc.) or a server
    </li>
    <li>
      Browser environment is headless, occasional consideration may be
      required
    </li>
  </ul>

</RichText>