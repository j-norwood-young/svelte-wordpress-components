# Svelte Wordpress Components

This is a collection of Svelte components, primarily useful for Wordpress admin pages.

## Usage

```javascript
<script>
import { Button } from 'svelte-wordpress-components';
function handleClick() {
    alert('Clicked!');
}
</script>

<Button on:click={handleClick} primary={true} href="/">Click me!</Button>
```

## Components

| Name | Description | Individual Component |
| --- | --- | --- |
| [Alert](#alert) | An alert. | [Alert.svelte](components/Alert.svelte) |
| [Button](#button) | A button. | [Button.svelte](components/Button.svelte) |
| [FormInput](#forminput) | A form input. | [FormInput.svelte](components/FormInput.svelte) |
| [FormTable](#formtable) | A form table. | [FormTable.svelte](components/FormTable.svelte) |
| [ListTable](#listtable) | A list table. | [ListTable.svelte](components/ListTable.svelte) |

Missing a component? Ask for it, or send me a pull request.

### Alert

```javascript
<script>
import { Alert } from 'svelte-wordpress-components';
</script>

<Alert type="success">Success!</Alert>
```

#### Props

| Name | Type | Default | Description |
| --- | --- | --- | --- |
| type | string | 'info' | The type of alert. Can be 'info', 'success', 'warning', or 'error'. |
| dismissible | boolean | false | Whether the alert can be dismissed. |
| display_icon | boolean | true | Whether to display an icon. |
| class | string | null | The classes of the alert. |

### Button

```javascript
<script>
import { Button } from 'svelte-wordpress-components';
</script>

<Button primary={true} href="/">Click me!</Button>
```

#### Props

| Name | Type | Default | Description |
| --- | --- | --- | --- |
| href | string | null | The URL to link to. |
| primary | boolean | false | Whether the button is a primary button. |
| target | string | null | The target of the link, eg '_blank' |
| rel | string | null | The rel of the link, eg 'noopener' |
| title | string | null | The title of the link. |
| type | string | 'button' | The type of button. Can be 'button', 'submit', or 'reset'. |
| id | string | null | The ID of the button. |
| class | string | 'button' | The classes of the button. |
| disabled | boolean | false | Whether the button is disabled. |
| aria_label | string | null | The aria-label of the button. |
| aria_hidden | boolean | false | Whether the button is aria-hidden. |
| large | boolean | false | Whether the button is large. |
| small | boolean | false | Whether the button is small. |
| warning | boolean | false | Whether the button is a warning button. |
| danger | boolean | false | Whether the button is a danger button. |
| link | boolean | false | Whether the button is a link. |

### FormInput

```javascript
<script>
import { FormInput } from 'svelte-wordpress-components';
</script>

<FormInput label="Name" name="name" value="John Doe" />
```

#### Props

| Name | Type | Default | Description |
| --- | --- | --- | --- |
| id | string | null | The ID of the input. |
| name | string | null | The name of the input. |
| label | string | null | The label of the input. |
| type | string | 'text' | The type of input. Can be 'text', 'email', 'password', 'number', 'url', 'tel', 'date', 'time', 'datetime-local', 'month', 'week', 'color', 'checkbox', 'radio', 'textarea', 'select', 'file', or 'hidden'. |
| value | string | null | The value of the input. |
| values | array | [] | The values of radio and checkbox input. |
| description | string | null | A description of the input that will display below the input. |
| class | string | null | The classes of the alert. |
| placeholder | string | null | The placeholder of the input. |
| required | boolean | false | Whether the input is required. |
| readonly | boolean | false | Whether the input is readonly. |
| disabled | boolean | false | Whether the input is disabled. |
| options | array | [] | The options of a checkbox, radio or select input. |
| multiple | boolean | false | Whether a select input takes multiple options. |
| checked | boolean | false | Whether a checkbox input is checked. |
| min | string | null | The min of a number input. |
| max | string | null | The max of a number input. |
| step | string | null | The step of a number input. |
| pattern | string | null | The pattern of the input. |
| rows | string | null | The rows of a textarea input  |
| cols | string | null | The cols of a textarea input. |
| wrap | string | null | Whether to wordwrap a textarea input. |

### Form Table

NOTE: Previously called Form

```javascript
<script>
import { FormTable, FormInput } from 'svelte-wordpress-components';
</script>

<FormTable>
    <FormInput label="Name" name="name" value="John Doe" />
</FormTable>
```

#### Props

| Name | Type | Default | Description |
| --- | --- | --- | --- |
| class | string | null | The classes of the alert. |
| id | string | null | The ID of the form. |

### ListTable

A list table creates a table similar to a [WP_List_Table](https://developer.wordpress.org/reference/classes/wp_list_table/).

```javascript
<script>
import { ListTable } from 'svelte-wordpress-components';
const headers = [
        {
            name: "select",
            key: "select",
            type: "select",
        },
        {
            name: "Name",
            key: "link_name",
            type: "unsafe",
        },
        {
            name: "Created",
            key: "createdAt",
            type: "date",
        },
        {
            name: "Active",
            key: "active",
            type: "boolean",
        },
    ]
const data = [
        {
            select: true,
            link_name: '<a href="#">John Doe</a>',
            createdAt: '2020-01-01',
            active: true,
        },
        {
            select: false,
            link_name: '<a href="#">Jane Doe</a>',
            createdAt: '2020-01-01',
            active: false,
        },
    ]

</script>

<ListTable {headers} {data} />
```

#### Props

| Name | Type | Default | Description |
| --- | --- | --- | --- |
| headers | array | [] | The headers of the table. |
| data | array | [] | The data of the table. |

#### Header


| Name | Type | Default | Description |
| --- | --- | --- | --- |
| name | string | null | The name of the header. |
| key | string | null | The key of the header. |
| type | string | null | The type of the header. Can be 'select', 'image', 'text', 'link', 'date', 'number', 'boolean', or 'unsafe' (does not escape HTML). |
