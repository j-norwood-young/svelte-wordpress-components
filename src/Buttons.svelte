<script lang="ts">
    import {Button, FormTable, FormInput} from "../index.js";
</script>

<h1>Buttons</h1>


<h2>Events</h2>

<table class="wp-list-table widefat fixed striped table-view-list">
    <thead>
        <tr>
            <th class="cell-sm">Button</th>
            <th>Code</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><Button on:click={() => alert("You clicked me")}>Click Me</Button></td>
            <td><pre><code>&lt;Button on:click=&#123;() =&gt; alert("You clicked me")&#125;&gt;Click Me&lt;/Button&gt;</code></pre></td>
        </tr>
    </tbody>
</table>

<h2>Types</h2>

<form method="GET">
    <FormTable>
        <FormInput type="text" label="Example text input to demo Submit and Reset buttons" value="Example value" />
    </FormTable>
    <table class="wp-list-table widefat fixed striped table-view-list">
        <thead>
            <tr>
                <th class="cell-sm">Button</th>
                <th>Code</th>
            </tr>
        </thead>
        <tbody>
            <tr>
                <td><Button type="button">Button</Button></td>
                <td><pre><code>&lt;Button type="button"&gt;Button&lt;/Button&gt;</code></pre></td>
            </tr>
            <tr>
                <td><Button type="submit">Submit</Button></td>
                <td><pre><code>&lt;Button type="submit"&gt;Submit&lt;/Button&gt;</code></pre></td>
            </tr>
            <tr>
                <td><Button type="reset">Reset</Button></td>
                <td><pre><code>&lt;Button type="reset"&gt;Reset&lt;/Button&gt;</code></pre></td>
            </tr>
        </tbody>
    </table>
</form>


<h2>WP Classes</h2>

<table class="wp-list-table widefat fixed striped table-view-list">
    <thead>
        <tr>
            <th class="cell-sm">Button</th>
            <th>Code</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><Button>Default</Button></td>
            <td><pre><code>&lt;Button&gt;Default&lt;/Button&gt;</code></pre></td>
        </tr>
        <tr>
            <td><Button primary>Primary</Button></td>
            <td><pre><code>&lt;Button primary&gt;Primary&lt;/Button&gt;</code></pre></td>
        </tr>
        <tr>
            <td><Button large>Large</Button></td>
            <td><pre><code>&lt;Button large&gt;Large&lt;/Button&gt;</code></pre></td>
        </tr>
        <tr>
            <td><Button small>Small</Button></td>
            <td><pre><code>&lt;Button small&gt;Small&lt;/Button&gt;</code></pre></td>
        </tr>
        <tr>
            <td><Button warning>Warning</Button></td>
            <td><pre><code>&lt;Button warning&gt;Warning&lt;/Button&gt;</code></pre></td>
        </tr>
        <tr>
            <td><Button danger>Danger</Button></td>
            <td><pre><code>&lt;Button danger&gt;Danger&lt;/Button&gt;</code></pre></td>
        </tr>
        <tr>
            <td><Button link>Link</Button></td>
            <td><pre><code>&lt;Button link&gt;Link&lt;/Button&gt;</code></pre></td>
        </tr>
    </tbody>
</table>


<h2>Attributes</h2>

<table class="wp-list-table widefat fixed striped table-view-list">
    <thead>
        <tr>
            <th class="cell-sm">Button</th>
            <th>Code</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><Button id="MyButton">ID #MyButton</Button></td>
            <td><pre><code>&lt;Button id="MyButton"&gt;#MyButton&lt;/Button&gt;</code></pre></td>
        </tr>
        <tr>
            <td><Button class="my-button">Class .my-button</Button></td>
            <td><pre><code>&lt;Button class="my-button"&gt;.my-button&lt;/Button&gt;</code></pre></td>
        </tr>
        <tr>
            <td><Button aria_label="My Button" aria_hidden>aria-label="My Button" aria-hidden</Button></td>
            <td><pre><code>&lt;Button aria_label="My Button" aria_hidden&gt;aria-label="My Button" aria-hidden&lt;/Button&gt;</code></pre></td>
        </tr>
        <tr>
            <td><Button disabled>Disabled</Button></td>
            <td><pre><code>&lt;Button disabled&gt;Disabled&lt;/Button&gt;</code></pre></td>
        </tr>
        <tr>
            <td><Button title="My Button">title="My Button"</Button></td>
            <td><pre><code>&lt;Button title="My Button"&gt;title="My Button"&lt;/Button&gt;</code></pre></td>
        </tr>
    </tbody>
</table>
    

<style>
    .cell-sm {
        width: 300px;
    }
</style>