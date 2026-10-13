# SMELL: Feature Envy

**Tipo:** Code Smell (Coupler)
**Referência:** Fowler [9]
**Categoria:** Implementação

## Descrição
Método que acessa dados de outro objeto mais do que os dados de sua própria classe. O método "tem inveja" das funcionalidades de outra classe e deveria estar lá.

## Como reconhecer no código
- Método que chama vários getters de outro objeto para calcular algo
- Método que usa dados de outra classe mais do que da própria
- Lógica de negócio colocada na classe errada

## Desafios de aprendizagem associados

| Desafio | Categorias | Confiança | Contexto de ativação |
|---------|-----------|-----------|----------------------|
| D02 – Classes | D02.07, D02.08 | Média | Não definiu abstração adequada, comportamento na classe errada |
| D03 – Métodos | D03.07, D03.08 | Alta | Método claramente pertence a outra classe |
| D04 – Paradigma OO | D04.02, D04.05, D04.06 | Alta | Não fez análise OO adequada antes de implementar |

## Regras de disambiguação
- **Feature Envy + Large Class** → Priorizar **D04.02**
- **Feature Envy + Data Class** → Priorizar **D02.07**
- **Feature Envy + Divergent Change** → Priorizar **D03.07**
- **Feature Envy isolado** → Priorizar **D03.08**

## Co-smells relacionados
- Data Class → reforça D02 (método deveria estar na classe de dados)
- Large Class → reforça D04
- Divergent Change → reforça D03
- Inappropriate Intimacy → reforça D05

## Perguntas para refinamento diagnóstico
1. O aluno sabe identificar em qual classe o método deveria estar?
2. A classe que "sofre" o Feature Envy é uma Data Class?
3. O aluno fez algum diagrama antes de implementar?

## Intervenção pedagógica sugerida
- Praticar o princípio "Tell, Don't Ask"
- Revisar o conceito de responsabilidade de método
- Exercícios de refatoração: mover método para a classe correta
