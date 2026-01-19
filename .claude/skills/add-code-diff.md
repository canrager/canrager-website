# Add Code Diff to Blog Post

Use this skill when the user asks to show code changes (diffs) in a distill blog post using Diff2Html.

## Front Matter Required

Enable code_diff in the post's front matter:

```yaml
code_diff: true
```

## Syntax

Use a fenced code block with `diff2html` language identifier:

~~~markdown
```diff2html
diff --git a/file.js b/file.js
index abc123..def456 100644
--- a/file.js
+++ b/file.js
@@ -1,5 +1,6 @@
-// Old comment
+// New comment
 function example() {
-    return 1;
+    const result = 2;
+    return result;
 }
```
~~~

## Format

The diff follows standard unified diff format:

- `---` marks the old file
- `+++` marks the new file
- `@@` shows line numbers (old start, count, new start, count)
- `-` prefix for removed lines
- `+` prefix for added lines
- Space prefix for unchanged context lines

## Multi-File Diff

Show changes across multiple files in one block:

~~~markdown
```diff2html
diff --git a/utils.js b/utils.js
index 3b5f3d1..c7f9b2e 100644
--- a/utils.js
+++ b/utils.js
@@ -1,4 +1,4 @@
-export function oldName(x) {
+export function newName(x) {
     return x * 2;
 }

diff --git a/main.js b/main.js
index 5f6a9c3..b7d4e8f 100644
--- a/main.js
+++ b/main.js
@@ -1,3 +1,3 @@
-import { oldName } from './utils';
+import { newName } from './utils';

-console.log(oldName(5));
+console.log(newName(5));
```
~~~

## Example

~~~markdown
Here's how we refactored the calculation:

```diff2html
diff --git a/math.py b/math.py
--- a/math.py
+++ b/math.py
@@ -1,5 +1,8 @@
-def calculate(x):
-    return x * 3.14159
+import math
+
+def calculate_area(radius):
+    """Calculate circle area with proper PI."""
+    return math.pi * radius ** 2
```
~~~

## Use Cases

- Showing code refactoring steps
- Tutorial step-by-step changes
- Code review explanations
- Before/after comparisons
- Bug fix demonstrations

## Notes

- The diff is rendered with syntax highlighting for additions (green) and deletions (red)
- Works best with actual git diff output format
- For simple changes, you can simplify the header lines
