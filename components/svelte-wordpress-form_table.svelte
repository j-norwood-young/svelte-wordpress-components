<script lang="ts">
    export let id: string | null | undefined = null;
</script>

<table {id} class="form-table {$$restProps.class || ''}">
    <tbody>
        <slot></slot>
    </tbody>
</table>