# GutenType

**[See the demo](https://awjin.me/guten-type).**

GutenType is a Sass library that creates correct typography.

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
  @include guten-type.press;
}
```
