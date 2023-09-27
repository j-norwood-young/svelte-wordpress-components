<script>
    export let type = "button";
    export let href = null;
    export let target = null;
    export let rel = null;
    export let title = null;
    export let disabled = false;
    export let id = null;
    export let primary = false;
    export let large = false;
    export let warning = false;
    export let danger = false;
    export let link = false;
    export let aria_label = null;
    export let aria_hidden = false;
    export let btn_class = "button";
    let style = "";
    $: if (warning) {
        style = "color: #a00; border-color: #a00;";
    }
    $: if (danger) {
        style = "background-color: #a00; border-color: #a00; color: #fff;";
    }

</script>

<button {type} {href} {target} {rel} {title} {disabled} aria-label={aria_label} aria-hidden={aria_hidden} {id} class="button {btn_class}" class:button-primary={primary} class:button-large={large} class:delete={warning} class:button-link={link} {style} on:click>
    <slot></slot>
</button>