<script>
  import Prism from "svelte-prism";

  import Note from "@/components/Note.svelte";
  import Hr from "@/components/Hr.svelte";
  import RichText from "@/components/RichText.svelte";

</script>

<!-- routify:options index=30 -->
<h1 class="c-h1">Build</h1>

<h3 class="c-h3">What's in the default build?</h3>

<RichText>
  <ul>
    <li>
      <strong>Dynamic Imports</strong>
      <p>
        This breaks up the app into fragments which are then loaded
        dynamically when required.
      </p>
    </li>
    <li>
      <strong>Prerenders</strong>
      <p>
        Prerenders are static pages which have been rendered to HTML in
        advance. This ensures that the rendered page is sent to the browser
        and visible while the actual app is loading in the background.
      </p>
    </li>
    <li>
      <strong>SSR (Server side rendering)</strong>
      <p>
        SSR works like prerendering, except it's performed in realtime. Both
        SSR and prerending are important for SEO, Opengraph and other areas
        where only the prerendered content matters.
      </p>
    </li>
  </ul>
</RichText>

<h3 class="c-h3">How to build</h3>

<RichText>
  <p>To build your app for production</p>
</RichText>

<Prism>npm run build</Prism>

<RichText>
  <p>
    <strong>Dynamic imports</strong>
    and
    <strong>prerenders</strong>
    are enabled by default, but can be disabled in
    <code>package.json</code>
  </p>
</RichText>

<Note>
  <h3 class="c-h5">If you're rolling your own</h3>
  <p>
    You can build the routes for your app by running
    <code>npx routify --single-build</code>
  </p>
  <p>
    Dynamic imports can be added with
    <code>--dynamic-imports</code>
  </p>
</Note>
