# Mixins

The `_mixins` folder allow you to define styles that can be re-used throughout your stylesheet. They make it easy to avoid using non-semantic classes like `.float-left`, and to distribute collections of styles in libraries.

The rule of thumb for this folder is that it **should not output a single line of CSS when compiled on its own**. These are nothing but Sass helpers.

- `_index.scss`
- `_buttons.scss`
- `_grid.scss`
- `_pictures.scss`
