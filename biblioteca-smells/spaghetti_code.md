# SMELL: Spaghetti Code

**Tipo:** Design Smell (Anti-Pattern)
**Referência:** Brown et al. [6]
**Categoria:** Design

## Descrição
Código com lógica e fluxo entrelaçados, difícil de seguir e modificar. Estrutura caótica com múltiplos desvios de fluxo e ausência de organização clara.

## Como reconhecer no código
- Lógica de controle extremamente aninhada (if dentro de if dentro de for)
- Uso excessivo de variáveis de controle ou flags booleanas globais
- Fluxo impossível de rastrear sem executar o código
- Ausência de estrutura modular clara

## Desafios de aprendizagem associados

| Desafio | Categorias | Confiança | Contexto de ativação |
|---------|-----------|-----------|----------------------|
| D04 – Paradigma OO | D04.01, D04.03, D04.05, D04.06 | Alta | Aluno não assimilou nenhum princípio OO de organização |

## Regras de disambiguação
- **Spaghetti Code + Functional Decomposition** → Confirma **D04.01**
- **Spaghetti Code + Large Class** → Priorizar **D04.05**
- **Spaghetti Code isolado** → **D04.03**

## Perguntas para refinamento diagnóstico
1. O aluno consegue explicar o fluxo do próprio código?
2. O aluno tem algum conhecimento de paradigma OO ou veio exclusivamente de programação estrutural?

## Intervenção pedagógica sugerida
- Retornar aos fundamentos do paradigma OO
- Introdução a padrões de organização de código
- Exercícios de refatoração incremental com guia
