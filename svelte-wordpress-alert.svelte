<script lang="ts">
    enum AlertTypes {
        success = "success",
        error = "error",
        warning = "warning",
        info = "info",
    }

    export let type: AlertTypes = AlertTypes.info;
    export let display_icon = false;
    export let dismissible = true;
</script>

<div class="notice notice-{type}" class:is-dismissible={dismissible}>
    {#if display_icon}
    <span class="dashicons dashicons-{type}"></span>
    {/if}
    <p><slot></slot></p>
</div>