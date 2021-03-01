# Misc

## Submit button

The submit button has a default text of `Submit`, but you can pass in a slot as well:

```html
<Submit>Do something!</Submit>
```

## Group component

With the `Group` component, you can group checkboxes and radio elements. You can use the `inline` attribute to arrange the children horizontally. Just like other the components, the `Group` component also supports the `error` and `label` attributes.

Most of the time, you don't want to show validation errors on each radio element, so the validation errors are hidden by default on the `Radio` component. Instead, you can use the `Group` component to show the error just once.

```html
<Form v-model="settings" :errors="errors">
  <Group name="theme" inline>
    <Radio name="theme" value="dark" label="Dark theme" />
    <Radio name="theme" value="light" label="Light theme" />
  </Group>

  <Group>
    <Checkbox name="newsletter" label="Do you want to receive my newsletter?" />
    <Checkbox name="terms" label="Do you agree with the terms?" />
  </Group>
</Form>
```

If you want to show the error on the `Radio` component, you can use the `show-error` attribute:

```html
<Form v-model="settings" :errors="errors">
  <Group>
    <Radio name="theme" value="dark" label="Dark theme" :show-error="true" />
    <Radio name="theme" value="light" label="Light theme" :show-error="true" />
  </Group>
</Form>
```

## Attribute inheritance

Additional attributes are passed down the form element itself. For example, the `placeholder` attribute is passed down to the inner input element, not to the `Input` component's outer `div`.

```html
<Input v-model="user.name" placeholder="Your name" data-foo="bar" />
```

Rendered template:

```html
<div>
  <input v-model="..." placeholder="Your name" data-foo="bar" />
</div>
```