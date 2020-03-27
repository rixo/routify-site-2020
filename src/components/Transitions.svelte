<script>
  import { BaseTransition } from "@sveltech/routify/decorators";
  import { getConcestor } from '@sveltech/routify'
  import { scale, fly } from "svelte/transition";
  const configs = [
    {
      condition: meta => _getDirection(meta) > 0,
      transition: fly,
      inParams: { y: 400 },
      outParams: { y: -400 }
    },
    {
      condition: meta => _getDirection(meta) < 0,
      transition: fly,
      inParams: { y: -400 },
      outParams: { y: 400 }
    },
    {
      condition: () => true,
      transition: () => {}
    }
  ];

  function _getDirection(meta) {
    const { routes } = meta;
    const components = routes.map(r =>
      r.meta.$index === false && r.isIndex ? r.parent : r
    );
    const tabs = routes.map(r => r.path.split('/')[1])
    const [, cmp1, cmp2] = getConcestor(components[0], components[1])

    const direction = cmp1 && cmp2 && cmp1.meta.$index - cmp2.meta.$index

    return tabs[0] === tabs[1] && direction;
  }
</script>

<BaseTransition {configs}>
  <slot>
    <!-- optional fallback -->
  </slot>
</BaseTransition>
