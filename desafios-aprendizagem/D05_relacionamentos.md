# DESAFIO DE APRENDIZAGEM: D05 – Dificuldade em Compreender Relacionamentos OO

**Código:** D05
**Referência base:** Gutiérrez, Guerrero e López-Ospina [12]

## Descrição do Desafio
Aluno apresenta dificuldades ao compreender e implementar relacionamentos entre objetos: associação, dependência, herança (generalização/especialização), composição e agregação.

## Categorias de Análise e Códigos

| Categoria | Código | Descrição |
|-----------|--------|-----------|
| Associação e dependência | D05.01 | Associação não clara |
| Associação e dependência | D05.02 | Uso incorreto de dependência |
| Herança/generalização | D05.03 | Herança não aplicada |
| Herança/generalização | D05.04 | Generalização não modelada |
| Composição e agregação | D05.05 | Confusão entre composição e agregação |
| Modelagem de relacionamentos | D05.06 | Erro na modelagem de relacionamentos |
| Modelagem de relacionamentos | D05.07 | Mapa conceitual confuso |

## Indicadores no Código (Code Smells e SOLID)

| Indicador | Categorias sinalizadas | Confiança |
|-----------|----------------------|-----------|
| Inappropriate Intimacy | D05.01, D05.05 | Alta |
| Middle Man | D05.01, D05.02 | Alta |
| DIP violado | D05.01, D05.02 | Alta |
| Refused Bequest | D05.03 | Alta |
| Temporary Field | D05.03, D05.04 | Alta |
| Parallel Inheritance Hierarchies | D05.03 | Alta |
| Large Class | D05.05 | Média |
| Divergent Change | D05.06 | Alta |
| Shotgun Surgery | D05.06, D05.07 | Alta |

## Perfil Típico do Aluno com D05
- Usa herança onde deveria usar composição e vice-versa
- Não consegue modelar diagrama de classes antes de implementar
- Cria dependências diretas onde deveria usar abstrações
- Confunde "usa" (dependência) com "é um" (herança) e "tem um" (composição)
- Cria classes que sabem demais sobre os internos de outras

## Intervenções Pedagógicas Sugeridas
1. Exercícios de distinção: "é um" vs. "tem um" vs. "usa"
2. Modelagem UML antes de codificar
3. Identificação do tipo de relacionamento em cenários do mundo real
4. Introduzir DIP com exemplos de injeção de dependência
5. Casos onde herança é incorreta e composição é a solução
