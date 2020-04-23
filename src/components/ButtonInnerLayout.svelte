<script>
    import Icon from './Icon.svelte';

    // layouts: icon, label
    export let layout = "text";
    export let icon = null;
</script>

<!-- TODO Shouldn't we just check for an icon to use icon layout? -->
{#if layout == "icon"}
    <span class="c-button__icon-wrap">
      <Icon name={icon} size="20" />
    </span>
    <span class="u-hide-accessibility"><slot></slot></span>
{:else if layout == "icon-text"}
    <span class="c-button__icon-wrap">
      <Icon name={icon} size="20" />
    </span>
    <span class="c-button__label"><slot></slot></span>
{:else if layout == "text-icon"}
    <span class="c-button__label"><slot></slot></span>
    <span class="c-button__icon-wrap">
      <Icon name={icon} size="20" />
    </span>
{:else}
    <slot></slot>
{/if}
