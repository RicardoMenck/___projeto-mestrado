# SMELL: Parallel Inheritance Hierarchies

**Tipo:** Code Smell (Change Preventer)
**Referência:** Fowler [9]
**Categoria:** Implementação

## Descrição
Quando uma subclasse é criada em uma hierarquia, é necessário criar subclasse correspondente em outra hierarquia. As duas crescem em paralelo.

## Como reconhecer no código
- Duas hierarquias que espelham exatamente a mesma estrutura
- Nomes das classes em uma hierarquia prefixam/sufixam as da outra
- Adicionar especialização exige modificar ambas as hierarquias

## Desafios de aprendizagem associados

| Desafio | Categorias | Confiança | Contexto de ativação |
|---------|-----------|-----------|----------------------|
| D02 – Classes | D02.02 | Alta | Hierarquia de classes modelada incorretamente |
| D05 – Relacionamentos | D05.03 | Alta | Herança/generalização não aplicada corretamente |

## Regras de disambiguação
- **Parallel Inheritance Hierarchies + Refused Bequest** → Priorizar **D02.02**
- **Parallel Inheritance Hierarchies + Shotgun Surgery** → Priorizar **D05.06**
- **Parallel Inheritance Hierarchies isolado** → **D05.03**

## Intervenção pedagógica sugerida
- Exercícios de consolidação de hierarquias paralelas
- Apresentar padrões como Visitor ou Strategy como alternativas
