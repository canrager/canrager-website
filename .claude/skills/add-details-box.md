# Add Details Box to Blog Post

Use this skill when the user asks to add a collapsible/expandable details box to a distill blog post.

## Syntax

Use the Jekyll `{% details %}` liquid tag:

```liquid
{% details Click here to know more %}
Additional details that are hidden by default.

You can include:
- Math: $ 2x - 1 $
- Code: `inline code`
- Lists and other markdown
{% enddetails %}
```

## Example

```liquid
{% details Show implementation details %}
The algorithm works as follows:

1. Initialize the counter to zero
2. Iterate through each element
3. Apply the transformation $ f(x) = x^2 $

```python
for item in items:
    result = transform(item)
```
{% enddetails %}
```

## Behavior

- Renders as a clickable header that expands/collapses content
- Content is hidden by default
- Supports markdown, math, and code inside
- Useful for supplementary information that doesn't need to be shown by default

## Use Cases

- Implementation details
- Proofs or derivations
- Extended examples
- Troubleshooting information
- Optional deep-dives
