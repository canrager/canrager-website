# Add Equation to Blog Post

Use this skill when the user asks to add a math equation to a distill blog post.

## MathJax 3 Syntax

This template uses MathJax 3 for rendering equations.

### Inline Equations

Surround math with single `$` signs:

```markdown
The famous equation $ E = mc^2 $ relates energy and mass.
```

Renders as: The famous equation $ E = mc^2 $ relates energy and mass.

### Display Equations

Use `$$` on separate lines for centered, larger equations:

```markdown
$$
\left( \sum_{k=1}^n a_k b_k \right)^2 \leq \left( \sum_{k=1}^n a_k^2 \right) \left( \sum_{k=1}^n b_k^2 \right)
$$
```

## Common LaTeX Commands

| Command | Result | Example |
|---------|--------|---------|
| `\frac{a}{b}` | Fraction | $\frac{a}{b}$ |
| `x^2` | Superscript | $x^2$ |
| `x_i` | Subscript | $x_i$ |
| `\sqrt{x}` | Square root | $\sqrt{x}$ |
| `\sum_{i=1}^n` | Summation | $\sum_{i=1}^n$ |
| `\int_a^b` | Integral | $\int_a^b$ |
| `\partial` | Partial derivative | $\partial$ |
| `\nabla` | Gradient | $\nabla$ |
| `\alpha, \beta, \gamma` | Greek letters | $\alpha, \beta, \gamma$ |
| `\mathbf{x}` | Bold vector | $\mathbf{x}$ |
| `\hat{x}` | Hat notation | $\hat{x}$ |
| `\bar{x}` | Bar notation | $\bar{x}$ |
| `\left( \right)` | Auto-sized brackets | $\left( \frac{a}{b} \right)$ |

## Examples

### Matrix
```latex
$$
\begin{bmatrix}
a & b \\
c & d
\end{bmatrix}
$$
```

### Aligned equations
```latex
$$
\begin{aligned}
f(x) &= x^2 + 2x + 1 \\
     &= (x + 1)^2
\end{aligned}
$$
```

### Cases (piecewise functions)
```latex
$$
f(x) = \begin{cases}
x^2 & \text{if } x \geq 0 \\
-x^2 & \text{if } x < 0
\end{cases}
$$
```

## Notes

- MathJax 3 loads and renders much faster than MathJax 2
- No special front matter is needed - equations work by default
- Use `\text{}` for text within equations
