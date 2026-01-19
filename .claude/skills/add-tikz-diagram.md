# Add TikZ Diagram to Blog Post

Use this skill when the user asks to add a LaTeX/TikZ diagram (mathematical figures, circuit diagrams, graphs, etc.) to a distill blog post.

## Front Matter Required

Enable TikZJax in the post's front matter:

```yaml
tikzjax: true
```

## Syntax

Use a script tag with `type="text/tikz"`:

```html
<script type="text/tikz">
\begin{tikzpicture}
  % TikZ commands here
\end{tikzpicture}
</script>
```

## Examples

### Circle with Labels (Euler's Formula)

```html
<script type="text/tikz">
\begin{tikzpicture}
    \filldraw[fill=cyan!10, draw=blue, thick] (0,0) circle (2cm);

    \draw[->, thick] (-2.5,0) -- (2.5,0) node[right] {Re};
    \draw[->, thick] (0,-2.5) -- (0,2.5) node[above] {Im};

    \draw[->, thick, color=purple] (0,0) -- (1.5,1.5);
    \node[color=purple] at (1.1, 1.7) {$e^{i\theta}$};

    \draw[thick] (0.7,0) arc (0:45:0.7);
    \node at (0.9, 0.3) {$\theta$};

    \draw[dashed, color=gray] (1.5,1.5) -- (1.5,0) node[below, black] {$\cos \theta$};
    \draw[dashed, color=gray] (1.5,1.5) -- (0,1.5) node[left, black] {$\sin \theta$};
\end{tikzpicture}
</script>
```

### Simple Graph

```html
<script type="text/tikz">
\begin{tikzpicture}
    \node[circle, draw] (A) at (0,0) {A};
    \node[circle, draw] (B) at (2,0) {B};
    \node[circle, draw] (C) at (1,1.5) {C};

    \draw (A) -- (B);
    \draw (B) -- (C);
    \draw (C) -- (A);
\end{tikzpicture}
</script>
```

### Neural Network Layer

```html
<script type="text/tikz">
\begin{tikzpicture}
    \foreach \i in {1,2,3} {
        \node[circle, draw, minimum size=0.8cm] (input\i) at (0, -\i) {$x_\i$};
    }
    \foreach \i in {1,2} {
        \node[circle, draw, fill=blue!20, minimum size=0.8cm] (hidden\i) at (2.5, -\i - 0.5) {$h_\i$};
    }
    \node[circle, draw, fill=green!20, minimum size=0.8cm] (output) at (5, -2) {$y$};

    \foreach \i in {1,2,3} {
        \foreach \j in {1,2} {
            \draw[->] (input\i) -- (hidden\j);
        }
    }
    \foreach \i in {1,2} {
        \draw[->] (hidden\i) -- (output);
    }
\end{tikzpicture}
</script>
```

### Coordinate Axes with Function

```html
<script type="text/tikz">
\begin{tikzpicture}
    \draw[->] (-0.5,0) -- (4,0) node[right] {$x$};
    \draw[->] (0,-0.5) -- (0,3) node[above] {$y$};

    \draw[domain=0:3.5, smooth, variable=\x, blue, thick]
        plot ({\x}, {0.5*\x*\x/3});

    \node at (3, 1.5) {$f(x)$};
\end{tikzpicture}
</script>
```

## Common TikZ Commands

| Command | Description |
|---------|-------------|
| `\draw` | Draw lines, curves |
| `\fill` | Fill shapes |
| `\filldraw` | Draw and fill |
| `\node` | Place text/labels |
| `circle (r)` | Circle with radius r |
| `rectangle (x,y)` | Rectangle to point |
| `--` | Straight line |
| `->` | Arrow head |
| `[thick]` | Line thickness |
| `[dashed]` | Dashed line |
| `[color=red]` | Color |

## Notes

- Renders as vector graphics (SVG)
- Supports most standard TikZ commands
- Can include LaTeX math with `$...$`
- Great for porting diagrams from academic papers
- Test complex diagrams locally first
- Some advanced TikZ libraries may not be supported
