<script lang="ts">
    enum HeaderType {
        select = "select",
        image = "image",
        text = "text",
        link = "link",
        date = "date",
        number = "number",
        boolean = "boolean",
        unsafe = "unsafe",
        component = "component"
    }

    interface Header {
        name: string;
        key: string;
        type: HeaderType | string;
        width_px?: number;
    }

    export let headers: Header[] = [];
    export let data: any[] = [];
    export let striped = true;
    export let list_table = true;
    export let widefat = true;
    export let fixed = true;

    function format_date(date: string) {
        if (!date) return "";
        const d = new Date(date);
        // yyyy-mm-dd
        return `${d.getFullYear()}-${('0' + (d.getMonth()+1)).slice(-2)}-${('0' + d.getDate()).slice(-2)}`;
    }
</script>

<table class:striped class:wp-list-table={list_table} class:widefat class:fixed>
    <thead>
        <tr>
            {#each headers as header}
                {#if header.type === "select"}
                <td class="manage-column check-column" >
                    <label class="screen-reader-text" for="">Select All</label> 
                    <input class="" type="checkbox">
                </td>
                {:else}
                <th scope="col" class="manage-column" style:width={`${header.width_px}px`}>{header.name}</th>
                {/if}
            {/each}
        </tr>
    </thead>
    <tbody>
        {#each data as row}
        <tr>
            {#each headers as header}
                {#if header.type === "select"}
                <th scope="row" class="check-column"><label class="screen-reader-text" for="cb-select-1">Select</label> <input class="cb-select-1" type="checkbox"></th>
                {:else if header.type === "image"}
                <td class="column-image">
                    <img class="image" width="50" height="50" src={row[header.key]} alt="">
                </td>
                {:else if header.type === "text"}
                <td>{row[header.key]}</td>
                {:else if header.type === "link"}
                <td>
                    <a href={row[header.key]}>{row[header.key]}</a>
                </td>
                {:else if header.type === "date"}
                <td>{format_date(row[header.key])}</td>
                {:else if header.type === "number"}
                <td>{row[header.key]}</td>
                {:else if header.type === "boolean"}
                <td>
                    {#if row[header.key]}
                    <span class="dashicons dashicons-yes"></span>
                    {:else}
                    <span class="dashicons dashicons-no"></span>
                    {/if}
                </td>
                {:else if header.type === "unsafe"}
                <td>
                    {#if row[header.key]}
                    {@html row[header.key]}
                    {/if}
                </td>
                {:else if header.type === "component"}
                <td>
                    <svelte:component this={row[header.key].component} {...row[header.key].props} />
                </td>
                {/if}
            {/each}
        </tr>
        {/each}
    </tbody>
</table>