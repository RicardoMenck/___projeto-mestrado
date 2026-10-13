# SMELL: Interface Segregation Principle (Violação)

**Tipo:** Violação de Princípio SOLID
**Referência:** Martin [36]
**Categoria:** Design

## Descrição
Interfaces grandes e genéricas que forçam classes a implementar métodos que não precisam. Um módulo não deve depender de métodos que não usa.

## Como reconhecer no código
- Interface com muitos métodos de propósitos diferentes
- Classes que implementam a interface mas deixam vários métodos vazios ou com exceção
- Interfaces que agrupam comportamentos de naturezas distintas

## Desafios de aprendizagem associados

| Desafio | Categorias | Confiança | Contexto de ativação |
|---------|-----------|-----------|----------------------|
| D02 – Classes | D02.04 | Alta | Não sabe identificar abstrações corretas para interfaces |
| D04 – Paradigma OO | D04.03, D04.05 | Alta | Não aplica corretamente os princípios OO de design |
| D07 – Encapsulamento | D07.03 | Alta | Interface grande viola modularidade e coesão |

## Regras de disambiguação
- **ISP violado + Swiss Army Knife** → Priorizar **D02.04**
- **ISP violado + Large Class** → Priorizar **D04.03**
- **ISP violado + Alternative Classes** → Priorizar **D07.03**

## Intervenção pedagógica sugerida
- Ensinar ISP com exemplos de interfaces coesas
- Exercícios de divisão de interfaces grandes em menores
- Comparar interfaces coesas vs. interfaces "canivete suíço"
