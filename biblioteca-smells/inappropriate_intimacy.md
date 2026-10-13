# SMELL: Inappropriate Intimacy

**Tipo:** Code Smell (Coupler)
**Referência:** Fowler [9]
**Categoria:** Implementação

## Descrição
Classes que sabem demais sobre os detalhes internos umas das outras. Viola encapsulamento e cria acoplamento excessivo.

## Como reconhecer no código
- Classe A acessa diretamente os atributos internos de Classe B
- Classes com dependências bidirecionais profundas
- Métodos que manipulam estado interno de outra classe diretamente

## Desafios de aprendizagem associados

| Desafio | Categorias | Confiança | Contexto de ativação |
|---------|-----------|-----------|----------------------|
| D03 – Métodos | D03.03 | Média | Método acessa dados de outra classe para cálculo que deveria ser encapsulado |
| D05 – Relacionamentos | D05.01, D05.05 | Alta | Não modelou corretamente associações e dependências |
| D07 – Encapsulamento | D07.01, D07.05 | Alta | Não entende que classes não devem expor internos |

## Regras de disambiguação
- **Inappropriate Intimacy + Feature Envy** → Priorizar **D05.01**
- **Inappropriate Intimacy + Data Class** → Priorizar **D07.01**
- **Inappropriate Intimacy + Large Class** → Priorizar **D05.05**
- **Inappropriate Intimacy + Data Clump** → Priorizar **D07.05**
- **Inappropriate Intimacy isolado** → **D05.05**

## Intervenção pedagógica sugerida
- Ensinar Law of Demeter ("fale apenas com seus vizinhos imediatos")
- Exercícios de refatoração: Move Method / Hide Delegate
- Revisitar encapsulamento como comportamento, não apenas dados
