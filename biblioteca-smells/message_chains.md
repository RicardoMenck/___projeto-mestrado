# SMELL: Message Chains

**Tipo:** Code Smell (Coupler)
**Referência:** Fowler [9]
**Categoria:** Implementação

## Descrição
Sequência de chamadas encadeadas que atravessam múltiplos objetos (ex: objeto.getA().getB().getC().valor()). Expõe estrutura interna de navegação.

## Como reconhecer no código
- Chamadas encadeadas com vários níveis de getters
- Código que "navega" pela estrutura interna dos objetos
- Violações da Lei de Demeter

## Desafios de aprendizagem associados

| Desafio | Categorias | Confiança | Contexto de ativação |
|---------|-----------|-----------|----------------------|
| D03 – Métodos | D03.01, D03.02 | Alta | Não sabe como chamar métodos de forma adequada — usa navegação em vez de delegação |

## Regras de disambiguação
- **Message Chains + Middle Man** → Priorizar **D03.01**
- **Message Chains + Inappropriate Intimacy** → Priorizar **D03.02**
- **Message Chains isolado** → **D03.01**

## Intervenção pedagógica sugerida
- Ensinar Lei de Demeter ("não fale com estranhos")
- Exercícios de refatoração: Hide Delegate
- Introduzir o princípio Tell, Don't Ask
