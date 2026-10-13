# SMELL: Data Class

**Tipo:** Code Smell (Object-Orientation Abuser)
**Referência:** Fowler [9]
**Categoria:** Implementação

## Descrição
Classe que contém apenas campos e acessores (getters/setters) com pouco ou nenhum comportamento próprio. Funciona como estrutura de dados simples, não como objeto OO.

## Como reconhecer no código
- Classe com apenas atributos, getters e setters
- Nenhum método que implemente regras de negócio
- Outros objetos manipulam os dados dessa classe diretamente

## Desafios de aprendizagem associados

| Desafio | Categorias | Confiança | Contexto de ativação |
|---------|-----------|-----------|----------------------|
| D02 – Classes | D02.01, D02.06, D02.07, D02.08 | Alta | Aluno trata classe como struct/record sem comportamento |
| D07 – Encapsulamento | D07.01, D07.05, D07.06 | Alta | Encapsulamento entendido apenas como private + getter/setter |

## Regras de disambiguação
- **Data Class + Feature Envy** → Priorizar **D02.07**
- **Data Class + Deficient Encapsulation** → Priorizar **D07.01**
- **Data Class + atributos públicos** → Priorizar **D07.05, D07.06**
- **Data Class isolado** → Priorizar **D02.08**

## Co-smells relacionados
- Feature Envy → reforça D02 (outro método manipula os dados)
- Deficient Encapsulation → reforça D07
- Inappropriate Intimacy → reforça D07

## Perguntas para refinamento diagnóstico
1. O aluno colocou getters/setters por hábito ou por entender que é correto?
2. A classe tem regras de negócio que poderiam ser internalizadas?
3. O aluno veio de linguagens sem OO (C, Pascal)?

## Intervenção pedagógica sugerida
- Revisar o conceito de comportamento em objetos
- Exercício: identificar quais métodos que usam os dados deveriam estar na própria classe
- Explorar o princípio "Tell, Don't Ask"
