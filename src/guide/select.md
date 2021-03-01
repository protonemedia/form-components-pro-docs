# Select elements

You can give the `Select` component a set of options that is either an Array or an Object. If you go with an Object, it should be a simple *key-value* collection. An Array should consists of one or more objects that have a `value` and `label` key.

Object example:
```js
<script>
export default {
  data() {
    return {
      selectOptions: {
        tailwind: "Tailwind CSS",
        bootstrap: "Bootstrap",
      },
    };
  },
};
</script>
```

Array example:
```js
<script>
export default {
  data() {
    return {
      selectOptions: [
        { value: "tailwind", label: "Tailwind CSS" },
        { value: "bootstrap", label: "Bootstrap" },
      ],
    };
  },
};
</script>
```

By using an Array, you could supply additional attributes, like `disabled`:

```js
<script>
export default {
  data() {
    return {
      selectOptions: [
        { value: "tailwind", label: "Tailwind CSS" },
        { value: "bootstrap", label: "Bootstrap", disabled: true },
      ],
    };
  },
};
</script>
```

There's support for grouping (`optgroup`) as well. Each group object should have a `label` key and an `options` key, which should be an Array:

```js
<script>
export default {
  data() {
    return {
      frameworks: [
        {
          label: "CSS Frameworks",
          options: [
            { value: "tailwind", label: "Tailwind CSS" },
            { value: "bootstrap", label: "Bootstrap" },
          ],
        },
        {
          label: "PHP Frameworks",
          options: [
            { value: "laravel", label: "Laravel" },
            { value: "symfony", label: "Symfony" },
          ],
        },
      ],
    };
  },
};
</script>
```

Instead of giving a set of options, you can also pass a custom slot into the `Select` component:

```html
<Select name="favorite_framework">
  <option value="tailwind">Tailwind CSS</option>
  <option value="bootstrap">Bootstrap</option>
</Select>
```