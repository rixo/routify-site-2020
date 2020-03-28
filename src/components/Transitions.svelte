<script>
  import { BaseTransition } from "@sveltech/routify/decorators"
  import { fade } from "svelte/transition";
  const duration = 100;
  const configs = [
    {
      condition: () => true,
      transition: fade,
      inParams: { duration },
      outParams: { duration }
    }
  ];
</script>

<BaseTransition {configs}>
  <slot>
    <!-- optional fallback -->
  </slot>
</BaseTransition>
