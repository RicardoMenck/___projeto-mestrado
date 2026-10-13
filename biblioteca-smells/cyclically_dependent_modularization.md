# SMELL: Cyclically-dependent Modularization

**Tipo:** Design Smell
**Referência:** Suryanarayana et al. [52]
**Categoria:** Design

## Descrição
Módulos/classes que dependem uns dos outros de forma circular (A depende de B, B depende de C, C depende de A). Prejudica modularidade e testabilidade.

## Como reconhecer no código
- Classe A importa Classe B que importa Classe A
- Ciclos de dependência detectáveis via análise de imports
- Impossibilidade de testar uma classe sem instanciar todas as outras do ciclo

## Desafios de aprendizagem associados

| Desafio | Categorias | Confiança | Contexto de ativação |
|---------|-----------|-----------|----------------------|
| D02 – Classes | D02.02 | Alta | Hierarquia cíclica é anomalia — aluno não modelou hierarquia correta |
| D04 – Paradigma OO | D04.02 | Alta | Dependência circular resultado de design inadequado |

## Regras de disambiguação
- **Cyclically-dependent Modularization + Large Class** → Priorizar **D04.02**
- **Cyclically-dependent Modularization + Refused Bequest** → Priorizar **D02.02**
- **Cyclically-dependent Modularization isolado** → **D04.02**

## Intervenção pedagógica sugerida
- Ensinar Dependency Inversion Principle (DIP)
- Exercícios com diagramas de dependência antes de codificar
- Introduzir o conceito de camadas arquiteturais
