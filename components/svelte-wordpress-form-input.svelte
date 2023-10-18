<script>
    export let id = null;
    export let name = null;
    export let label = "";
    export let type = "text"; 
    export let value = "";
    export let values = [];
    export let placeholder = "";
    export let description = "";
    export let required = false;
    export let readonly = false;
    export let disabled = false;
    export let options = [];
    export let multiple = false;
    export let checked = false;
    export let min = null;
    export let max = null;
    export let step = null;
    export let pattern = null;
    export let rows = null;
    export let cols = null;
    export let wrap = null;

    
    $: if (type === "date" && value) {
        value = parse_date(value);
    }
    

    function parse_date(d) {
        const date = new Date(d);
        const year = date.getFullYear();
        const month = date.getMonth() + 1;
        const day = date.getDate();
        return `${year}-${month.toString().padStart(2, "0")}-${day.toString().padStart(2, "0")}`;
    }
</script>

{#if (type === "hidden")}
<input bind:value={value} type="hidden" {id} {name} {required} {readonly} {disabled}>
{:else}
<tr>
    <th scope="row">
        <label for={id}>{label}</label>
    </th>
    <td>
        {#if (type === "text")}
        <input bind:value={value} type="text" {id} class="{$$restProps.class || ''}" {name} {placeholder} {required} {readonly} {disabled} {pattern}>
        {:else if (type === "password")}
        <input bind:value={value} type="password" {id} class="{$$restProps.class || ''}" {name} {required} {readonly} {disabled} {pattern}>
        {:else if (type === "email")}
        <input bind:value={value} type="email" {id} class="{$$restProps.class || ''}" {name} {required} {readonly} {disabled} {pattern}>
        {:else if (type === "url")}
        <input bind:value={value} type="url" {id} class="{$$restProps.class || ''}" {name} {required} {readonly} {disabled} {pattern}>
        {:else if (type === "tel")}
        <input bind:value={value} type="tel" {id} class="{$$restProps.class || ''}" {name} {required} {readonly} {disabled} {pattern}>
        {:else if (type === "number")}
        <input bind:value={value} type="number" {id} class="{$$restProps.class || ''}" {name} {required} {readonly} {disabled} {min} {max} {step}>
        {:else if (type === "range")}
        <input bind:value={value} type="range" {id} class="{$$restProps.class || ''}" {name} {required} {readonly} {disabled} {min} {max} {step}>
        {:else if (type === "date")}
        <input bind:value={value} type="date" {id} class="{$$restProps.class || ''}" {name} {required} {readonly} {disabled}>
        {:else if (type === "month")}
        <input bind:value={value} type="month" {id} class="{$$restProps.class || ''}" {name} {required} {readonly} {disabled}>
        {:else if (type === "week")}
        <input bind:value={value} type="week" {id} class="{$$restProps.class || ''}" {name} {required} {readonly} {disabled}>
        {:else if (type === "time")}
        <input bind:value={value} type="time" {id} class="{$$restProps.class || ''}" {name} {required} {readonly} {disabled}>
        {:else if (type === "datetime-local")}
        <input bind:value={value} type="datetime-local" {id} class="{$$restProps.class || ''}" {name} {required} {readonly} {disabled}>
        {:else if (type === "color")}
        <input bind:value={value} type="color" {id} class="{$$restProps.class || ''}" {name} {required} {readonly} {disabled}>
        {:else if (type === "checkbox")}
            {#if (multiple)}
                {#each options as option}
                    <input bind:group={values} type="checkbox" 
    {name} value={option.value}>
                {/each}
            {:else}
                <input bind:checked={checked} type="checkbox" {id} class="{$$restProps.class || ''}" {name} {required} {readonly} {disabled}>
            {/if}
        {:else if (type === "radio")}
            {#each options as option}
            <input bind:group={values} type="radio" 
{name} value={option.value}>
            {/each}
        {:else if (type === "file")}
        <input bind:value={value} type="file" {id} class="{$$restProps.class || ''}" {name} {required} {readonly} {disabled}>
        {:else if (type === "submit")}
        <input bind:value={value} type="submit" {id} class="{$$restProps.class || ''}" {name} {required} {readonly} {disabled}>
        {:else if (type === "reset")}
        <input bind:value={value} type="reset" {id} class="{$$restProps.class || ''}" {name} {required} {readonly} {disabled}>
        {:else if (type === "button")}
        <input bind:value={value} type="button" {id} class="{$$restProps.class || ''}" {name} {required} {readonly} {disabled}>
        {:else if (type === "select")}
            {#if (multiple)}
            <select bind:value={value} {id} class="{$$restProps.class || ''}" {name} multiple>
                {#each options as option}
                <option value={option.value}>{option.label}</option>
                {/each}
            </select>
            {:else}
            <select bind:value={value} {id} class="{$$restProps.class || ''}" {name}>
                {#each options as option}
                <option value={option.value}>{option.label}</option>
                {/each}
            </select>
            {/if}
        {:else if (type === "textarea")}
        <textarea bind:value={value} {id} class="{$$restProps.class || ''}" {name} {required} {readonly} {disabled} {rows} {cols} {wrap}></textarea>
        {/if}
        {#if (description)}
        <p class="description">{description}</p>
        {/if}
    </td>
</tr>
{/if}
