# SMELL: Deficient Encapsulation

**Tipo:** Design Smell
**Referência:** Suryanarayana et al. [52]
**Categoria:** Design

## Descrição
Detalhes internos de implementação expostos desnecessariamente, reduzindo flexibilidade e segurança.

## Como reconhecer no código
- Atributos públicos que deveriam ser privados
- Métodos auxiliares internos públicos sem necessidade
- Exposição direta de coleções internas sem cópia defensiva

## Desafios de aprendizagem associados

| Desafio | Categorias | Confiança | Contexto de ativação |
|---------|-----------|-----------|----------------------|
| D02 – Classes | D02.06 | Média | Confunde classe com estrutura de dados sem comportamento protegido |
| D07 – Encapsulamento | D07.01, D07.05 | Alta | Encapsulamento entendido de forma superficial ou não aplicado |

## Regras de disambiguação
- **Deficient Encapsulation + Data Class** → Priorizar **D07.01**
- **Deficient Encapsulation + Inappropriate Intimacy** → Priorizar **D07.05**
- **Deficient Encapsulation + Large Class** → Priorizar **D02.06**

## Intervenção pedagógica sugerida
- Revisitar o conceito de information hiding
- Demonstrar riscos de estado exposto com exemplos práticos
- Apresentar invariantes de classe como conceito central
