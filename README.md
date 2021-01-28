# JustType

*See the [demo and explanation](https://awjin.me/just-type).*

JustType is a Sass library that creates correct typography.

```scss
@use 'just-type';

main {
  /* STEP 1 (optional): Configure the module. */
  @include just-type.configure(
    $line-height: 1.4,
    $font-size: 18px,
    $font-stack: (
      'heading': ('PT Serif', serif),
      'body': ('PT Sans', sans-serif),
      'mono': ('Roboto Mono', monospace),
    ),
  );

  /* STEP 2: Use the module. */
  @include just-type.typography;
}
```

TODO: Add docs.
