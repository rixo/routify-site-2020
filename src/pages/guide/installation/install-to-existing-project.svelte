<script>
  import { url, meta } from "@sveltech/routify";
  import Prism from "svelte-prism";
  import { Tabs, TabsLink, TabsPage } from "@sveltech/bricks";

  import Note from "@/components/Note.svelte";
  import Hr from "@/components/Hr.svelte";
  import RichText from "@/components/RichText.svelte";

  meta.title = "Install to existing project";
</script>

<!-- routify:options index=20 -->

<h1 class="c-h1">Install to existing project</h1>

<RichText>
  <p>This is a guide to install Routify in an existing project.</p>
  <p>For example, you might have started your project using svelte-template and decide you need a router. Perhaps you don't want the features provided by Routify's starter template (code splitting, PWA-ready etc.) and want to keep things simpler.</p>
</RichText>

<h2 class="c-h2">Integrate into svelte-template</h2>

<RichText>
  <h3>1. Install module</h3>
  <p>Run in project folder</p>
</RichText>
<Prism>npm i -D @sveltech/routify</Prism>

<Hr />

<h3 class="c-h3">2. Update package.json</h3>

<Prism language="javascript">
  {`
    /** package.json **/
    ...
    "scripts": {
        "dev": "routify -c my-server",
        "my-server": "rollup -c -w",
        ...
    }
  `}
</Prism>

<p>
  <code>routify -c</code>
  is shorthand for
  <code>routify --childprocess</code>
  . If you do not wish to launch your server as a child process, you can use
  an npm task runner like
  <code>npm-run-all</code>
</p>

<Hr />

<h3 class="c-h3">3. Add router to your app</h3>

<Prism language="html">
  {`
    <!-- src/App.svelte -->
    <scrip`}{`t>
      import { Router } from "@sveltech/routify";
      import { routes } from "@sveltech/routify/tmp/routes";
    </script>

    <Router {routes} />
  `}
</Prism>

<Hr />

<h3 class="c-h3">4. Enable SPA</h3>

<p>
  If you're using history based navigation, make sure that your server
  redirects all requests to your app's path. Usually "/index.html" or just
  "/".
</p>

<Tabs>
  <div class="c-tabs">
    <TabsLink>Sirv</TabsLink>
    <TabsLink>Apache</TabsLink>
    <TabsLink>Other</TabsLink>
  </div>
  <div class="c-tabs-pages">
    <TabsPage>
      <p>For Sirv, enable the single option.</p>
      <Prism language="javascript">
        {`
          /** package.json **/
          ...
          "scripts": {
              "start": "sirv public --single"
              ...
          }
        `}
      </Prism>
    </TabsPage>
    <TabsPage>
      <Prism>
        {`
          RewriteEngine On
          RewriteBase /
          RewriteRule ^index\.html$ - [L]
          RewriteCond %{REQUEST_FILENAME} !-f
          RewriteCond %{REQUEST_FILENAME} !-d
          RewriteRule . /index.html [L]
        `}
      </Prism>
    </TabsPage>
    <TabsPage>
      <p>
        For other servers, consult the documentation on how to redirect all
        requests. This is also known as URL-rewrites.
      </p>
    </TabsPage>
  </div>
</Tabs>
