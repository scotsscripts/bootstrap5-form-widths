# Bootstrap 5 Form Width Utilities

A tiny CSS add-on for Bootstrap 5 that sets form field widths on the familiar 12-column scale, as stacked (block) or side-by-side (inline) fields.

- About 1 KB minified, no JavaScript
- Mobile-first: widths apply at 576px and up; below that, fields stay full width
- Works on inputs, selects, textareas, or wrapper `div`s (so labels move with their fields)
- Adjustable with CSS custom properties

## Installation

Download `bs5-form-widths.css` (or the `.min.css`) and load it **after** Bootstrap:

```html
<link href="https://cdn.jsdelivr.net/npm/bootstrap@5.3.9/dist/css/bootstrap.min.css" rel="stylesheet">
<link href="bs5-form-widths.min.css" rel="stylesheet">
```

Or load it from GitHub through jsDelivr:

```html
<link href="https://cdn.jsdelivr.net/gh/scotsscripts/bootstrap5-form-widths@v2.0.0/bs5-form-widths.min.css" rel="stylesheet">
```

## Usage

### Block widths

Each field stacks on its own line. Use `form-sm-1` through `form-sm-12`.

```html
<input class="form-control form-sm-4">
<select class="form-select form-sm-6">...</select>
```

### Inline widths

Fields sit side by side. Use `form-sm-1-inline` through `form-sm-12-inline`, inside a `d-flex flex-wrap` wrapper:

```html
<div class="d-flex flex-wrap">
  <input class="form-control form-sm-6-inline">
  <input class="form-control form-sm-3-inline">
  <input class="form-control form-sm-3-inline">
</div>
```

The wrapper is recommended. Without it, browsers add a small whitespace gap between inline-block elements, so a row that adds up to 12 can wrap onto a second line.

### Labels with fields

Put the class on a wrapper `div` so the label and field move together:

```html
<div class="d-flex flex-wrap">
  <div class="form-sm-8-inline">
    <label class="form-label" for="city">City</label>
    <input class="form-control" id="city">
  </div>
  <div class="form-sm-4-inline">
    <label class="form-label" for="zip">ZIP</label>
    <input class="form-control" id="zip">
  </div>
</div>
```

## Customizing

| Variable | Default | What it does |
|---|---|---|
| `--form-sm-gap` | `0.5rem` | Space to the right of each inline field |
| `--form-sm-w` | set by each class | The field's width |

Change the gap everywhere:

```css
:root { --form-sm-gap: 1rem; }
```

Or for one group of fields:

```html
<div class="d-flex flex-wrap" style="--form-sm-gap: 1.5rem">...</div>
```

One-off custom width (add it alongside any `form-sm` class):

```html
<input class="form-control form-sm-12" style="--form-sm-w: 30%">
```

## Demo

Open `demo.html` (keep it in the same folder as the CSS file) to see every option, including the mobile fallback when you resize the window.

## Browser support

All current browsers. Uses CSS custom properties and `:is()`, supported in Chrome, Edge, Firefox and Safari since 2021.

## License

MIT. See [LICENSE](LICENSE).

Made by [Scot's Scripts](https://www.scotsscripts.com).
