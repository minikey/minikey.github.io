---
layout: default
title: 低版本IE模拟compareDocumentPosition
---

```javascript
function comparePosition(a, b) {
    return a.compareDocumentPosition ?
        a.compareDocumentPosition(b) :
        a.contains ?
        (a != b && a.contains(b) && 16) +
        (a != b && b.contains(a) && 8) +
        (a.sourceIndex >= 0 && b.sourceIndex >= 0 ?
            (a.sourceIndex < b.sourceIndex && 4) +
            (a.sourceIndex > b.sourceIndex && 2) :
            1) :
        0;
}
```
