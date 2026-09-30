This file explains the architecture of `rustytorch`.

```
           core
             │
             ▼
          tensor
             │
             ▼
        autograd
             │
      ┌──────┴───────┐
      ▼              ▼
     nn           optim
      │              │
      └──────┬───────┘
             ▼
         training
             │
    ┌────────┴────────┐
    ▼                 ▼
 vision         transformer
```