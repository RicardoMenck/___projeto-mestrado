# DESAFIO DE APRENDIZAGEM: D02 – Dificuldade em Compreender Classes

**Código:** D02
**Referência base:** Gutiérrez, Guerrero e López-Ospina [12]

## Descrição do Desafio
O aluno não assimilou a natureza abstrata de classes. Apresenta dificuldade em compreender hierarquia de classes, em identificar as classes corretas para um problema e em distinguir entre classe e objeto. Frequentemente trata a classe como coleção de objetos ou como estrutura de dados simples.

## Categorias de Análise e Códigos

| Categoria | Código | Descrição |
|-----------|--------|-----------|
| Natureza estática da classe | D02.01 | Não assimila que a classe é um modelo estático |
| Compreensão de hierarquia | D02.02 | Não cria hierarquia de classes |
| Compreensão de hierarquia | D02.03 | Coloca abstração no nível errado |
| Identificação de classes corretas | D02.04 | Não consegue identificar as classes adequadas |
| Identificação de classes corretas | D02.05 | Usa objetos do mundo real diretamente como classe |
| Confusão entre classe e objeto | D02.06 | Trata classe como objeto individual |
| Classe como coleção de objetos | D02.07 | Vê classe como coleção |
| Classe como coleção de objetos | D02.08 | Não aplica abstração na definição da classe |

## Indicadores no Código (Code Smells e SOLID)

| Indicador | Categorias sinalizadas | Confiança |
|-----------|----------------------|-----------|
| Large Class | D02.02, D02.03, D02.04, D02.05, D02.06 | Alta |
| Data Class | D02.01, D02.06, D02.07, D02.08 | Alta |
| Speculative Generality | D02.01 | Média |
| Refused Bequest | D02.02, D02.03 | Alta |
| Cyclically-dependent Modularization | D02.02 | Média |
| Parallel Inheritance Hierarchies | D02.02 | Alta |
| Shotgun Surgery | D02.04 | Média |
| Swiss Army Knife | D02.04 | Alta |
| Alternative Classes with Different Interfaces | D02.04 | Alta |
| Deficient Encapsulation | D02.06 | Média |
| Feature Envy | D02.07, D02.08 | Média |
| Interface Segregation Principle (violação) | D02.04 | Alta |

## Perfil Típico do Aluno com D02
- Cria uma ou duas classes grandes em vez de várias menores e coesas
- Nomeia classes de forma vaga ("Sistema", "Gerenciador", "Utils")
- Não consegue justificar por que separou (ou não) as classes
- Confunde instância com definição de classe
- Modela classes espelhando objetos físicos sem abstração

## Intervenções Pedagógicas Sugeridas
1. Exercícios de modelagem (UML/CRC Cards) antes de codificar
2. Prática de identificar substantivos do domínio como candidatos a classes
3. Exercícios de distinção entre classe e objeto com exemplos concretos
4. Revisitar o conceito de abstração progressivamente
5. Análise crítica do código próprio: "o que essa classe representa?"
