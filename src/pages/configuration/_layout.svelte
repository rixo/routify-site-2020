<script>
    import SidebarNav from '../../components/SidebarNav.svelte';

    let items =
        [
            ['/configuration/basics', 'Basics'],
            ['/configuration/code-splitting', 'Code-splitting'],
            ['/configuration/prerendering', 'Prerendering'],
            ['/configuration/deployments', 'Deployments'],
            ['/configuration/ssr', 'SSR'],
            ['/configuration/cache', 'Cache']
        ]

</script>

<main class="c-sidebar-layout">
    <div class="c-sidebar-layout__side">
        <nav>
            <SidebarNav items />
        </nav>
    </div>
    <div class="c-sidebar-layout__main">
        <slot />
    </div>
</main>
