<script>
  import { meta } from "@sveltech/routify";
  meta.title = "Deployments";
  import Prism from "svelte-prism";
  
  import Note from "@/components/Note.svelte";
  import Hr from "@/components/Hr.svelte";
  import RichText from "@/components/RichText.svelte";
  
</script>

<RichText>

  <h2>Apache server</h2>

  <p>Deploy the contents of the <code>dist</code> folder. We've had success with the following <code>.htaccess</code> configuration:</p>
  
  <script>
    import Prism from "svelte-prism";
  </script>

  <Prism>{`
    RewriteEngine On

    RewriteCond %{REQUEST_FILENAME}.html -f
    RewriteRule !.*\.html$ %{REQUEST_FILENAME}.html [L]

    RewriteCond %{REQUEST_FILENAME} !-f
    RewriteRule . __app.html

    <Files "*.js">
        ForceType text/javascript
    </Files>
    `}</Prism>

</RichText>