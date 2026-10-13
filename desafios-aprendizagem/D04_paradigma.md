# DESAFIO DE APRENDIZAGEM: D04 – Dificuldade em Implementar Orientação a Objetos

**Código:** D04
**Referência base:** Gutiérrez, Guerrero e López-Ospina [12]

## Descrição do Desafio
Aluno apresenta dificuldades ao adotar o paradigma OO. Background em programação estrutural leva a assimilar concepções errôneas. A natureza modular do paradigma é percebida como desafio, resultando em código procedural disfarçado de OO.

## Categorias de Análise e Códigos

| Categoria | Código | Descrição |
|-----------|--------|-----------|
| Transição procedural → OO | D04.01 | Domínio do pensamento estruturado |
| Análise e design OO | D04.02 | Design OO não realizado antes de implementar |
| Implementação de conceitos OO | D04.03 | Falhas na implementação de conceitos OO |
| Implementação de conceitos OO | D04.04 | Confusão na sintaxe OO |
| Misconceptions sobre OO | D04.05 | Misconceptions gerais sobre o paradigma |
| Misconceptions sobre OO | D04.06 | Confunde modularização com OO |

## Indicadores no Código (Code Smells e SOLID)

| Indicador | Categorias sinalizadas | Confiança |
|-----------|----------------------|-----------|
| Large Class | D04.01, D04.03, D04.05 | Alta |
| Long Method | D04.01 | Alta |
| Functional Decomposition | D04.01, D04.03, D04.05, D04.06 | Alta |
| Spaghetti Code | D04.01, D04.03, D04.05, D04.06 | Alta |
| Feature Envy | D04.02, D04.05, D04.06 | Alta |
| Shotgun Surgery | D04.02, D04.05 | Média |
| Cyclically-dependent Modularization | D04.02 | Média |
| Divergent Change | D04.03 | Média |
| Primitive Obsession | D04.03 | Alta |
| Swiss Army Knife | D04.03, D04.05, D04.06 | Alta |
| ISP violado | D04.03, D04.05 | Alta |
| DIP violado | D04.03, D04.05, D04.06 | Alta |

## Perfil Típico do Aluno com D04
- Tem background forte em C, Pascal ou outra linguagem procedural
- Usa classes apenas como "embrulho" para funções
- Não usa herança, polimorfismo ou interfaces de forma significativa
- Cria classe "main" ou "gerenciador" com toda a lógica do sistema
- Nomeia classes com verbos (ProcessarPedido, CalcularSalario)

## Intervenções Pedagógicas Sugeridas
1. Comparação explícita entre estilo procedural e OO no mesmo problema
2. Exercícios com CRC Cards (Class-Responsibility-Collaboration)
3. Revisitar fundamentos: objetos como entidades com estado e comportamento
4. Análise de domínio antes de qualquer codificação
5. Mostrar progressivamente como polimorfismo substitui condicionais
