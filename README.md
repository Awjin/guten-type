# Just Type

A sass mixin that generates correct typography, so you can just type.

## Who is this for?

For the hacker/blogger who wants to get a writing-driven site online as quickly as possible. (Perhaps you have a Jekyll-backed site hosted on Github pages.) This mixin allows you to configure as much or as little as you want, with sane defaults. It provides a solid foundation based on typographic principles so your content will shine.

## Structure

```
(1) just-type.scss

lib/
  (2) normalize.scss
  (3) scale-functions.scss
  (4) style.scss
```

  1. Imports files contained in `lib/`. This is where all configurations are set.
  1. [Normalize.css v6.0.0](https://necolas.github.io/normalize.css/6.0.0/normalize.css). Included by default, remove if unneeded.
  1. Given a starting size and a scale ratio, calculates the font-size and margin of `h4`, `h3`, `h2`, and `h1`. Keeping the sizes of these elements proportional is important for typographic rhythm.
  1. Eponymous.

## Usage

`./watch` starts a `sass --watch` session, outputting to `just-type.css`. If you need more control, modify `watch` or compile `just-type.scss` manually.
