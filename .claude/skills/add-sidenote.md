# Add Sidenote to Blog Post

Use this skill when the user asks to add a sidenote (margin note) to a distill blog post.

## Options

There are two ways to create sidenotes with different styling:

### 1. Using `<aside>` Tag (Distill Style)

```html
<aside>
  <p>This is a sidenote in the margin.</p>
</aside>
```

Can include images:

```liquid
<aside>
  {% include figure.liquid loading="eager" path="assets/img/photo.png" class="img-fluid rounded z-depth-1" zoomable=true %}
  <p>Caption for the margin image.</p>
</aside>
```

### 2. Using `l-gutter` Class (al-folio Style)

```html
<div class="l-gutter">
  <p>This is a sidenote using l-gutter class.</p>
</div>
```

## Examples

### Simple Text Sidenote

```html
The main text discusses the concept in detail.

<aside>
  <p>Additional context that doesn't interrupt the main flow.</p>
</aside>
```

### Sidenote with Math and Link

```html
In physics, the relationship between mass and energy is fundamental.

<aside>
  <p>This principle is defined by Einstein's famous equation: $E = mc^2$
  <a href="https://en.wikipedia.org/wiki/Mass%E2%80%93energy_equivalence" target="_blank">(Source)</a></p>
</aside>
```

### Sidenote with Image

```liquid
The original illustration shows remarkable detail.

<aside>
  {% include figure.liquid loading="eager" path="assets/img/illustration.png" class="img-fluid rounded z-depth-1" zoomable=true %}
  <p>Historical illustration from 1515.</p>
</aside>
```

## Behavior

- **Desktop**: Sidenotes appear in the margin alongside the main text
- **Mobile**: Sidenotes appear inline within the text flow
- Sidenotes don't interrupt the reading flow of `.l-body` content on desktop

## When to Use

| Content Type | Recommended |
|--------------|-------------|
| Brief clarification | `<aside>` |
| Source attribution | `<aside>` |
| Related image | `<aside>` with figure |
| Extended note | `<div class="l-gutter">` |
| Mathematical note | `<aside>` with math |

## Sidenotes vs Footnotes

| Feature | Sidenote | Footnote |
|---------|----------|----------|
| Location | Margin | Hover/inline |
| Visibility | Always visible | On interaction |
| Length | Can be longer | Should be brief |
| Images | Supported | Not recommended |
| Use case | Context, images | Quick clarifications |

## Notes

- Place the `<aside>` tag near the relevant text
- Keep sidenotes concise for better readability
- Use `zoomable=true` on images for click-to-zoom functionality
- Both methods support HTML, math, and links
