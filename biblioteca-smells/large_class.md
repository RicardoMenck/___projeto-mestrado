# SMELL: Large Class

**Tipo:** Bloater / Design Smell
**Referência:** Fowler [9], Suryanarayana et al. [52]
**Categoria:** Implementação e Design

## Descrição
Classe que centralizou responsabilidades demais, tornando-se excessivamente grande e difícil de manter. Viola o Princípio da Responsabilidade Única (SRP).

## Como reconhecer no código
- Classe com mais de 200–300 linhas (referência contextual)
- Métodos cobrindo domínios completamente distintos (ex: autenticação + relatório + cálculo)
- Muitos atributos sem coesão entre si
- Métodos que manipulam dados de outras classes
- Impossibilidade de nomear a classe com uma responsabilidade única

## Desafios de aprendizagem associados

| Desafio | Categorias | Confiança | Contexto de ativação |
|---------|-----------|-----------|----------------------|
| D02 – Classes | D02.02, D02.03, D02.04, D02.05, D02.06 | Alta | Classe mistura conceitos de domínios distintos sem critério de abstração |
| D04 – Paradigma OO | D04.01, D04.03, D04.05 | Alta | Métodos longos e sequenciais com lógica procedural |
| D05 – Relacionamentos | D05.05 | Média | Classe faz o trabalho que deveria ser de composição/agregação |
| D07 – Encapsulamento | D07.03 | Média | Atributos públicos e responsabilidades completamente misturadas |

## Regras de disambiguação
- **Large Class + Functional Decomposition + Spaghetti Code** → Priorizar **D04.01**
- **Large Class + Data Class + Deficient Encapsulation** → Priorizar **D02.06**
- **Large Class + Inappropriate Intimacy + Feature Envy** → Priorizar **D05.05**
- **Large Class + Divergent Change + atributos públicos** → Priorizar **D07.03**
- **Large Class isolado** → Priorizar **D02.04**

## Co-smells relacionados
- Spaghetti Code → reforça D04
- Shotgun Surgery → reforça D02, D05
- Feature Envy → reforça D05
- Divergent Change → reforça D07
- Data Class → reforça D02

## Smells relacionados (inferidos)
- Blob / Brain Class / God Class — variantes mais graves

## Perguntas para refinamento diagnóstico
1. Os métodos seguem lógica sequencial como funções procedurais?
2. A classe foi crescendo gradualmente ou já nasceu grande?
3. O aluno consegue explicar com uma frase curta o que a classe representa?
4. Os atributos têm relação semântica entre si?

## Intervenção pedagógica sugerida
- Exercícios de modelagem (UML) antes de codificar
- Praticar identificação de responsabilidades únicas (SRP)
- Refatoração guiada: extrair classes a partir da Large Class
- Revisitar o conceito de abstração com exemplos do domínio real
