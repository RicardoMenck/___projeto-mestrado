# SMELL: Data Clump

**Tipo:** Code Smell (Bloater)
**Referência:** Fowler [9]
**Categoria:** Implementação

## Descrição
Grupos de dados (variáveis, parâmetros) que sempre aparecem juntos em múltiplos lugares, sugerindo que deveriam ser encapsulados em uma classe própria.

## Como reconhecer no código
- Três ou mais variáveis que sempre aparecem juntas como parâmetros
- Mesmos campos repetidos em múltiplas classes
- Conjunto de dados sempre manipulado junto

## Desafios de aprendizagem associados

| Desafio | Categorias | Confiança | Contexto de ativação |
|---------|-----------|-----------|----------------------|
| D03 – Métodos | D03.01, D03.03 | Alta | Agrupamento em chamadas de métodos — dificuldade em estruturar parâmetros |
| D07 – Encapsulamento | D07.05 | Média | Grupo de dados deveria ser encapsulado como objeto |

## Regras de disambiguação
- **Data Clump + Long Parameter List** → Priorizar **D03.01**
- **Data Clump + Deficient Encapsulation** → Priorizar **D07.05**
- **Data Clump + Inappropriate Intimacy** → Priorizar **D07.05**

## Intervenção pedagógica sugerida
- Exercícios de identificação de conceitos implícitos no código
- Refatoração: Introduce Parameter Object / Preserve Whole Object
