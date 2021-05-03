# Reactivity

One of the great features of Vue is [two-way data bindings](https://vuejs.org/v2/guide/forms.html) on form elements. This is fully supported on all Form Components and all integrations with third-party libraries.

## Use v-model on individual form elements

You can set the `v-model` on each individual form element. The `label` attribute is optional.

```js
<template>
  <div id="app">
    <Form class="p-8">
      <Input v-model="user.name" label="Your name" />
      <Textarea v-model="user.biography" label="Write your story" autosize />
      <Input v-model="user.date_of_birth" label="Date of birth" date />
      <Select v-model="user.favorite_framework" :options="frameworks" label="Pick your favorite framework"/>
      <Select v-model="user.interests" :options="interests" label="Choose your interests" multiple />

      <Group label="Prefered IDE theme" inline>
        <Radio v-model="user.theme" value="dark" label="Dark theme" />
        <Radio v-model="user.theme" value="light" label="Light theme" />
      </Group>

      <Group>
        <Checkbox v-model="user.newsletter" label="Do you want to receive my newsletter?" />
      </Group>

      <Submit />
    </Form>
  </div>
</template>

<script>
export default {
  data() {
    return {
      user: {
        name: "",
        biography: "",
        date_of_birth: "",
        favorite_framework: "",
        interests: [],
        theme: "light",
        newsletter: false,
      },

      frameworks: {
        tailwind: "Tailwind CSS",
        bootstrap: "Bootstrap",
      },

      interests: [
        { value: "tailwind", label: "Tailwind CSS" },
        { value: "bootstrap", label: "Bootstrap" },
        { value: "inertiajs", label: "Inertia.js" },
        { value: "livewire", label: "Livewire" },
        { value: "laravel", label: "Laravel" },
      ],
    };
  },
};
</script>
```

## Use v-model on the Form component

You can also pass an object to the form by using `v-model` on the `Form` component. The binding of the Form Components is now based on the `name` attribute. Nested properties using the dot-notation are supported as well (`biography` example). The package can [evaluate validation errors](#errors-per-form) by the `name` attribute as well. This is great as the `name` attribute is used for both, so you don't have to define the `v-model` and `error` attributes manually.

```js
<template>
  <div id="app">
    <Form class="p-8" v-model="user">
      <Input name="name" label="Your name" />

      <Textarea name="biography.en" label="Write your story (English)" autosize />
      <Textarea name="biography.nl" label="Write your story (Dutch)" autosize />

      <Input name="date_of_birth" label="Date of birth" date />
      <Select name="favorite_framework" :options="frameworks" label="Pick your favorite framework" />
      <Select name="interests" :options="interests" label="Choose your interests" multiple />

      <Group label="Prefered IDE theme" inline>
        <Radio name="theme" value="dark" label="Dark theme" />
        <Radio name="theme" value="light" label="Light theme" />
      </Group>

      <Group>
        <Checkbox name="newsletter" label="Do you want to receive my newsletter?" />
      </Group>

      <Submit />
    </Form>
  </div>
</template>

<script>
export default {
  data() {
    return {
      user: {
        name: "",
        biography: {
          en: "",
          nl: "",
        },
        date_of_birth: "",
        favorite_framework: "",
        interests: [],
        theme: "light",
        newsletter: false,
      },

      frameworks: [
        { value: "tailwind", label: "Tailwind CSS" },
        { value: "bootstrap", label: "Bootstrap" },
      ],

      interests: [
        { value: "tailwind", label: "Tailwind CSS" },
        { value: "bootstrap", label: "Bootstrap" },
        { value: "inertiajs", label: "Inertia.js" },
        { value: "livewire", label: "Livewire" },
        { value: "laravel", label: "Laravel" },
      ],
    };
  },
};
</script>
```
