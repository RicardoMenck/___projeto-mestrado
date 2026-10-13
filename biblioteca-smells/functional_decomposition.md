# SMELL: Functional Decomposition

**Tipo:** Design Smell (Anti-Pattern)
**Referência:** Brown et al. [6]
**Categoria:** Design

## Descrição
Código no estilo procedural dentro de um ambiente OO. O aluno implementa hierarquia de funções ao invés de objetos colaborativos.

## Como reconhecer no código
- Classe principal com um método central que chama outros auxiliares
- Classes que representam ações (verbo) em vez de entidades (substantivo)
- Ausência de herança, polimorfismo e encapsulamento real
- OO usado apenas como "embrulho" para código procedural

## Desafios de aprendizagem associados

| Desafio | Categorias | Confiança | Contexto de ativação |
|---------|-----------|-----------|----------------------|
| D04 – Paradigma OO | D04.01, D04.03, D04.05, D04.06 | Alta | Aluno aplica raciocínio procedural em OO — não assimilou o paradigma |

## Regras de disambiguação
- **Functional Decomposition + Spaghetti Code** → Priorizar **D04.01**
- **Functional Decomposition + Large Class** → Priorizar **D04.05**
- **Functional Decomposition isolado** → **D04.03**

## Co-smells relacionados
- Spaghetti Code → combinação clássica de D04
- Large Class → reforça D04
- Long Method → reforça D04.01

## Perguntas para refinamento diagnóstico
1. O aluno estudou programação procedural antes de OO?
2. As classes têm nomes de verbos (ProcessarDados, CalcularSalario)?

## Intervenção pedagógica sugerida
- Revisitar os fundamentos do paradigma OO desde o início
- Comparar estilo procedural vs. OO no mesmo problema
- Exercícios com CRC Cards (Class-Responsibility-Collaboration)
