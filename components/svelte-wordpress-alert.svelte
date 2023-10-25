<script lang="ts">
    export let type: "success" | "error" | "warning" | "info" = "info";
    export let display_icon = false;
    export let dismissible = true;
    export let icon = "";

    function set_icon() {
        if (!display_icon) return;
        switch (type) {
            case "success":
                icon = "yes";
                break;
            case "error":
                icon = "no-alt";
                break;
            case "warning":
                icon = "warning";
                break;
            case "info":
                icon = "info";
                break;
        }
    }

    $: set_icon();
</script>

<div class="notice notice-{type} {$$restProps.class || ''}" class:is-dismissible={dismissible}>
    <p>
        {#if display_icon}
            <span class="dashicons dashicons-{icon}"></span>
        {/if}
        <slot></slot>
    </p>
</div>

<style>
    .notice {
        padding: 1em;
        margin: 1em 0;
        border-left: 4px solid;
    }

    .notice p {
        margin: 0;
    }

    .notice.notice-success {
        border-color: #46b450;
        background-color: #e6ffe6;
    }

    .notice.notice-error {
        border-color: #dc3232;
        background-color: #ffe6e6;
    }

    .notice.notice-warning {
        border-color: #ffb900;
        background-color: #fff7e6;
    }

    .notice.notice-info {
        border-color: #00a0d2;
        background-color: #e6f7ff;
    }

    .notice.is-dismissible {
        padding-right: 3em;
    }

    .notice.is-dismissible .notice-dismiss {
        position: absolute;
        top: 0.5em;
        right: 0.5em;
    }
</style>