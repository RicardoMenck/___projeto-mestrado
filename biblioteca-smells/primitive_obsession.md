# SMELL: Primitive Obsession

**Tipo:** Code Smell (Object-Orientation Abuser)
**Referência:** Fowler [9]
**Categoria:** Implementação

## Descrição
Uso excessivo de tipos primitivos ao invés de criar pequenos objetos para representar conceitos do domínio. Aluno não cria abstrações para conceitos que merecem uma classe própria.

## Como reconhecer no código
- CPF representado como String sem validação encapsulada
- Dinheiro representado como float sem regras de arredondamento
- Enumerações como constantes inteiras
- Grupos de primitivos que sempre andam juntos (CEP, cidade, estado)

## Desafios de aprendizagem associados

| Desafio | Categorias | Confiança | Contexto de ativação |
|---------|-----------|-----------|----------------------|
| D04 – Paradigma OO | D04.03 | Alta | Não cria abstrações para conceitos do domínio — pensa em dados primitivos |

## Regras de disambiguação
- **Primitive Obsession + Data Class** → Confirma **D04.03**
- **Primitive Obsession + Data Clump** → Priorizar **D04.03** (primitivos agrupados deveriam ser classe)
- **Primitive Obsession isolado** → **D04.03**

## Intervenção pedagógica sugerida
- Exercícios de identificação de Value Objects
- Apresentar o conceito de Domain Model
- Refatoração: Replace Primitive with Object
