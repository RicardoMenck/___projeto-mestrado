# SMELL: Alternative Classes with Different Interfaces

**Tipo:** Code Smell (Dispensable)
**Referência:** Fowler [9]
**Categoria:** Implementação

## Descrição
Classes que realizam trabalho similar mas possuem interfaces diferentes, dificultando uso polimórfico. Frequentemente indica que o aluno criou a mesma abstração duas vezes de formas diferentes.

## Como reconhecer no código
- Duas classes com nomes diferentes mas funcionalidades sobrepostas
- Métodos que fazem a mesma coisa mas têm assinaturas diferentes
- Lógica duplicada em classes com interfaces incompatíveis

## Desafios de aprendizagem associados

| Desafio | Categorias | Confiança | Contexto de ativação |
|---------|-----------|-----------|----------------------|
| D02 – Classes | D02.04 | Alta | Não identificou que as classes representam o mesmo conceito |
| D07 – Encapsulamento | D07.03 | Média | Não aplicou modularidade corretamente — duplicou a abstração |

## Regras de disambiguação
- **Alternative Classes + Duplicate Code** → Priorizar **D02.04**
- **Alternative Classes + ISP violado** → Priorizar **D07.03**
- **Alternative Classes isolado** → **D02.04**

## Intervenção pedagógica sugerida
- Exercícios de identificação de conceitos duplicados
- Praticar extração de interface comum
- Ensinar o papel das interfaces em OO
