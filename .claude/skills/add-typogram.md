# Add Typogram to Blog Post

Use this skill when the user asks to add an ASCII-art style diagram (typogram) to a distill blog post.

## Front Matter Required

Enable typograms in the post's front matter:

```yaml
typograms: true
```

## Syntax

Use a fenced code block with `typograms` language identifier:

~~~markdown
```typograms
+-------+
|  Box  |
+-------+
```
~~~

## Examples

### Simple Box

~~~markdown
```typograms
+------------------+
|                  |
|     Content      |
|                  |
+------------------+
```
~~~

### 3D Box

~~~markdown
```typograms
     ___________________
    /                  /|
   /__________________/ |
  |                  |  |
  |     Distill      |  |
  |                  |  |
  |                  | /
  |__________________|/
```
~~~

### Flowchart

~~~markdown
```typograms
+-------+     +--------+     +-------+
| Start | --> | Process| --> |  End  |
+-------+     +--------+     +-------+
```
~~~

### Tree Structure

~~~markdown
```typograms
       Root
       /  \
      /    \
   Left   Right
   / \      |
  A   B     C
```
~~~

### Simple Diagram with Arrows

~~~markdown
```typograms
   Input
     |
     v
  +------+
  | Func |
  +------+
     |
     v
  Output
```
~~~

### Architecture Diagram

~~~markdown
```typograms
+----------+    +----------+    +----------+
|  Client  |--->|   API    |--->| Database |
+----------+    +----------+    +----------+
                     |
                     v
               +----------+
               |  Cache   |
               +----------+
```
~~~

## Drawing Characters

| Character | Purpose |
|-----------|---------|
| `+` | Corner |
| `-` | Horizontal line |
| `|` | Vertical line |
| `/` `\` | Diagonal lines |
| `v` `^` `<` `>` | Arrows |
| `*` | Bullet point |
| `_` | Underline |

## Notes

- Typograms are rendered from ASCII art to clean vector graphics
- Great for quick diagrams without learning a diagram syntax
- Keep diagrams simple and use monospace alignment
- Works well for boxes, flowcharts, and simple structures
- For complex diagrams, consider Mermaid or TikZ instead
