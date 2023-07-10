# GutenType

**[See the demo](https://awjin.me/guten-type)**

GutenType is a Sass library that creates correct typography. Give it base values
like `font-size`, and it automatically generates styles for you.

## Usage

```scss
@use "guten-type";

article {
  @include guten-type.press();
}
```

## Customization

```scss
@use "guten-type";

article {
  @include guten-type.set(
    $font-size: 20px,
    $font-stack: (
      "serif": (
        Baskerville,
      ),
      "sans": (
        Helvetica,
      ),
      "mono": (
        Consolas,
      ),
    )
  );

  @include guten-type.press();
}
```

### `$font-size`

- The body text's font-size. Must be in px. This is automatically scaled smaller for elements like captions, code, etc.

- Default: `18px`

### `$font-stack`

- The various serif, sans-serif, and monospace fonts used for all text.

- Default:

  ```scss
  (
    "serif": (
      "Iowan Old Style",
      "Palatino Linotype",
      "URW Palladio L",
      P052,
      serif,
    ),

    "sans": (
      Inter,
      Roboto,
      "Helvetica Neue",
      "Arial Nova",
      "Nimbus Sans",
      Arial,
      sans-serif,
    ),

    "mono": (
      ui-monospace,
      "Cascadia Code",
      "Source Code Pro",
      Menlo,
      Consolas,
      "DejaVu Sans Mono",
      monospace,
    )
  )
  ```

### `$line-height`

- The body text's line-height. This is automatically scaled smaller for headings.

- Default: `1.5`

### `$color`

- `normal` is used for text. `light` is used for lines (tables, hr, etc.). `action` is used for links.

- Default:

  ```scss
  (
    "normal": rgba(1, 2, 3, 0.95),
    "light": rgba(0, 0, 0, 0.55),
    "action": rgba(1, 2, 3, 0.95),
  )
  ```

### `$whitespace`

- The size of line breaks. Must be in rem.

- Default: `1rem * $line-height`

### `$font-size-scale`

- The typographic scale for heading font-size.

  Given `start` == 4, the scale starts at h4. h4's font-size gets calculated
  as follows:

  h4 font-size = `$font-size` \* `base`.

  Then, the remaining headings scale exponentially:

  h3 font-size = h4 font-size \* `ratio`^1
  h2 font-size = h4 font-size \* `ratio`^2
  h1 font-size = h4 font-size \* `ratio`^3

* Default:

  ```scss
  (
    "start": 4,
    "base": 1.33333,
    "ratio": 1.25,
  )
  ```

### `$whitespace-scale`

- Same concept as $font-size-scale.

- Default:

  ```scss
  (
    "start": 4,
    "base": 1.5,
    "ratio": 1.33333,
  )
  ```
