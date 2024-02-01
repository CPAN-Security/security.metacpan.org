

```mermaid
---
title: 
---
stateDiagram-v2
    author_ecosystem: Author Ecosystem
    author: Author
    second: 

    author --> author_ecosystem
    state author_ecosystem {
        [*] --> second
        second --> [*]
    }
```
