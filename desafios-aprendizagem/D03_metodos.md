# DESAFIO DE APRENDIZAGEM: D03 – Dificuldade em Compreender Métodos

**Código:** D03
**Referência base:** Gutiérrez, Guerrero e López-Ospina [12]

## Descrição do Desafio
O aluno não tem clareza sobre como fazer chamadas de métodos, não sabe determinar a quantidade necessária, não nomeia adequadamente e não entende como reutilizar métodos existentes.

## Categorias de Análise e Códigos

| Categoria | Código | Descrição |
|-----------|--------|-----------|
| Dificuldade em chamar métodos | D03.01 | Não sabe como chamar um método |
| Dificuldade em chamar métodos | D03.02 | Erros de sintaxe na chamada de método |
| Incerteza sobre quantidade e nome | D03.03 | Não sabe quantos métodos criar |
| Incerteza sobre quantidade e nome | D03.04 | Confusão na nomenclatura dos métodos |
| Falta de reuso de métodos | D03.05 | Não consegue reutilizar métodos existentes |
| Falta de reuso de métodos | D03.06 | Reescreve métodos desnecessariamente |
| Posicionamento incorreto | D03.07 | Coloca método na classe errada |
| Posicionamento incorreto | D03.08 | Método claramente pertence a outra classe |

## Indicadores no Código (Code Smells e SOLID)

| Indicador | Categorias sinalizadas | Confiança |
|-----------|----------------------|-----------|
| Message Chains | D03.01, D03.02 | Alta |
| Long Parameter List | D03.01, D03.02 | Alta |
| Data Clump | D03.01, D03.03 | Alta |
| Long Method | D03.03, D03.04 | Alta |
| Inappropriate Intimacy | D03.03 | Média |
| Duplicate Code | D03.05, D03.06 | Alta |
| Lazy Class | D03.05 | Média |
| Switch Statements | D03.05 | Média |
| Feature Envy | D03.07, D03.08 | Alta |
| Divergent Change | D03.07, D03.08 | Média |

## Perfil Típico do Aluno com D03
- Cria métodos muito longos que fazem várias coisas
- Copia e cola código em vez de chamar método existente
- Nomeia métodos de forma genérica ("metodo1", "processo", "fazer")
- Coloca lógica de uma classe dentro de outra sem critério
- Usa cadeias longas de chamadas para chegar a um valor

## Intervenções Pedagógicas Sugeridas
1. Exercícios de decomposição de método: identificar blocos com nome próprio
2. Praticar nomeação expressiva de métodos (verbo + substantivo)
3. Introduzir o princípio DRY antes de mostrar como extrair métodos
4. Exercícios: "esse método pertence a esta classe?"
5. Ensinar Law of Demeter para resolver Message Chains
