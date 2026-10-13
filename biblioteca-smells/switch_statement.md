# SMELL: Switch Statement

**Tipo:** Code Smell (Object-Orientation Abuser)
**Referência:** Fowler [9]
**Categoria:** Implementação

## Descrição
Uso de lógica condicional complexa (switch/case ou if-else em cascata) para implementar comportamento que deveria ser resolvido via polimorfismo. Indicador claro de dificuldade com OO.

## Como reconhecer no código
- Switch/case ou if-else em cadeia baseado no tipo de objeto
- Mesmo switch repetido em múltiplos métodos ou classes
- Verificação de instanceof para decidir comportamento

## Desafios de aprendizagem associados

| Desafio | Categorias | Confiança | Contexto de ativação |
|---------|-----------|-----------|----------------------|
| D03 – Métodos | D03.05 | Média | Usa switch para reutilizar lógica em vez de polimorfismo |
| D06 – Polimorfismo | D06.01 | Alta | Substitui polimorfismo por condicional explícita |

## Regras de disambiguação
- **Switch Statement + Refused Bequest** → Priorizar **D06.01**
- **Switch Statement + Duplicate Code** → Priorizar **D06.02**
- **Switch Statement + Functional Decomposition** → Priorizar **D04.01 + D06.01** (múltiplos desafios)
- **Switch Statement isolado** → **D06.01**

## Smells relacionados (inferidos)
- Complicated Boolean Expression → variante
- Conditional Complexity → variante
- Unexploited Encapsulation → violação relacionada
- Missing Hierarchy → hierarquia polimórfica ausente
- Open/Closed Principle violado → associado diretamente

## Perguntas para refinamento diagnóstico
1. O switch verifica o tipo do objeto (instanceof)?
2. O mesmo switch aparece em outros métodos?
3. O aluno sabe que o switch poderia ser substituído por herança?

## Intervenção pedagógica sugerida
- Demonstrar refatoração Replace Conditional with Polymorphism
- Exercícios que mostram vantagens do polimorfismo sobre condicionais
- Introduzir o Open/Closed Principle (OCP)
