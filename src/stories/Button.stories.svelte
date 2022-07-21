<script lang="ts">
    import { Meta, Story, Template } from '@storybook/addon-svelte-csf';
    import Button from './Button.svelte';
</script>

<Meta
    title="Example/Button"
    component={Button}
    parameters={{
        controls: {
            expanded: true,
            sort: 'requiredFirst'
        }
    }}
    argTypes={{
        backgroundColor: {
            control: 'color'
        },
        slot_default: {
            control: 'text',
            name: 'default'
        },
        event_click: {
            action: 'click',
            name: 'click',
            control: 'none'
        },
        primary: {
            control: 'boolean'
        },
        size: {
            control: { type: 'select' },
            options: ['small', 'medium', 'large'],
        }
    }}
/>

<Template let:args>
    <Button {...args} on:click={args.event_click}>
        {args.slot_default}
    </Button>
</Template>

<Story name="Primary" args={{primary: true, slot_default: 'Button Label'}} />
