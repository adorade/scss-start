# Scss Start Architecture

## Example Project

```sh
sass/
   |
   | ### No output a single line of CSS when compile
   |– core/
   |   |– _index.scss        # Core All-In-One
   |   |– _functions.scss    # Sass Functions
   |   |– _colors.scss       # Color Variables
   |   |– _variables.scss    # Sass Variables
   |   |– _maps.scss         # Sass Maps
   |   |– _placeholders.scss # placeholders helpers
   |   ...                   # Etc.
   |
   |– mixins/
   |   |– _index.scss        # Sass Mixins All-In-One
   |   |– _grid.scss         # Grid
   |   |– _buttons.scss      # Buttons
   |   |– _pictures.scss     # Pictures
   |   ...                   # Etc.
   |
   | ### Output of CSS when compile
   |– vendors/
   |   |– _index.scss        # Vendors All-In-One
   |   |– _normalize.scss    # normalize.css
   |   ...                   # Etc.
   |
   |– base/
   |   |– _index.scss        # Base All-In-One
   |   |– _root.scss         # CSS Variables
   |   |– _reset.scss        # Reset/normalize
   |   |– _fonts.scss        # Fonts
   |   |– _helpers.scss      # Class helpers
   |   |– _typography.scss   # Typography rules
   |   |– _base.scss         # Base rules
   |   ...                   # Etc.
   |
   |– layout/
   |   |– _index.scss        # Layout All-In-One
   |   |– _grid.scss         # Grid system
   |   |– _header.scss       # Header
   |   |– _footer.scss       # Footer
   |   |– _sidebar.scss      # Sidebar
   |   |– _navigation.scss   # Navigation
   |   |– _forms.scss        # Forms
   |   ...                   # Etc.
   |
   |– components/
   |   |– _index.scss        # Components All-In-One
   |   |– _buttons.scss      # Buttons
   |   |– _carousel.scss     # Carousel
   |   |– _cover.scss        # Cover
   |   |– _dropdown.scss     # Dropdown
   |   |– _media.scss        # Media, images, pictures
   |   ...                   # Etc.
   |
   | ### Optional
   |– pages/
   |   |– _index.scss        # Pages All-In-One
   |   |– _home.scss         # Home specific styles
   |   |– _contact.scss      # Contact specific styles
   |   ...                   # Etc.
   |
   |– themes/
   |   |– _index.scss        # Themes All-In-One
   |   |– _theme.scss        # Default theme
   |   |– _admin.scss        # Admin theme
   |   ...                   # Etc.
   |
   – main.scss               # Main Sass file
```

## Main file

The main file (usually labelled `main.scss`) should be the only sass file from the whole code base not to begin with an underscore. This file should not contain anything but `@import` or/and `@forward` and comments.

Files should be imported according to the folder they live in, one after the other in the following order:

- `core/`
- `mixins/`
- `vendors/`
- `base/`
- `layout/`
- `components/`
- `pages/`
- `themes/`

In order to preserve readability, the main file should respect these guidelines:

- one file per `@use` or `@forward`;
- one `@import` or `@forward` per line;
- no new line between two imports from the same folder;
- a new line after the last import from a folder;
- file extensions and leading underscores omitted.

We have to use `@use` and `@forward`, which are modern methods of importing files and folders in Sass.

```scss
// _index.scss
@forward 'functions';
@forward 'colors';
@forward 'variables';

// main.scss
@use 'core';
@use 'mixins';
@use 'vendors';
@use 'base';
@use 'layout';
@use 'components';
@use 'pages';
@use 'themes';
```
