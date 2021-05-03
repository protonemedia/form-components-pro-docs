# Inertia.js Form Helper

You can pass an instance of the [Inertia.js Form Helper](https://inertiajs.com/forms#form-helper) to the form by using `v-model` on the `Form` component. This will bind the values, as well as the validation errors. You don't have to explicitly set the `:errors` attribute, as described [in the validation documentation](#validation).

```js
<template>
  <Form v-model="form">
    <Input name="name" label="Your name" />
    <Submit />
  </Form>
</template>

<script>
export default {
  data() {
    return {
      form: this.$inertia.form({
        name: "",
      }),
    };
  },
};
</script>
```