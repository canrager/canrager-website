# Add Footnote to Blog Post

Use this skill when the user asks to add a footnote to a distill blog post.

## Syntax

Use the `<d-footnote>` tag to wrap the footnote content:

```html
Main text with a footnote reference.<d-footnote>This is the footnote content that appears on hover.</d-footnote>
```

## Behavior

- The footnote number is automatically generated
- On desktop: footnote content appears on hover
- On mobile: footnote content appears on tap
- Footnotes are numbered sequentially throughout the post

## Example

```markdown
The experiment showed significant results<d-footnote>p < 0.05, n = 150 participants across three trials.</d-footnote> that supported our hypothesis.
```

## Notes

- Keep footnotes concise - they're meant for brief clarifications
- For longer notes or references, consider using sidenotes instead
- Footnotes can contain basic HTML formatting
- Math can be included in footnotes: `<d-footnote>Where $ x = 5 $</d-footnote>`
