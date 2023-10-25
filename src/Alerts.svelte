<script lang="ts">
    import { Alert } from "../index.js";
</script>

<h1>Alerts</h1>

<h2>Types</h2>

<form method="GET">
    <table class="wp-list-table widefat fixed striped table-view-list">
        <thead>
            <tr>
                <th class="cell-sm">Alert</th>
                <th>Code</th>
            </tr>
        </thead>
        <tbody>
            <tr>
                <td><Alert>Default alert</Alert></td>
                <td><pre><code>&lt;Alert&gt;Default alert&lt;/Alert&gt;</code></pre></td>
            </tr>
            <tr>
                <td><Alert type="success">Success alert</Alert></td>
                <td><pre><code>&lt;Alert type="success"&gt;Success alert&lt;/Alert&gt;</code></pre></td>
            </tr>
            <tr>
                <td><Alert type="warning">Warning alert</Alert></td>
                <td><pre><code>&lt;Alert type="warning"&gt;Warning alert&lt;/Alert&gt;</code></pre></td>
            </tr>
            <tr>
                <td><Alert type="error">Error alert</Alert></td>
                <td><pre><code>&lt;Alert type="error"&gt;Error alert&lt;/Alert&gt;</code></pre></td>
            </tr>
            <tr>
                <td><Alert type="info">Info alert</Alert></td>
                <td><pre><code>&lt;Alert type="info"&gt;Info alert&lt;/Alert&gt;</code></pre></td>
            </tr>
        </tbody>
    </table>
</form>

<h2>Icons</h2>

<form method="GET">
    <table class="wp-list-table widefat fixed striped table-view-list">
        <thead>
            <tr>
                <th class="cell-sm">Alert</th>
                <th>Code</th>
            </tr>
        </thead>
        <tbody>
            <tr>
                <td><Alert display_icon={true}>Default alert</Alert></td>
                <td><pre><code>&lt;Alert display_icon=&#123;true&#125;&gt;Default alert&lt;/Alert&gt;</code></pre></td>
            </tr>
            <tr>
                <td><Alert display_icon={true} type="warning">Warning alert</Alert></td>
                <td><pre><code>&lt;Alert display_icon=&#123;true&#125; type="warning"&gt;Warning alert&lt;/Alert&gt;</code></pre></td>
            </tr>
            <tr>
                <td><Alert display_icon={true} type="error">Error alert</Alert></td>
                <td><pre><code>&lt;Alert display_icon=&#123;true&#125; type="error"&gt;Error alert&lt;/Alert&gt;</code></pre></td>
            </tr>
            <tr>
                <td><Alert display_icon={true} type="info">Info alert</Alert></td>
                <td><pre><code>&lt;Alert display_icon=&#123;true&#125; type="info"&gt;Info alert&lt;/Alert&gt;</code></pre></td>
            </tr>
        </tbody>
    </table>
</form>
    

<style>
    .cell-sm {
        width: 300px;
    }
</style>