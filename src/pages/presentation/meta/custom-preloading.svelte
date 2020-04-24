<script>
  import Code from "@/components/Code.svelte";
</script>

<!-- routify:options index=20 -->

<div class="c-content">

  <h3>Custom preloading</h3>

  <strong>blog/index.svelte</strong>
  <Code language="javascript">
    {`
      /** List and sort posts, without loading the components */
        import { routes } from "@sveltech/routify/tmp/routes";

        <!-- iterate all routes -->
        routes.forEach(route => {
          if(route.meta.preloadMe){ //custom metadata
            route.component(); //preload component
            route.layouts.forEach(layout => layout.component()) //preload layouts
          }
  `}
  </Code>
</div>
