# Add Mermaid Diagram to Blog Post

Use this skill when the user asks to add a diagram (flowchart, sequence diagram, class diagram, Gantt chart, etc.) to a distill blog post.

## Front Matter Required

Enable Mermaid in the post's front matter:

```yaml
mermaid:
  enabled: true
  zoomable: true  # optional: allows zoom on click
```

## Syntax

Use a fenced code block with `mermaid` language identifier:

~~~markdown
```mermaid
graph TD
    A[Start] --> B[Process]
    B --> C[End]
```
~~~

## Diagram Types

### Flowchart

```mermaid
graph TD
    A[Start] --> B{Decision}
    B -->|Yes| C[Action 1]
    B -->|No| D[Action 2]
    C --> E[End]
    D --> E
```

Direction options: `TD` (top-down), `LR` (left-right), `BT` (bottom-top), `RL` (right-left)

### Sequence Diagram

```mermaid
sequenceDiagram
    participant A as Alice
    participant B as Bob
    A->>B: Hello Bob
    B-->>A: Hi Alice
    A->>B: How are you?
```

### Class Diagram

```mermaid
classDiagram
    class Animal {
        +String species
        +int age
        +makeSound()
    }
    class Dog {
        +String breed
        +bark()
    }
    Animal <|-- Dog
```

### Gantt Chart

```mermaid
gantt
    dateFormat  YYYY-MM-DD
    title Project Timeline

    section Phase 1
    Task A           :a1, 2025-01-01, 30d
    Task B           :after a1, 20d

    section Phase 2
    Task C           :2025-02-01, 15d
```

### State Diagram

```mermaid
stateDiagram-v2
    [*] --> Idle
    Idle --> Processing: start
    Processing --> Done: complete
    Processing --> Error: fail
    Error --> Idle: reset
    Done --> [*]
```

## Styling

Add custom styles within the diagram:

```mermaid
graph TD
    A[Start]:::green --> B[End]:::red
    classDef green fill:#9f6,stroke:#333
    classDef red fill:#f66,stroke:#333
```

## Example in Post

~~~markdown
The system architecture is shown below:

```mermaid
graph LR
    Client --> API
    API --> Database
    API --> Cache
    Cache --> Database
```
~~~

## Notes

- Diagrams are rendered client-side using Mermaid.js
- Keep diagrams simple for readability
- Use descriptive labels for nodes
- Test complex diagrams in the [Mermaid Live Editor](https://mermaid.live/)
