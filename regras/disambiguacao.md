# REGRAS DE DISAMBIGUAÇÃO POR CO-SMELLS

## Princípio Geral

**O diagnóstico mais confiável é obtido pela combinação de múltiplos smells (co-smells).**
Um único smell raramente é suficiente. O conjunto de smells observados e o contexto
de como a classe evoluiu são os principais fatores de decisão.

---

## Tabela de Priorização por Combinação de Co-Smells

### Combinações → D04 – Paradigma OO (alta confiança)

| Combinação | Indicador | Justificativa |
|-----------|-----------|---------------|
| Large Class + Functional Decomposition + Spaghetti Code | D04.01 | Tríade clássica de pensamento procedural |
| Long Method + Spaghetti Code | D04.01 | Métodos como funções procedurais |
| Functional Decomposition + qualquer smell | D04.01 ou D04.05 | Functional Decomposition sempre indica D04 |
| Swiss Army Knife + Large Class + Spaghetti Code | D04.05 | Misconception profunda sobre OO |
| DIP violado + Functional Decomposition | D04.06 | Confunde modularização com OO |

### Combinações → D02 – Classes (alta confiança)

| Combinação | Indicador | Justificativa |
|-----------|-----------|---------------|
| Large Class + Data Class | D02.06 ou D02.07 | Classe vista como coleção/estrutura de dados |
| Refused Bequest + Parallel Inheritance Hierarchies | D02.02 | Hierarquia modelada incorretamente |
| Speculative Generality + Lazy Class | D02.01 | Natureza estática não assimilada |
| Large Class + Shotgun Surgery + Swiss Army Knife | D02.04 | Não identifica classes corretas |
| Feature Envy + Data Class | D02.07 ou D02.08 | Classe sem abstração adequada |

### Combinações → D05 – Relacionamentos (alta confiança)

| Combinação | Indicador | Justificativa |
|-----------|-----------|---------------|
| Inappropriate Intimacy + Feature Envy | D05.01 | Associação modelada incorretamente |
| Middle Man + Message Chains | D05.01 | Dependência mal estruturada |
| Refused Bequest + Temporary Field | D05.03 | Herança inadequada |
| Shotgun Surgery + Divergent Change | D05.06 | Relacionamentos modelados incorretamente |
| DIP violado + Inappropriate Intimacy | D05.02 | Dependência mal utilizada |

### Combinações → D07 – Encapsulamento (alta confiança)

| Combinação | Indicador | Justificativa |
|-----------|-----------|---------------|
| Data Class + Deficient Encapsulation | D07.01 | Encapsulamento incompreendido |
| Inappropriate Intimacy + Data Clump | D07.05 | Problemas com information hiding |
| Large Class + Divergent Change + atributos públicos | D07.03 | Modularidade não aplicada |
| ISP violado + Alternative Classes | D07.03 | Modularidade não aplicada |

### Combinações → D03 – Métodos (alta confiança)

| Combinação | Indicador | Justificativa |
|-----------|-----------|---------------|
| Long Method + Duplicate Code | D03.03 + D03.05 | Não sabe decompor nem reutilizar |
| Message Chains + Long Parameter List | D03.01 | Dificuldade em chamar métodos |
| Feature Envy + Divergent Change | D03.07 | Método colocado na classe errada |
| Data Clump + Long Parameter List | D03.01 | Parâmetros que deveriam ser um objeto |

### Combinações → D06 – Polimorfismo (alta confiança)

| Combinação | Indicador | Justificativa |
|-----------|-----------|---------------|
| Switch Statement + Refused Bequest | D06.01 | Polimorfismo muito abstrato |
| Long Parameter List + Duplicate Code | D06.02 + D06.03 | Confusão com sobrecarga |
| Switch Statement + Functional Decomposition | D04.01 + D06.01 | Múltiplos desafios simultâneos |

---

## Regras para Smells com Alta Ambiguidade

### Large Class (pode indicar D02, D04, D05, D07)
```
SE Large Class + Functional Decomposition → D04.01 (procedural dominante)
SE Large Class + Data Class              → D02.06 (confusão classe/objeto)
SE Large Class + Inappropriate Intimacy  → D05.05 (composição/agregação confusa)
SE Large Class + Divergent Change        → D07.03 (modularidade não aplicada)
SE Large Class isolado                   → D02.04 (não identifica classes corretas)
```

### Feature Envy (pode indicar D02, D03, D04)
```
SE Feature Envy + Data Class             → D02.07 (classe como coleção)
SE Feature Envy + Large Class            → D04.02 (design OO inadequado)
SE Feature Envy + Divergent Change       → D03.07 (método na classe errada)
SE Feature Envy isolado                  → D03.08 (Wrong Class For Method)
```

### Inappropriate Intimacy (pode indicar D03, D05, D07)
```
SE Inappropriate Intimacy + Feature Envy → D05.01 (associação incorreta)
SE Inappropriate Intimacy + Data Class   → D07.01 (encapsulamento incompreendido)
SE Inappropriate Intimacy + Data Clump  → D07.05 (information hiding)
SE Inappropriate Intimacy isolado        → D05.05 (confusão composição/agregação)
```

### Divergent Change (pode indicar D03, D04, D05, D07)
```
SE Divergent Change + Shotgun Surgery    → D05.06 (relacionamentos inadequados)
SE Divergent Change + Large Class        → D07.03 (modularidade)
SE Divergent Change + Feature Envy      → D03.07 (método no lugar errado)
SE Divergent Change isolado             → D07.03 (mistura de concerns)
```

---

## Quando Há Múltiplos Desafios Simultâneos

Quando a análise indicar 2 ou mais desafios com confiança similar, reportar **todos**
com grau de confiança diferenciado.

**Exemplo de saída esperada:**
```
Smells detectados: Large Class, Functional Decomposition, Spaghetti Code
Diagnóstico primário: D04 – Dificuldade em implementar OO (Alta confiança)
  → Aluno pensa de forma procedural (D04.01)
Diagnóstico secundário: D02 – Dificuldade em compreender classes (Média confiança)
  → Pode não identificar as classes corretas (D02.04)
Pergunta de refinamento: Os métodos seguem uma sequência lógica linear?
```

---

## Escala de Confiança

| Nº de smells apontando para o mesmo desafio | Confiança |
|--------------------------------------------|-----------|
| 1 smell | Baixa |
| 2 smells | Média |
| 3+ smells | Alta |
| 3+ smells + SOLID violado relacionado | Muito Alta |
