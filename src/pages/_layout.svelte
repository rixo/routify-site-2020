<script>
  import Header from "@/components/Header.svelte";
  import Footer from "@/components/Footer.svelte";
  import { meta, route } from "@sveltech/routify";
  import Transitions from "@/components/Transitions.svelte";
  meta.template("title", title => `${title ? ` ${title} - ` : ""}Routify`);

</script>

<div class="c-container-horizontal">
  <Header />
  <slot decorator={Transitions} />
  <Footer />
</div>
