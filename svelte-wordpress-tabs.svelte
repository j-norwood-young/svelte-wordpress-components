<script>
    export let tabs = [];
    export let current_tab = null;

    function do_select_tab(tab) {
        current_tab = tab;
    }
</script>

<nav class="nav-tab-wrapper">
    {#each tabs as tab}
        <a href={""} class="nav-tab" nav-tab-active={tab.title === current_tab.title} on:click={() => do_select_tab(tab)}>{tab.title}</a>
    {/each}
</nav>