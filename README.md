# ABAC-Policy
ABAC Policy 
| Aspect | Cross-Validation | Universal Cross-Validation |
|------|------------------|----------------------------|
| Input to algorithm | Training log only | Training log + all possible requests (U×P) |
| Evaluation set | Testing log only | Testing log + sampled unseen requests |
| Requests outside the log | Ignored | Explicitly evaluated |
| Detects overly permissive rules | ❌ No | ✅ Yes |
| Precision evaluation | Weak / implicit | Explicit |
| Suitability for sparse logs | Poor | High |
| Metrics used | TPR, FPR (sometimes F1) | TPR, FPR, Precision, F1 |
| Generalization quality | Limited | Strong |
| Security awareness | Low | High |
התחלה
# ABAC-Policy
Article2-Paragraph for Article 2
%% תרשים ראשון – Mining Frequent Rules
```mermaid
 flowchart TD
    subgraph FrequentRules
        A1([Start]) --> B1[Input logs & attributes<br/>Observed allow/deny requests<br/>Parameters T/K]
        B1 --> C1[Mine frequent rules<br/>Cover >= T requests<br/>FreqRules]
        C1 --> D1[Filter by reliability<br/>Remove over permissive rules<br/>RelRules]
        D1 --> E1[Minimality step<br/>Keep shortest equivalent rules<br/>ShortRules]
        E1 --> F1([End])
    end

```
# ABAC-Policy
Article3-ABAC policy mining method based on hierarchical clustering and relationship extraction
```mermaid
flowchart TD
    subgraph ABACMining [ABAC Policy Mining]
        A2[קלט: Access control logs + Attribute values] --> B2[Data Preprocessing]
        B2 --> C2[Matrix & nTreeClus Representation]
        C2 --> D2[Hierarchical Clustering]
        D2 --> E2[Parameter Tuning]
        E2 --> F2[Policy Extraction]
        F2 --> G2[Policy Optimization]
        G2 --> H2[Output: Optimized ABAC policy set + Conflict status]
    end
```
# Article 4 - Text for article 4
