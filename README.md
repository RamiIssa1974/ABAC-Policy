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
 ```mermaid
flowchart LR
    A([Start]) --> B[Input logs and attributes<br/>Observed allow and deny requests<br/>Parameters T and K]
    B --> C[Mine frequent rules<br/>Rules covering at least T requests<br/>FreqRules]
    C --> D[Filter by reliability<br/>Remove over permissive rules<br/>RelRules]
    D --> E[Minimality step<br/>Keep shortest equivalent rules<br/>ShortRules]
    E --> F([End])



