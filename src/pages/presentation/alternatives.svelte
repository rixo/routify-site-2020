<script>
  import { url, layout } from "@sveltech/routify";
  const alternatives = [
    ["Sapper", "A great framework with data handling and built in file router."],
    ["Traditional routers", "If you prefer traditional conventions."],
    ["Roll your own", "Edge cases that can't be handled with existing routers."],
  ]
</script>

<!-- routify:options index=150 -->
<h1>What are the alternatives</h1>


{#each alternatives as [title, text]}
<h3>{title}</h3>
<h5>{text}</h5>
<br>
{/each}
