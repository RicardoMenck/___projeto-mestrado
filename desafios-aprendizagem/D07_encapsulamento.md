# DESAFIO DE APRENDIZAGEM: D07 – Dificuldade em Compreender Encapsulamento

**Código:** D07
**Referência base:** Gutiérrez, Guerrero e López-Ospina [12]

## Descrição do Desafio
O aluno apresenta concepções errôneas sobre encapsulamento, modularity e information hiding. Frequentemente o encapsulamento é entendido superficialmente como "usar private com getters/setters", sem compreender a ocultação de informação e a coesão de módulo.

## Categorias de Análise e Códigos

| Categoria | Código | Descrição |
|-----------|--------|-----------|
| Misconceptions sobre encapsulamento | D07.01 | Encapsulamento incompreendido em essência |
| Misconceptions sobre encapsulamento | D07.02 | Entendido apenas como "esconder" atributos |
| Falta de modularidade | D07.03 | Modularidade não aplicada |
| Falta de modularidade | D07.04 | Mistura concerns na mesma classe |
| Problemas com information hiding | D07.05 | Expõe estado interno |
| Problemas com information hiding | D07.06 | Usa atributos públicos |

## Indicadores no Código (Code Smells e SOLID)

| Indicador | Categorias sinalizadas | Confiança |
|-----------|----------------------|-----------|
| Data Class | D07.01, D07.05, D07.06 | Alta |
| Inappropriate Intimacy | D07.01, D07.05 | Alta |
| Deficient Encapsulation | D07.01, D07.05 | Alta |
| Large Class | D07.03 | Alta |
| Divergent Change | D07.03 | Alta |
| Alternative Classes with Different Interfaces | D07.03 | Média |
| ISP violado | D07.03 | Alta |
| Data Clump | D07.05 | Média |

## Perfil Típico do Aluno com D07
- Coloca todos os atributos como públicos ou cria getters/setters para tudo
- Acha que encapsulamento = private + getter + setter
- Não percebe que o comportamento também deve estar na classe
- Expõe coleções internas diretamente (retorna a lista interna por referência)
- Mistura responsabilidades completamente distintas na mesma classe

## Intervenções Pedagógicas Sugeridas
1. Mostrar que encapsulamento = dados + comportamento juntos
2. Demonstrar riscos de expor estado interno com exemplos práticos
3. Exercícios de invariantes de classe
4. Progressão: private → método de acesso → comportamento encapsulado
5. Information hiding: o que o cliente precisa saber vs. o que é interno
