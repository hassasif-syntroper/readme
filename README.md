# Syntroper Diagram Test Suite

This repo tests all supported diagram types and engines.

---

<!-- MERMAID: Flowchart -->
## 1. Mermaid - Flowchart

```mermaid
graph TD
  A[User] --> B[GitHub Action]
  B --> C[Scan Markdown]
  C --> D[Canonicalize]
  D --> E[Hash]
  E --> F[Upload to Syntroper API]
  F --> G[Rewrite README]
  G --> H[Commit and Push]
```

---

<!-- MERMAID: Sequence -->
## 2. Mermaid - Sequence Diagram

```mermaid
sequenceDiagram
    User->>GitHub: Push commit
    GitHub->>Action: Trigger workflow
    Action->>Syntroper: Upload diagram source
    Syntroper-->>Action: Return image URL
    Action->>README: Rewrite with image
    Action->>Git: Commit and push
```

---

<!-- MERMAID: Class Diagram -->
## 3. Mermaid - Class Diagram

```mermaid
classDiagram
    class DiagramAction {
        +scan()
        +canonicalize()
        +hash()
        +upload()
        +rewrite()
    }
    class SyntroperAPI {
        +importDiagram()
        +getImageUrl()
    }
    DiagramAction --> SyntroperAPI : calls
```

---

<!-- PLANTUML: Sequence -->
## 4. PlantUML - Sequence Diagram

```plantuml
@startuml
Alice -> GitHub : Push commit
GitHub -> Action : Trigger workflow
Action -> Syntroper : Upload diagram
Syntroper --> Action : Return image URL
Action -> README : Rewrite with image
@enduml
```

---

<!-- PLANTUML puml alias -->
## 5. PlantUML puml - Use Case Diagram

```puml
@startuml
left to right direction
actor User
actor Developer
rectangle Syntroper {
    usecase UC1 as "Push Code"
    usecase UC2 as "Scan Diagrams"
    usecase UC3 as "Render Image"
    usecase UC4 as "View README"
}
User --> UC4
Developer --> UC1
UC1 --> UC2
UC2 --> UC3
UC3 --> UC4
@enduml
```

---

<!-- DITAA -->
## 6. Ditaa - Simple Architecture

```ditaa
+--------+   +--------+   +--------+
| Client |-->| Server |-->|   DB   |
+--------+   +--------+   +--------+
```

---

<!-- ASCII -->
## 7. ASCII - Architecture Overview

```ascii
+------------------+   +------------------+   +------------------+
|   Developer      |   |  GitHub Action    |   |  Syntroper API   |
|                  |   |                  |   |                  |
|  Push commit     +-->+  Scan and Hash   +-->+  Render diagram  |
|                  |   |                  |   |                  |
|                  |   |  Rewrite README  +<--+  Return image    |
+------------------+   +------------------+   +------------------+
```

---

## Footer (Push 4 - verify API receives hashes)

All 7 diagram blocks cover:
- Engines: mermaid, plantuml, puml, ditaa, ascii
- Types: flowchart, sequence, class, use case, ditaa, ASCII art
