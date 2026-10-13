# DESAFIO DE APRENDIZAGEM: D06 – Dificuldade em Compreender Polimorfismo e Sobrecarga

**Código:** D06
**Referência base:** Gutiérrez, Guerrero e López-Ospina [12]

## Descrição do Desafio
Polimorfismo e sobrecarga apresentam alto nível de complexidade para iniciantes. O polimorfismo é abstrato demais sem exemplos concretos. A sobrecarga frequentemente é substituída por duplicação de código.

## Categorias de Análise e Códigos

| Categoria | Código | Descrição |
|-----------|--------|-----------|
| Polimorfismo | D06.01 | Não consegue aplicar polimorfismo |
| Sobrecarga de método | D06.02 | Não compreende sobrecarga |
| Sobrecarga de método | D06.03 | Duplica métodos em vez de sobrecarregar |

## Indicadores no Código (Code Smells e SOLID)

| Indicador | Categorias sinalizadas | Confiança |
|-----------|----------------------|-----------|
| Switch Statements | D06.01 | Alta |
| Refused Bequest | D06.01 | Média |
| Long Parameter List | D06.02 | Alta |
| Duplicate Code | D06.02, D06.03 | Alta |

## Smells relacionados (inferidos por co-ocorrência)
- Complicated Boolean Expression → reforça D06.01
- Conditional Complexity → reforça D06.01
- Unexploited Encapsulation → reforça D06.01
- Missing Hierarchy → hierarquia polimórfica ausente

## Perfil Típico do Aluno com D06
- Usa switch/case ou if-else em cascata para simular polimorfismo
- Cria métodos com nomes ligeiramente diferentes que fazem a mesma coisa
- Não entende que subclasses podem "ser usadas" onde a superclasse é esperada
- Copia e cola método com pequenas variações em vez de usar sobrecarga
- Usa verificação de instanceof explicitamente

## Intervenções Pedagógicas Sugeridas
1. Demonstrar progressivamente: sobrescrita → polimorfismo → substituição de Liskov
2. Refatoração guiada: Replace Conditional with Polymorphism
3. Exercícios de sobrecarga com variações de parâmetros
4. Mostrar concretamente como polimorfismo elimina a necessidade de switch
5. Exemplos do mundo real próximos do aluno (animais, formas geométricas)
