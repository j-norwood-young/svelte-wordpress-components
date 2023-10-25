<script lang="ts">
    import Buttons from "./Buttons.svelte";
    import Alerts from "./Alerts.svelte";
    import Forms from "./Forms.svelte";
    import { Tabs } from "../index.js";

    let tabs = [
        {
            id: "alerts",
            title: "Alerts",
            component: Alerts
        },
        {
            id: "buttons",
            title: "Buttons",
            component: Buttons
        },
        {
            id: "forms",
            title: "Forms",
            component: Forms
        }
    ];

</script>

<h1>Components</h1>
<h1>Svelte Wordpress Components</h1>
<p>Here you can find a list of all the components that are available to use in your Wordpress theme.</p>

<Tabs {tabs} />