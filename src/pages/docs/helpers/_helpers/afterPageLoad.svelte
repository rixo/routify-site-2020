<script>
  import FunctionDoc from "@/components/FunctionDoc.svelte";
  import Code from "@/components/Code.svelte";

  const params = [
    {
      type: "Function",
      name: "callback",
      description: "TBD"
    }
  ];
</script>

<FunctionDoc name="$afterPageLoad" {params}>
  <p>
    <code>$afterPageLoad</code>
    TBD
  </p>

  <Code language="svelte">
    {`
      <`}{`script>
        import { afterPageLoad } from "@sveltech/routify"
        $afterPageLoad ((page) => {
          console.log(page.title);
        })
      </script>
    `}
  </Code>

</FunctionDoc>
