<script lang="ts">

    import { onMount } from "svelte";

    interface Tab {
        id: string;
        title: string;
        component?: any;
        content?: string;
    }
    export let tabs: Array<Tab> = [];
    export let current_tab: Tab | null = null;

    function doSelectTab(tab: Tab) {
        window.location.hash = tab.id;
        current_tab = tab;
    }

    onMount(() => {
        const current_hash = window.location.hash;
        if (current_hash) {
            const tab = tabs.find(tab => tab.id === current_hash.substr(1));
            if (tab) {
                current_tab = tab;
            }
        }
        if (!current_tab && tabs.length > 0) {
            current_tab = tabs[0];
        }
    });
</script>

<nav class="nav-tab-wrapper">
    {#each tabs as tab}
        <a href="#{tab.id}" class="nav-tab" class:nav-tab-active={tab.id === current_tab?.id} on:click|preventDefault={() => doSelectTab(tab)}>{tab.title}</a>
    {/each}
</nav>

{#if current_tab}
    <div class="tab-content">
        {#if current_tab.component}
        <svelte:component this={current_tab.component} />
        {:else}
        <div class="tab-content-inner">{current_tab.content}</div>
        {/if}
    </div>
{/if}

<style>
    .nav-tab {
        user-select: none;
        outline-style: none;
        box-shadow: none;
        outline: none;
    }
</style>