# Add Code Block to Blog Post

Use this skill when the user asks to add code snippets to a distill blog post.

## Options

### 1. Standard Markdown (Recommended)

Use triple backticks with language identifier:

~~~markdown
```python
def foo(x):
    return x * 2
```
~~~

Supported languages: `python`, `javascript`, `typescript`, `bash`, `json`, `html`, `css`, `rust`, `go`, `java`, `c`, `cpp`, and more.

### 2. Jekyll Highlight Tag

Use the `{% highlight %}` liquid tag for better dark mode support:

```liquid
{% highlight javascript %}
var x = 25;
function square(x) {
  return x * x;
}
{% endhighlight %}
```

### 3. Distill `<d-code>` Tag

For inline code with syntax highlighting:

```html
<d-code language="html">let x = 10;</d-code>
```

For block code:

```html
<d-code block language="javascript">
var x = 25;
function(x) {
  return x * x;
}
</d-code>
```

**Note:** `<d-code>` blocks may not render well in dark mode. Prefer markdown or Jekyll highlight tags.

## Recommendations

| Use Case | Recommended Method |
|----------|-------------------|
| Most code blocks | Standard markdown (triple backticks) |
| Dark mode support needed | Jekyll `{% highlight %}` tag |
| Inline code with highlighting | `<d-code language="...">` |
| Simple inline code | Backticks: `` `code` `` |

## Example

~~~markdown
Here's a Python function:

```python
def greet(name):
    """Return a greeting message."""
    return f"Hello, {name}!"
```

Or using Jekyll for better dark mode:

{% highlight python %}
def greet(name):
    return f"Hello, {name}!"
{% endhighlight %}
~~~
