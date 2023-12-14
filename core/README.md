# Core

The `core/` folder gathers all Sass tools and helpers used across the project. Every global variable, function and placeholder should be put in here.

The rule of thumb for this folder is that it **should not output a single line of CSS when compiled on its own**. These are nothing but Sass helpers.

- `_index.scss`
- `_functions.scss`
- `_colors.scss`
- `_variables.scss`
- `_maps.scss`
- `_placeholders.scss`

When working on a very large project with a lot of abstract utilities, it might be interesting to group them by topic rather than type, for instance typography (`_typography.scss`), theming (`_theming.scss`), etc. Each file contains all the related helpers: **variables, functions and placeholders**. Doing so can make the code easier to browse and maintain, especially when files are getting very long.

*NOTE: The folder might also be called `abstracts/`, `utilities/` or `helpers/`, depending on what you prefer.*
