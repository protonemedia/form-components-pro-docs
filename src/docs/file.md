# File element

There's a dedicated Vue component that you can use to select files. This component is based mainly on the `Input` component, but provides additional logic to display the filename of the selected file.

```html
<File name="avatar" />
```

The component supports selecting multiple files as well by adding the `multiple` attribute.

```html
<File name="documents" multiple />
```