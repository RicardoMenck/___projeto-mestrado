# SMELL: Duplicate Code

**Tipo:** Code Smell (Dispensable)
**Referência:** Fowler [9]
**Categoria:** Implementação

## Descrição
Código idêntico ou muito similar que existe em mais de um lugar: dentro de uma classe, entre classes relacionadas ou não relacionadas.

## Como reconhecer no código
- Blocos de código copiados e colados com pequenas variações
- Mesma lógica implementada em múltiplos métodos
- Mesma sequência de operações em classes diferentes

## Desafios de aprendizagem associados

| Desafio | Categorias | Confiança | Contexto de ativação |
|---------|-----------|-----------|----------------------|
| D03 – Métodos | D03.05, D03.06 | Alta | Não sabe reutilizar métodos — reescreve o que poderia chamar |
| D06 – Polimorfismo | D06.02, D06.03 | Média | Duplica em vez de usar sobrecarga ou polimorfismo |

## Regras de disambiguação
- **Duplicate Code em classes não relacionadas** → Priorizar **D03.05**
- **Duplicate Code entre subclasses** → Priorizar **D06.03**
- **Duplicate Code + Long Method** → Priorizar **D03.06**
- **Duplicate Code + Switch Statement** → Priorizar **D06.02**

## Smells relacionados (inferidos)
- Cut and paste programming → mesma causa raiz
- Unfactored hierarchy / Duplicate abstraction → variantes de design

## Intervenção pedagógica sugerida
- Ensinar o princípio DRY (Don't Repeat Yourself)
- Exercícios de Extract Method e Pull Up Method
- Explorar o papel da herança no reuso de comportamento
