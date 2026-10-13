# SMELL: Divergent Change

**Tipo:** Code Smell (Change Preventer)
**Referência:** Fowler [9]
**Categoria:** Implementação

## Descrição
Classe que frequentemente precisa ser alterada de maneiras diferentes para razões diferentes. Indica múltiplas responsabilidades não relacionadas.

## Como reconhecer no código
- Classe precisa ser modificada por mudança em banco de dados E em regras de negócio E em interface
- Mistura responsabilidades de diferentes "eixos de mudança"

## Desafios de aprendizagem associados

| Desafio | Categorias | Confiança | Contexto de ativação |
|---------|-----------|-----------|----------------------|
| D03 – Métodos | D03.07, D03.08 | Média | Métodos pertencem a outras responsabilidades |
| D04 – Paradigma OO | D04.03 | Média | Não aplicou SRP na implementação |
| D05 – Relacionamentos | D05.06, D05.07 | Alta | Relacionamentos de responsabilidade não modelados |
| D07 – Encapsulamento | D07.03 | Alta | Mistura concerns na mesma classe |

## Regras de disambiguação
- **Divergent Change + Large Class** → Priorizar **D07.03**
- **Divergent Change + Feature Envy** → Priorizar **D03.07**
- **Divergent Change + Shotgun Surgery** → Priorizar **D05.06**
- **Divergent Change isolado** → **D07.03**

## Co-smells relacionados
- Shotgun Surgery → par clássico: juntos indicam design inadequado
- Large Class → reforça D07
- Feature Envy → reforça D03

## Intervenção pedagógica sugerida
- Ensinar SRP com exemplos práticos
- Exercícios de identificação de "eixos de mudança"
- Praticar separação por camadas (domínio, persistência, interface)
