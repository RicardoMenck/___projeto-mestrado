# SMELL: Dependency Inversion Principle (Violação)

**Tipo:** Violação de Princípio SOLID
**Referência:** Martin [36]
**Categoria:** Design

## Descrição
Módulos de alto nível dependem de implementações concretas em vez de abstrações. Aluno não usa interfaces ou classes abstratas para desacoplar componentes.

## Como reconhecer no código
- Instanciação direta de classes concretas dentro de outras classes (new ConcreteClass())
- Dependência de classes específicas em vez de interfaces
- Ausência de injeção de dependência
- Impossibilidade de substituir uma implementação sem alterar o código cliente

## Desafios de aprendizagem associados

| Desafio | Categorias | Confiança | Contexto de ativação |
|---------|-----------|-----------|----------------------|
| D04 – Paradigma OO | D04.03, D04.05, D04.06 | Alta | Não aplica abstrações no design — acopla diretamente às implementações |
| D05 – Relacionamentos | D05.01, D05.02 | Alta | Não modela corretamente dependências entre módulos |

## Regras de disambiguação
- **DIP violado + Cyclically-dependent Modularization** → Priorizar **D04.02**
- **DIP violado + Functional Decomposition** → Priorizar **D04.06**
- **DIP violado + Inappropriate Intimacy** → Priorizar **D05.02**
- **DIP violado isolado** → **D04.03**

## Intervenção pedagógica sugerida
- Ensinar DIP com exemplos de injeção de dependência
- Exercícios de substituição de instanciação direta por abstração
- Introduzir: "programe para interfaces, não para implementações"
