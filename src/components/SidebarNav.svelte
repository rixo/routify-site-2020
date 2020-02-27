<script>
    import { isActive, url } from '@sveltech/routify'

    export let items = [];

    $: items = items.map(([url, name]) => {
      return {
        name,
        url: $url(url),
        active: $isActive(url)
      }
    });
    
</script>

<ul class="c-sidebar-nav">
    {#each items as {name, url, active}}
        <li class:c-sidebar-nav__item--selected={active} class="c-sidebar-nav__item">
            <a href="{url}">{name}</a>
        </li>
    {/each}
</ul>

