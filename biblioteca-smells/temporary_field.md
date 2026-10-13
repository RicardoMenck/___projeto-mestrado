# SMELL: Temporary Field

**Tipo:** Code Smell (Object-Orientation Abuser)
**Referência:** Fowler [9]
**Categoria:** Implementação

## Descrição
Variáveis de instância usadas apenas em determinadas situações ou em um único método, ficando nulas no restante do tempo.

## Como reconhecer no código
- Atributo que só é definido em um método específico e nulo no restante
- Atributos usados apenas durante um algoritmo específico
- Flags booleanas de instância que controlam estado temporário

## Desafios de aprendizagem associados

| Desafio | Categorias | Confiança | Contexto de ativação |
|---------|-----------|-----------|----------------------|
| D05 – Relacionamentos | D05.03, D05.04 | Alta | Campo temporário indica que deveria ser subclasse ou objeto separado — herança não modelada |

## Regras de disambiguação
- **Temporary Field + Refused Bequest** → Confirma **D05.03**
- **Temporary Field + Parallel Inheritance Hierarchies** → Priorizar **D05.04**
- **Temporary Field isolado** → **D05.03**

## Intervenção pedagógica sugerida
- Exercícios de identificação de candidatos à especialização (subclasse)
- Ensinar State Pattern como alternativa para objetos com estados variáveis
