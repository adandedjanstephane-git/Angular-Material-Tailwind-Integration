# Angular Material's system variables and Tailwind utility classes merger

**A stable, themeable set of CSS custom properties mapping Material Design System tokens to Tailwind CSS utility classes.**

## Overview

This project provides a project-scoped mapping of Material Design CSS variables (`--mat-sys-*`) to custom property namespaces compatible with Tailwind CSS v4 utilities. It allows you to use Material tokens in your HTML via Tailwind utility classes, **without** the need for square bracket syntax.

## Why?

- **Seamless theming:** Override Material tokens globally or per scope for easy theme changes.
- **Tailwind-friendly:** Use variables in utility classes like `bg-mat-primary-container` or `text-mat-on-surface`.
- **Maintainability:** Components consume tokens, not hardcoded values, for maximum flexibility.

## Variable Namespaces

Tailwind v4 supports the following variable namespaces for utility classes:

| Namespace            | Utility Example                |
|----------------------|-------------------------------|
| `--color-*`          | `bg-red-500`, `text-sky-300`  |
| `--font-*`           | `font-sans`                   |
| `--text-*`           | `text-xl`                     |
| `--spacing-*`        | `px-4`, `max-h-16`            |
| `--radius-*`         | `rounded-sm`                  |
| ...                  | ...                           |

(See [Tailwind docs](https://tailwindcss.com/docs/adding-custom-styles#using-css-variables-in-tailwind-classes) for more.)

## Mapping Structure

Each custom variable maps to a Material Design token:

```css
--color-mat-primary: var(--mat-sys-primary);
--color-mat-on-surface: var(--mat-sys-on-surface);
```

## Usage

In your HTML (with Tailwind):

```html
<div class="text-mat-on-surface bg-mat-primary-container">
  Hello World
</div>
```

## Theming & Scoping

To change a theme value globally:

```css
:root {
  --mat-sys-primary: #6200ee;
}
```

To override for a specific scope:

```css
.my-scope {
  --mat-primary: #6200ee;
}
```

Switch themes by applying a class to `<body>` or a container:

```css
.theme-dark {
  --mat-sys-primary: #333;
  /* ... */
}
```

## Accessibility

- **Always use** `mat-on-*` variables for text/icons to ensure proper contrast.
- **Never hardcode** color values in components—consume tokens!

## Best Practices

- Keep variable mappings consistent.
- Use `:root` or theme classes for overrides.
- Use Tailwind utility classes for all styling.

## References

- [Tailwind Custom Styles](https://tailwindcss.com/docs/adding-custom-styles#using-css-variables-in-tailwind-classes)
- [Material Design Color Tokens](https://m3.material.io/styles/color/the-color-system/tokens)
- [Angular Material System Variables](https://material.angular.dev/guide/system-variables)
---

> This file acts as an indirection layer; keep mappings stable for reliable theming.

