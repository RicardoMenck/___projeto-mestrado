# SMELL: Long Method

**Tipo:** Code Smell (Bloater)
**Referência:** Fowler [9]
**Categoria:** Implementação

## Descrição
Método excessivamente longo e complexo, difícil de entender e manter. Geralmente faz muitas coisas que deveriam ser delegadas a métodos menores.

## Como reconhecer no código
- Método com mais de 20–30 linhas (referência contextual)
- Método que mistura múltiplas responsabilidades
- Comentários intermediários explicando "blocos" (cada bloco poderia ser um método)
- Aninhamento profundo de condicionais e loops

## Desafios de aprendizagem associados

| Desafio | Categorias | Confiança | Contexto de ativação |
|---------|-----------|-----------|----------------------|
| D03 – Métodos | D03.03, D03.04 | Alta | Não sabe decompor comportamento em métodos menores |
| D04 – Paradigma OO | D04.01 | Alta | Método como função procedural longa |

## Regras de disambiguação
- **Long Method + Spaghetti Code + Functional Decomposition** → Priorizar **D04.01**
- **Long Method + Duplicate Code** → Priorizar **D03.03**
- **Long Method com comentários de bloco** → Priorizar **D03.04**
- **Long Method isolado** → Priorizar **D03.03**

## Co-smells relacionados
- Spaghetti Code → reforça D04
- Functional Decomposition → reforça D04
- Duplicate Code → reforça D03
- Large Class → reforça D04 quando combinado

## Smells relacionados (inferidos)
- Broken modularization → variante de design

## Perguntas para refinamento diagnóstico
1. O aluno consegue identificar "partes" do método que poderiam ter nome próprio?
2. O aluno usa comentários para separar seções dentro do método?

## Intervenção pedagógica sugerida
- Prática de Extract Method (refatoração)
- Exercícios de decomposição funcional em OO
- Introdução ao SRP aplicado a métodos
