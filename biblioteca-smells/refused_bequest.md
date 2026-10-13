# SMELL: Refused Bequest

**Tipo:** Code Smell (Object-Orientation Abuser)
**Referência:** Fowler [9]
**Categoria:** Implementação

## Descrição
Subclasse que herda métodos ou dados que não precisa ou não usa. Herança usada apenas para reuso de código, não para representar "é um".

## Como reconhecer no código
- Subclasse que sobrescreve métodos herdados com corpo vazio ou exceção
- Subclasse que ignora parte significativa da interface da superclasse
- Herança usada apenas para reuso de código, não para especialização

## Desafios de aprendizagem associados

| Desafio | Categorias | Confiança | Contexto de ativação |
|---------|-----------|-----------|----------------------|
| D02 – Classes | D02.02, D02.03 | Alta | Não compreende hierarquia de classes nem nível correto de abstração |
| D05 – Relacionamentos | D05.03, D05.04 | Alta | Não distingue herança de composição |
| D06 – Polimorfismo | D06.01 | Média | Não sabe aplicar polimorfismo — usa herança inadequada |

## Regras de disambiguação
- **Refused Bequest + Parallel Inheritance Hierarchies** → Priorizar **D02.02**
- **Refused Bequest + Switch Statement** → Priorizar **D06.01**
- **Refused Bequest isolado** → Priorizar **D05.03**

## Smells relacionados (inferidos)
- Rebellious hierarchy → variante de design
- Liskov Substitution Principle violado → indicador SOLID associado

## Perguntas para refinamento diagnóstico
1. O aluno consegue explicar a relação "é um" entre as classes?
2. O aluno sabe quando usar herança vs. composição?

## Intervenção pedagógica sugerida
- Ensinar o Princípio de Substituição de Liskov (LSP)
- Exercícios para distinguir "é um" (herança) de "tem um" (composição)
- Refatoração de herança inadequada para composição
