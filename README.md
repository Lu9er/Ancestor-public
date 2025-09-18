# Ancestor Lab – Source Quality Verification API (Demo)

Ancestor Lab is building infrastructure to verify the quality of sources used in AI systems.  
This demo repository provides **documentation, sample endpoints, and usage examples** for our Source Quality Verification API. The production system includes additional features and proprietary scoring algorithms not shown here.

---

## Overview

Language models often cite sources that vary widely in credibility. Ancestor Lab develops APIs that evaluate source reliability by analyzing:

- **Authority** – credibility of the publisher or author  
- **Recency** – how up-to-date the content is  
- **Provenance** – ability to trace the information to original, verifiable data  

This produces a **trust score (0–100)**, giving developers an auditable signal for filtering or ranking citations.

---

## Example API (Mock)

**Endpoint**  
`POST /verify-source`

**Sample Request**
```json
{
  "url": "https://examplejournal.org/article123",
  "metadata": {
    "title": "AI Policy Framework",
    "date": "2023-05-14"
  }
}
```

**Sample Response**
```json
{
  "url": "https://examplejournal.org/article123",
  "trust_score": 82,
  "factors": {
    "authority": 90,
    "recency": 75,
    "provenance": 80
  },
  "explanation": "Published in a peer-reviewed journal within the last 2 years."
}
```

---

## SDK Usage (Demo)

**Python**
```python
from ancestor_demo import verify_source

score = verify_source("https://examplejournal.org/article123")
print(score.trust_score)  # 82
```

**JavaScript**
```javascript
import { verifySource } from "ancestor-demo";

const score = await verifySource("https://examplejournal.org/article123");
console.log(score.trust_score); // 82
```

---

## Applications

- **AI Assistants** – Filter or rank sources in LLM outputs  
- **Research Platforms** – Improve citation quality and transparency  
- **Compliance Tools** – Provide audit trails for regulatory reporting  

---

## Disclaimer

This repository is for demonstration purposes only.  
It does not include Ancestor Lab’s production algorithms or infrastructure.  
For collaboration or access requests, contact: **contact@ancestor.cloud**  

---
