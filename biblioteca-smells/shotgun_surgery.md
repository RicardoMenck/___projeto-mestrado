# SMELL: Shotgun Surgery

**Tipo:** Code Smell (Change Preventer)
**Referência:** Fowler [9]
**Categoria:** Implementação

## Descrição
Uma única mudança lógica requer modificações em muitas classes diferentes simultaneamente. Indica baixa coesão e alto acoplamento.

## Como reconhecer no código
- Adicionar funcionalidade simples exige alterar 5+ classes
- Lógica relacionada espalhada por várias classes sem critério
- Mudança em um campo exige atualização em múltiplos lugares

## Desafios de aprendizagem associados

| Desafio | Categorias | Confiança | Contexto de ativação |
|---------|-----------|-----------|----------------------|
| D02 – Classes | D02.04 | Alta | Aluno não identificou corretamente as classes |
| D04 – Paradigma OO | D04.02, D04.05, D04.06 | Alta | Ausência de análise OO na fase de design |
| D05 – Relacionamentos | D05.06, D05.07 | Alta | Relacionamentos entre classes modelados incorretamente |

## Regras de disambiguação
- **Shotgun Surgery + Feature Envy + Large Class** → Priorizar **D04** (design OO inadequado)
- **Shotgun Surgery + Parallel Inheritance Hierarchies** → Priorizar **D05.06**
- **Shotgun Surgery + Data Class** → Priorizar **D02.04**

## Co-smells relacionados
- Feature Envy → reforça D04
- Large Class → reforça D02
- Parallel Inheritance Hierarchies → reforça D05

## Perguntas para refinamento diagnóstico
1. O aluno planejou as classes antes de codificar?
2. A lógica espalhada tem alguma coesão semântica?

## Intervenção pedagógica sugerida
- Ensinar o conceito de coesão antes de acoplamento
- Exercícios de refatoração: consolidar lógica dispersa
- Praticar análise de domínio com identificação de responsabilidades
