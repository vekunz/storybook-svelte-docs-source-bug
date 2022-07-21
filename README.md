# storybook-svelte-docs-source-bug

This repository demonstrates the issue that Storybook Docs does not generate the source code of an Svelte story correctly.

## Reproduction

To reproduce the issue, execute the following commands.
```shell
npm install

npm run storybook
```

Now a browser opens with Storybook. Select the "Button" story, go to the docs page and expand the source code panel with the **Show code** button.

## The bug

The source code panel shows this code
```html
<Button primary slot_default="Button Label" event_click={undefined}/>
```

But the panel should show this code instead
```html
<Button primary>Button Label</Button>
```
