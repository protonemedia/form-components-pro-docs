# Integrations with third-party Libaries

Currently, all three libraries are included in the bundle *by default*. This will be fixed before the first public release.

## Autosize

Add the `autosize` attribute to the `Textarea` component:

```html
<Textarea name="biography" autosize />
```

## Litepicker

Add the `date` attribute to the `Input` component:

```html
<Input name="published_at" date />
```

You can instantiate Litepicker with a [custom set of options](https://litepicker.com/docs/options) by passing an object to the `date` attribute:

```html
<Input name="published_at" :date="{ format: 'YYYY' }" />
```

## Choices.js

Choices.js uses a *SCSS* stylesheet to style the library. Our stylesheet extends the vendor stylesheet (of Choices.js) and adds some Tailwind-specific tweaks. Make sure your bundler handles SCSS stylesheets correctly.

You can import the stylesheet in your Vue component:

```js
import "@protonemedia/form-components-pro-vue2-tailwind2-unstyled/src/choices.scss"
```

Add the `choices` attribute to the `Select` component:

```html
<Select name="favorite_framework" :options="frameworks" choices />
```

This works for selecting multiple values as well:

```html
<Select name="favorite_framework" :options="frameworks" mulitple choices />
```

You can instantiate Choices.js with a [custom set of options](https://github.com/jshjohnson/Choices#setup) by passing an object to the `choices` attribute:

```html
<Select name="favorite_framework" :options="frameworks" :choices="{ searchEnabled: false }" />
```