# MAPA DE CO-SMELLS: RELAÇÕES ENTRE INDICADORES

## Clusters de Co-Smells por Desafio

### Cluster D04 – Pensamento Procedural
```
Functional Decomposition
    ├── Large Class        (reforça D04.01)
    ├── Spaghetti Code     (reforça D04.01)
    ├── Long Method        (reforça D04.01)
    └── DIP violado        (reforça D04.06)
```
Quando 3+ desses smells aparecem: confirmar D04 com alta confiança.

### Cluster D02 – Abstração de Classes
```
Data Class
    ├── Feature Envy              (reforça D02.07)
    ├── Deficient Encapsulation   (reforça D02.06)
    └── Large Class               (reforça D02.06, D02.07)

Large Class
    ├── Shotgun Surgery                   (reforça D02.04)
    ├── Swiss Army Knife                  (reforça D02.04)
    └── Parallel Inheritance Hierarchies  (reforça D02.02)
```

### Cluster D05 – Relacionamentos OO
```
Inappropriate Intimacy
    ├── Feature Envy    (confirma D05.01)
    ├── Middle Man      (reforça D05.01)
    └── Data Clump      (reforça D05.05)

Refused Bequest
    ├── Temporary Field                   (confirma D05.03)
    └── Parallel Inheritance Hierarchies  (reforça D05.04)
```

### Cluster D07 – Encapsulamento
```
Data Class
    ├── Deficient Encapsulation  (confirma D07.01, D07.05)
    ├── Inappropriate Intimacy   (reforça D07.05)
    └── Data Clump               (reforça D07.05)

Large Class
    ├── Divergent Change  (confirma D07.03)
    └── ISP violado       (reforça D07.03)
```

### Cluster D03 – Métodos
```
Long Method
    ├── Duplicate Code      (reforça D03.05)
    └── Long Parameter List (reforça D03.01)

Message Chains
    ├── Long Parameter List (confirma D03.01)
    └── Middle Man          (reforça D03.02)

Feature Envy
    └── Divergent Change    (confirma D03.07, D03.08)
```

### Cluster D06 – Polimorfismo
```
Switch Statement
    ├── Refused Bequest       (confirma D06.01)
    ├── Duplicate Code        (reforça D06.02)
    └── Functional Decomp.    (reforça D04 + D06)

Long Parameter List
    └── Duplicate Code        (confirma D06.02, D06.03)
```

---

## Smells "Pivô" (Alta Ambiguidade — Exigem Co-Smells)

| Smell Pivô | Desafios Possíveis | Co-Smell Obrigatório? |
|------------|-------------------|----------------------|
| Large Class | D02, D04, D05, D07 | Sim |
| Feature Envy | D02, D03, D04 | Sim |
| Inappropriate Intimacy | D03, D05, D07 | Sim |
| Divergent Change | D03, D04, D05, D07 | Sim |
| Shotgun Surgery | D02, D04, D05 | Recomendado |
| Duplicate Code | D03, D06 | Recomendado |

**Regra:** Para smells pivô, nunca diagnosticar com base no smell isolado.

---

## Smells "Âncora" (Alta Especificidade — Diagnóstico Direto Possível)

| Smell Âncora | Desafio Primário | Confiança sem co-smell |
|--------------|-----------------|------------------------|
| Functional Decomposition | D04.01 | Alta |
| Switch Statement | D06.01 | Alta |
| Primitive Obsession | D04.03 | Alta |
| Spaghetti Code | D04.01 | Alta |
| Speculative Generality | D02.01 | Alta |
| Temporary Field | D05.03 | Alta |
| Refused Bequest | D05.03 ou D02.02 | Média-Alta |

**Regra:** Para smells âncora, o diagnóstico pode ser emitido mesmo sem co-smells,
mas co-smells ainda aumentam a confiança.
