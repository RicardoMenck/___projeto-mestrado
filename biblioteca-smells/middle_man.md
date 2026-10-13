# SMELL: Middle Man

**Tipo:** Code Smell (Coupler)
**Referência:** Fowler [9]
**Categoria:** Implementação

## Descrição
Classe que delega a maioria de seu trabalho para outra classe, adicionando camada de indireção desnecessária. Existe apenas para repassar chamadas.

## Como reconhecer no código
- A maioria dos métodos da classe apenas chama o correspondente de outro objeto
- Classe como "wrapper" sem comportamento próprio
- Cadeia de delegações sem transformação de dados

## Desafios de aprendizagem associados

| Desafio | Categorias | Confiança | Contexto de ativação |
|---------|-----------|-----------|----------------------|
| D05 – Relacionamentos | D05.01, D05.02 | Alta | Não modelou corretamente associação/dependência — criou indireção desnecessária |

## Regras de disambiguação
- **Middle Man + Message Chains** → Priorizar **D05.01**
- **Middle Man + Inappropriate Intimacy** → Priorizar **D05.02**
- **Middle Man isolado** → **D05.01**

## Intervenção pedagógica sugerida
- Ensinar quando usar Façade vs. delegação desnecessária
- Exercícios de revisão de hierarquias de chamada
