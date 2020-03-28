<script>
  import Header from "@/components/Header.svelte";
  import Footer from "@/components/Footer.svelte";
  import { meta, route } from "@sveltech/routify";
  import Transitions from "@/components/Transitions.svelte";
  meta.template("title", title => `${title ? ` ${title} - ` : ""}Routify`);
  let offsetHeight
  // $: console.log(offsetHeight);

</script>

<div class="c-container-horizontal">
  <Header bind:offsetHeight />
  <div style="position: relative; padding-top: 78px">
    <slot decorator={Transitions} />
  </div>
  <Footer />
</div>
