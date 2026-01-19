# Use Layouts in Blog Post

Use this skill when the user asks to control the width of content (images, figures, iframes) in a distill blog post.

## Layout Classes

Distill provides CSS classes to control content width:

| Class | Width | Use Case |
|-------|-------|----------|
| `.l-body` | Standard text width | Default for text |
| `.l-body-outset` | Slightly wider than text | Small overflow |
| `.l-page` | Page width | Wider figures |
| `.l-page-outset` | Slightly wider than page | Emphasized content |
| `.l-screen` | Full browser width | Full-width content |
| `.l-screen-inset` | Full width with margins | Full-width with padding |
| `.l-gutter` | Margin/sidebar | Sidenotes, marginalia |

## Usage

Wrap content in a `<div>` with the layout class:

```html
<div class="l-page">
  <img src="path/to/image.jpg" alt="Description">
</div>
```

## Examples

### Standard Width Image

```html
<div class="l-body">
  {% include figure.liquid path="assets/img/photo.jpg" class="img-fluid" %}
</div>
```

### Wide Image (Page Width)

```html
<div class="l-page">
  {% include figure.liquid path="assets/img/panorama.jpg" class="img-fluid" %}
</div>
```

### Full Screen Image

```html
<div class="l-screen">
  <img src="{{ '/assets/img/hero.jpg' | relative_url }}" width="100%">
</div>
```

### Full Screen with Inset

```html
<div class="l-screen-inset">
  <iframe src="..." height="500px" width="100%"></iframe>
</div>
```

### Sidenote/Marginalia

```html
<div class="l-gutter">
  <p>This appears in the margin</p>
</div>
```

## With Figures

```liquid
<div class="l-page">
  {% include figure.liquid
     loading="eager"
     path="assets/img/diagram.png"
     class="img-fluid rounded z-depth-1"
     zoomable=true
  %}
</div>
```

## Visual Hierarchy

```
|                    Browser Window                    |
|                                                      |
|  |---------------- l-screen --------------------|    |
|  |   |---------- l-screen-inset ----------|     |    |
|  |   |   |------- l-page-outset ------|   |     |    |
|  |   |   |   |------ l-page ------|   |   |     |    |
|  |   |   |   | |- l-body-outset -||   |   |     |    |
|  |   |   |   | |  |-- l-body --|  |   |   |     |    |
|  |   |   |   | |  |   Text    |  |   |   |     |    |
```

## Notes

- Default content (no class) uses `.l-body` width
- Use wider layouts for data visualizations and images
- `.l-gutter` content appears in the margin on desktop, inline on mobile
- Combine with `img-fluid` class for responsive images
