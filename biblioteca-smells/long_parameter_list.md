# SMELL: Long Parameter List

**Tipo:** Code Smell (Bloater)
**Referência:** Fowler [9]
**Categoria:** Implementação

## Descrição
Método com número excessivo de parâmetros, tornando-o difícil de usar e manter. Frequentemente indica que os dados deveriam estar agrupados em um objeto.

## Como reconhecer no código
- Método com mais de 3–4 parâmetros (referência contextual)
- Parâmetros que sempre aparecem juntos em várias chamadas
- Parâmetros representando dados de um mesmo conceito não encapsulado

## Desafios de aprendizagem associados

| Desafio | Categorias | Confiança | Contexto de ativação |
|---------|-----------|-----------|----------------------|
| D03 – Métodos | D03.01, D03.02 | Alta | Não sabe estruturar a assinatura do método corretamente |
| D06 – Polimorfismo | D06.02, D06.03 | Média | Usa parâmetros para simular o que deveria ser sobrecarga |

## Regras de disambiguação
- **Long Parameter List + Duplicate Code** → Priorizar **D06.02**
- **Long Parameter List + Data Clump** → Priorizar **D03.01**
- **Long Parameter List isolado** → **D03.02**

## Co-smells relacionados
- Data Clump → parâmetros juntos deveriam ser uma classe
- Duplicate Code → reforça D06

## Intervenção pedagógica sugerida
- Ensinar o conceito de Parameter Object
- Revisar o conceito de sobrecarga de método (overloading)
- Exercício de refatoração: Introduce Parameter Object
