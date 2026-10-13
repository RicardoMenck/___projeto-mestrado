# SMELL: Speculative Generality

**Tipo:** Code Smell (Dispensable)
**Referência:** Fowler [9]
**Categoria:** Implementação

## Descrição
Código projetado para necessidades futuras que podem nunca ocorrer. O aluno tenta antecipar extensões não solicitadas.

## Como reconhecer no código
- Hierarquias de classes para um único caso de uso concreto
- Parâmetros ou métodos que nunca são utilizados
- Interfaces com apenas uma implementação sem necessidade real

## Desafios de aprendizagem associados

| Desafio | Categorias | Confiança | Contexto de ativação |
|---------|-----------|-----------|----------------------|
| D02 – Classes | D02.01 | Alta | Não assimilou a natureza estática das classes — generaliza onde não é necessário |

## Regras de disambiguação
- **Speculative Generality + Open/Closed Principle violado** → Confirma **D02.01**
- **Speculative Generality + Lazy Class** → reforça classes criadas sem propósito real
- **Speculative Generality isolado** → **D02.01**

## Intervenção pedagógica sugerida
- Ensinar o princípio YAGNI (You Aren't Gonna Need It)
- Exercícios com requisitos concretos e limitados
