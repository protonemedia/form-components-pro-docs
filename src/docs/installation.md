# Installation

Make sure you've installed the [@tailwindcss/forms](https://github.com/tailwindlabs/tailwindcss-forms) plugin correctly.

In your project's root folder, create a `.npmrc` file and fill in your [Personal Access Token](https://github.com/settings/tokens) with access to the `read:packages` scope.

```
//npm.pkg.github.com/:_authToken=your-personal-access-token
@protonemedia:registry=https://npm.pkg.github.com
```

Now you can install the package with `npm` or `yarn`:

```bash
npm install @protonemedia/form-components-pro-vue2-tailwind2-unstyled
```

Available packages for Vue.js 2 + Tailwind v2:

* `@protonemedia/form-components-pro-vue2-tailwind2-unstyled`
* `@protonemedia/form-components-pro-vue2-tailwind2-simple`
* `@protonemedia/form-components-pro-vue2-tailwind2-underline`
* `@protonemedia/form-components-pro-vue2-tailwind2-solid`

## Register components

To start using the components, you need to [register](https://vuejs.org/v2/guide/components-registration.html) the components. You can do this globally for your Vue.js app or per component.

### Register globally

By registering the Form Components globally, you can use them in the template of any root Vue instance (`new Vue`).

```js
import Vue from 'vue'
import App from './App.vue'

import "./assets/style.css";

import {
  Checkbox,
  Form,
  Group,
  Input,
  Radio,
  Select,
  Submit,
  Textarea,
} from "@protonemedia/form-components-pro-vue2-tailwind2-unstyled";

Vue.component('Checkbox', Checkbox);
Vue.component('Form', Form);
Vue.component('Group', Group);
Vue.component('Input', Input);
Vue.component('Radio', Radio);
Vue.component('Select', Select);
Vue.component('Submit', Submit);
Vue.component('Textarea', Textarea);

new Vue({
  render: h => h(App),
}).$mount('#app')
```

### Register per component

Instead of registering the components globally, you can also choose to define them in the `components` object of a Vue component.

```js
<template>
  <div id="user_settings">
    <Form class="p-8">

    </Form>
  </div>
</template>

<script>
import {
  Checkbox,
  Form,
  Group,
  Input,
  Radio,
  Select,
  Submit,
  Textarea,
} from "@protonemedia/form-components-pro-vue2-tailwind2-unstyled";

export default {
  components: {
    Checkbox,
    Form,
    Group,
    Input,
    Radio,
    Select,
    Submit,
    Textarea,
  },
};
</script>
```