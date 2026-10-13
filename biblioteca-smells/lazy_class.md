# SMELL: Lazy Class

**Tipo:** Code Smell (Dispensable)
**Referência:** Fowler [9]
**Categoria:** Implementação

## Descrição
Classe que faz muito pouco para justificar sua existência. Pode ser resultado de refatoração excessiva ou planejamento sem implementação completa.

## Como reconhecer no código
- Classe com 1–2 métodos triviais
- Classe que apenas delega para outra sem adicionar valor
- Classe criada especulativamente mas nunca desenvolvida

## Desafios de aprendizagem associados

| Desafio | Categorias | Confiança | Contexto de ativação |
|---------|-----------|-----------|----------------------|
| D03 – Métodos | D03.05 | Alta | Classe criada para "guardar" código que poderia estar em outra, sem entender reuso |

## Regras de disambiguação
- **Lazy Class + Speculative Generality** → classe sem propósito concreto
- **Lazy Class + Duplicate Code** → Priorizar **D03.05**
- **Lazy Class isolado** → **D03.05**

## Intervenção pedagógica sugerida
- Revisar critérios para criação de nova classe
- Ensinar quando consolidar vs. separar responsabilidades
