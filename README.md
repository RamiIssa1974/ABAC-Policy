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
## another detailed chart
```mermaid
flowchart TD
    A[קלט: Access control logs + Attribute values] --> B[Data Preprocessing]
    B --> B1[שילוב log + attributes → LABAC]
    B --> B2[טיפול בערכים חסרים na]
    B --> B3[String splicing → יצירת attribute strings]

    B3 --> C[Matrix & nTreeClus Representation]
    C --> C1[חלוקה לתת-מחרוזות]
    C --> C2[בניית מטריצת תווים]
    C --> C3[Random Forest → leaf nodes]
    C --> C4[יצירת וקטורים שמייצגים security intent]

    C4 --> D[Hierarchical Clustering]
    D --> D1[חישוב cosine similarity בין וקטורים]
    D --> D2[יצירת distance matrix]
    D --> D3[Ward SSE → tree of clusters]
    D --> D4[חלוקה ל-k clusters]

    D4 --> E[Parameter Tuning]
    E --> E1[Segment length c]
    E --> E2[Number of decision trees m]
    E --> E3[Number of clusters k]
    E --> E4[Threshold η]

    E4 --> F[Policy Extraction]
    F --> F1[Entity & inter-attribute relationships]
    F --> F2[Operational attribute relationships לפי threshold]
    F --> F3[יצירת policy set π1]

    F3 --> G[Policy Optimization]
    G --> G1[Pruning: הסרת חוקים כפולים/מיותרים]
    G --> G2[Refinement: תיקון חוקים לפי FN/FP]
    G --> G3[Analysis: בדיקה מול מגבלות SMT → isConflict]

    G3 --> H[Output: Optimized ABAC policy set π + Conflict status]

```
# Article 4 - Text for article 4
