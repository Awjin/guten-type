# GutenType

### [See the demo](https://awjin.me/guten-type)

### [Install via npm](https://npmjs.org/guten-type)

GutenType is a Sass library that creates correct typography. Give it base values
like `font-size`, and it automatically generates styles for you.

## `press()`

The `press()` mixin assigns a base font-size to the html element, so that all
other styles can be derived from 1rem. Then, it generates the typography system.

```scss
@use 'guten-type';

main {
  @include guten-type.press();
}
```

## `set()`

The `set()` mixin allows you to customize the default styles.

```scss
@use 'guten-type';

main {
  /* STEP 1 (optional): Configure the module. */
  @include guten-type.set(
    $line-height: 1.4,
    $font-size: 18px,
    $font-stack: (
      'heading': ('PT Serif', serif),
      'body': ('PT Sans', sans-serif),
      'mono': ('Roboto Mono', monospace),
    ),
  );

  /* STEP 2: Use the module. */
  @include guten-type.press();
}
```

These are the options you can pass to `set()`:

#### `$font-size`

- The body text's font-size. Must be in px.

- Default: `16px`

#### `$responsive-breakpoint`

- The min breakpoint at which font-size will switch from static to responsive
units (i.e. the font-size increases along with the viewport size, therefore
supporting infinitely large viewports). Must be in px.

- Default: `-1px` (negative values are ignored)

#### `$line-height`

- The body text's line-height.

- Default: `1.5`

#### `$whitespace`

- The size of line breaks. Must be in rem.

- Default: `1rem * $line-height`

#### `$font-size-scale`

- The typographic scale for heading font-size.

- `start` is the heading at which the scale starts. Since h5 and h6 are less
common than h1 - h4, defaults to h4.

- Assuming h4 is the `start`:
  - h4 font-size = body font-size * `base`.

- Then, the remaining headings scale exponentially:
  - h3 font-size = h4 font-size * `ratio`^1
  - h2 font-size = h4 font-size * `ratio`^2
  - h1 font-size = h4 font-size * `ratio`^3

- Default:
  ```scss
  (
    'start': 4,
    'base': 1.33333,
    'ratio': 1.25,
  )
  ```

#### `$whitespace-scale`

- Same concept as $font-size-scale.

- Default:
  ```scss
  (
    'start': 4,
    'base': 1.5,
    'ratio': 1.33333,
  )
  ```

#### `$font-stack`

- The font-stack for headings, body text, and monospaced text.

- Default:
  ```scss
  (
    'heading': (sans-serif,),
    'body': (Georgia, serif),
    'mono': ('Andale Mono', 'Lucida Console', monospace),
  )
  ```

#### `$color`

- The text colors. `normal` is used for the body and headings. `light` is used
selectively for auxiliary text, like captions. `action` is used for links.

- Default:
  ```scss
  (
    'normal': rgba(0, 0, 0, 0.95),
    'light': rgba(0, 0, 0, 0.6),
    'action': rgba(10, 30, 220, 0.95),
  )
  ```

#### `$border`

- The appearance of items that have a border: table, pre, hr, and blockquote.

- Default:
  ```scss
  (
    'weight': 2px,
    'color': color('light'),
  )
  ```
