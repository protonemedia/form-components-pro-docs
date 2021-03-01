# Validation errors

## Specify an error per element

With the `error` attribute, you can pass a validation error to any form element. This also works for the `Group` component.

```html
<Form>
  <Input v-model="user.name" :error="errors.name" />

  <Group label="Prefered IDE theme" inline :error="errors.theme">
    <Radio v-model="user.theme" value="dark" label="Dark theme" />
    <Radio v-model="user.theme" value="light" label="Light theme" />
  </Group>

  <Submit />
</Form>
```

## Errors per form

Just like passing an object to `v-model` on the `Form` component, you can give it an error object as well. Now each error will be evaluated by the `name` attribute.

```html
<Form v-model="company" :errors="errors">
  <Input name="business_name" />
  <Input name="vat_number" />

  <Submit />
</Form>
```

## Hiding errors

Suppose you want to hide a validation error. In that case, you can use the `show-error` attribute, which defaults to `true` (except on the [Radio component](#group-component)).

```html
<Form v-model="company" :errors="errors">
  <Input name="business_name" />
  <Input name="vat_number" :show-error="false" />

  <Submit />
</Form>
```