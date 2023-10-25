<script lang="ts">
    import { FormTable, FormInput, ListTable } from "../index.js";

    let headers = [{
        name: "Form Input",
        key: "form-input",
        type: "component",
        width_px: 400
    },
    {
        name: "Code",
        key: "code",
        type: "text"
    },
    {
        name: "Attributes",
        key: "attributes",
        type: "unsafe"
    }];
    
    const text_inputs = [{
        "form-input": {
            component: FormInput,
            props: {
                label: "Text",
                type: "text",
                placeholder: "Placeholder"
            }
        },
        "code": `<FormInput label="Text" type="text" placeholder="Placeholder" />`,
        "attributes": `label<br>placeholder<br>required<br>readonly<br>disabled<br>id<br>class<br>pattern`
    },
    {
        "form-input": {
            component: FormInput,
            props: {
                label: "Password",
                type: "password"
            }
        },
        "code": `<FormInput label="Password" type="password" />`,
        "attributes": `label<br>required<br>readonly<br>disabled<br>id<br>class<br>pattern`
    },
    {
        "form-input": {
            component: FormInput,
            props: {
                label: "Email",
                type: "email"
            }
        },
        "code": `<FormInput label="Email" type="email" />`,
        "attributes": `label<br>required<br>readonly<br>disabled<br>id<br>class<br>pattern`
    },
    {
        "form-input": {
            component: FormInput,
            props: {
                label: "URL",
                type: "url"
            }
        },
        "code": `<FormInput label="URL" type="url" />`,
        "attributes": `label<br>required<br>readonly<br>disabled<br>id<br>class<br>pattern`
    },
    {
        "form-input": {
            component: FormInput,
            props: {
                label: "Tel",
                type: "tel"
            }
        },
        "code": `<FormInput label="Tel" type="tel" />`,
        "attributes": `label<br>required<br>readonly<br>disabled<br>id<br>class<br>pattern`
    },
    {
        "form-input": {
            component: FormInput,
            props: {
                label: "Number",
                type: "number",
                min: 1,
                max: 100,
                step: 2
            }
        },
        "code": `<FormInput label="Number" type="number" min={1} max={100} step={2} />`,
        "attributes": `label<br>required<br>readonly<br>disabled<br>id<br>class<br>min<br>max<br>step`
    },
    {
        "form-input": {
            component: FormInput,
            props: {
                label: "Textarea",
                type: "textarea",
                cols: 40,
                rows: 5
            }
        },
        "code": `<FormInput label="Textarea" type="textarea" cols={40} rows={5} />`,
        "attributes": `label<br>required<br>readonly<br>disabled<br>id<br>class<br>cols<br>rows<br>wrap`
    }
    ];

    const select_inputs = [{
        "form-input": {
            component: FormInput,
            props: {
                label: "Select",
                type: "select",
                options: [
                    { label: "Option 1", value: "option-1" },
                    { label: "Option 2", value: "option-2" },
                    { label: "Option 3", value: "option-3" }
                ],
                value: "option-2"
            }
        },
        "code": `<FormInput label="Select" type="select" options={[{ label: "Option 1", value: "option-1" }, { label: "Option 2", value: "option-2" }, { label: "Option 3", value: "option-3" }]} value="option-2" />`,
        "attributes": `label<br>required<br>readonly<br>disabled<br>id<br>class<br>multiple`
    },
    {
        "form-input": {
            component: FormInput,
            props: {
                label: "Radio",
                type: "radio",
                options: [
                    { label: "Option 1", value: "option-1" },
                    { label: "Option 2", value: "option-2" },
                    { label: "Option 3", value: "option-3" }
                ]
            }
        },
        "code": `<FormInput label="Radio" type="radio" options={[{ label: "Option 1", value: "option-1" }, { label: "Option 2", value: "option-2" }, { label: "Option 3", value: "option-3" }]} />`,
        "attributes": `label<br>required<br>readonly<br>disabled<br>id<br>class`
    },{
        "form-input": {
            component: FormInput,
            props: {
                label: "Checkbox",
                type: "checkbox"
            }
        },
        "code": `<FormInput label="Checkbox" type="checkbox" />`,
        "attributes": `label<br>required<br>readonly<br>disabled<br>id<br>class`
    }]

    const button_inputs =[{
        "form-input": {
            component: FormInput,
            props: {
                label: "Submit",
                type: "submit"
            }
        },
        "code": `<FormInput label="Submit" type="submit" />`,
        "attributes": `label<br>required<br>readonly<br>disabled<br>id<br>class`
    },
    {
        "form-input": {
            component: FormInput,
            props: {
                label: "Reset",
                type: "reset"
            }
        },
        "code": `<FormInput label="Reset" type="reset" />`,
        "attributes": `label<br>required<br>readonly<br>disabled<br>id<br>class`
    },
    {
        "form-input": {
            component: FormInput,
            props: {
                label: "Button",
                type: "button"
            }
        },
        "code": `<FormInput label="Button" type="button" />`,
        "attributes": `label<br>required<br>readonly<br>disabled<br>id<br>class`
    }]

    const datetime_inputs = [{
        "form-input": {
            component: FormInput,
            props: {
                label: "Date",
                type: "date"
            }
        },
        "code": `<FormInput label="Date" type="date" />`,
        "attributes": `label<br>required<br>readonly<br>disabled<br>id<br>class<br>min<br>max<br>step`
    },
    {
        "form-input": {
            component: FormInput,
            props: {
                label: "Month",
                type: "month"
            }
        },
        "code": `<FormInput label="Month" type="month" />`,
        "attributes": `label<br>required<br>readonly<br>disabled<br>id<br>class`
    },
    {
        "form-input": {
            component: FormInput,
            props: {
                label: "Week",
                type: "week"
            }
        },
        "code": `<FormInput label="Week" type="week" />`,
        "attributes": `label<br>required<br>readonly<br>disabled<br>id<br>class`
    },
    {
        "form-input": {
            component: FormInput,
            props: {
                label: "Time",
                type: "time"
            }
        },
        "code": `<FormInput label="Time" type="time" />`,
        "attributes": `label<br>required<br>readonly<br>disabled<br>id<br>class`
    },
    {
        "form-input": {
            component: FormInput,
            props: {
                label: "Datetime Local",
                type: "datetime-local"
            }
        },
        "code": `<FormInput label="Datetime Local" type="datetime-local" />`,
        "attributes": `label<br>required<br>readonly<br>disabled<br>id<br>class`
    }]

    const misc_inputs = [{
        "form-input": {
            component: FormInput,
            props: {
                label: "Range",
                type: "range",
                min: 1,
                max: 100,
                step: 2
            }
        },
        "code": `<FormInput label="Range" type="range" min={1} max={100} step={2} />`,
        "attributes": `label<br>required<br>readonly<br>disabled<br>id<br>class<br>min<br>max<br>step`
    },
    {
        "form-input": {
            component: FormInput,
            props: {
                label: "Color",
                type: "color"
            }
        },
        "code": `<FormInput label="Color" type="color" />`,
        "attributes": `label<br>required<br>readonly<br>disabled<br>id<br>class`
    },
    {
        "form-input": {
            component: FormInput,
            props: {
                label: "File",
                type: "file"
            }
        },
        "code": `<FormInput label="File" type="file" />`,
        "attributes": `label<br>required<br>readonly<br>disabled<br>id<br>class`
    }]

    const attributes = [{
        "form-input": {
            component: FormInput,
            props: {
                label: "Normal",
                type: "text",
                placeholder: "Placeholder"
            }
        },
        "code": `<FormInput label="Normal" type="text" placeholder="Placeholder" />`,
        "attributes": `label<br>placeholder<br>required<br>readonly<br>disabled<br>id<br>class<br>pattern`
    },
    {
        "form-input": {
            component: FormInput,
            props: {
                label: "Disabled",
                type: "text",
                placeholder: "Placeholder",
                disabled: true
            }
        },
        "code": `<FormInput label="Disabled" type="text" placeholder="Placeholder" disabled />`
    },
    {
        "form-input": {
            component: FormInput,
            props: {
                label: "Readonly",
                type: "text",
                placeholder: "Placeholder",
                readonly: true
            }
        },
        "code": `<FormInput label="Readonly" type="text" placeholder="Placeholder" readonly />`
    },
    {
        "form-input": {
            component: FormInput,
            props: {
                label: "Required",
                type: "text",
                placeholder: "Placeholder",
                required: true
            }
        },
        "code": `<FormInput label="Required" type="text" placeholder="Placeholder" required />`
    },
    {
        "form-input": {
            component: FormInput,
            props: {
                label: "ID",
                type: "text",
                placeholder: "Placeholder",
                id: "my-id"
            }
        },
        "code": `<FormInput label="ID" type="text" placeholder="Placeholder" id="my-id" />`
    },
    {
        "form-input": {
            component: FormInput,
            props: {
                label: "Class",
                type: "text",
                placeholder: "Placeholder",
                class: "my-class"
            }
        },
        "code": `<FormInput label="Class" type="text" placeholder="Placeholder" class="my-class" />`
    },
    {
        "form-input": {
            component: FormInput,
            props: {
                label: "Pattern",
                type: "text",
                placeholder: "Placeholder",
                pattern: "[A-Za-z]{3}"
            }
        },
        "code": `<FormInput label="Pattern" type="text" placeholder="Placeholder" pattern="[A-Za-z]{3}" />`
    },
    {
        "form-input": {
            component: FormInput,
            props: {
                label: "Min. Max and Step",
                type: "number",
                min: 1,
                max: 100,
                step: 2
            }
        },
        "code": `<FormInput label="Min" type="number" min={1} max={100} step={2} />`
    },
    {
        "form-input": {
            component: FormInput,
            props: {
                label: "Cols and Rows",
                type: "textarea",
                cols: 40,
                rows: 5
            }
        },
        "code": `<FormInput label="Rows" type="textarea" cols={40} rows={5} />`
    },

    ]
</script>

<h1>Forms</h1>

<p>There are two main components that typically work together for forms, the FormInput which represents a form component, and the FormTable which would typically wrap a form to assist with layout.</p>

<p>The examples below do not use the FormTable to show them in their pure form, but a component in a form table would look like this:</p>

<FormTable>
    <FormInput label="Text" type="text" placeholder="Placeholder" />
</FormTable>

<p>Note that all form elements are included in the FormInput type, and there are no separate components for different types of elements. The component will adapt to single or multiple values depending on the type of input you need.</p>

<h3 id="text_inputs">Text Inputs</h3>
<ListTable {headers} data={text_inputs} />

<h3 id="select_inputs">Select Inputs</h3>
<ListTable {headers} data={select_inputs} />

<h3 id="button_inputs">Buttons</h3>
<ListTable {headers} data={button_inputs} />

<h3 id="datetime_inputs">Date-Time Inputs</h3>
<ListTable {headers} data={datetime_inputs} />

<h3 id="misc_inputs">Miscellaneous Inputs</h3>
<ListTable {headers} data={misc_inputs} />

<h3 id="attributes">Attributes</h3>
<ListTable {headers} data={attributes} />

<style>
    .cell-sm {
        width: 400px;
    }
</style>