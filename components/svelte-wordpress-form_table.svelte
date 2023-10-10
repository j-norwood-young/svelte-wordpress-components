<script>
    export let id = null;
</script>

<table {id} class="form-table {$$restProps.class || ''}">
    <tbody>
        <slot></slot>
    </tbody>
</table>