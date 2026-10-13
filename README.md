# RAG Document — Diagnóstico de Aprendizagem em POO via Análise de Código

## Visão Geral
Base de conhecimento para sistema RAG destinado a diagnosticar dificuldades de
aprendizagem em Programação Orientada a Objetos (POO) a partir da análise de
código-fonte de estudantes.

## Organização atual do workspace

O workspace contém dois conjuntos de artefatos com papéis diferentes:

- a raiz (`biblioteca-smells/`, `desafios-aprendizagem/`, `regras/` e `system_prompt.md`) é um acervo
  acadêmico preexistente e serve como fonte de pesquisa;

O acervo da raiz não é carregado automaticamente pela PoC. Nas etapas
apropriadas, apenas o conteúdo necessário será selecionado, revisado e adaptado
para a linguagem cautelosa exigida pela metodologia. Essa separação evita que a
primeira execução incorpore prematuramente disambiguação por co-smells,
diagnósticos D02–D07 ou outros elementos de um fluxo mais complexo.


## Fundamentação Teórica
Baseado no artigo:
> Menolli, A., & Strik, B. (2025). Educational Insights from Code: Mapping Learning
> Challenges in OOP through Code-Based Evidence. SBES '25, Recife, PE, Brazil.

## Estrutura
```
workspace/
├── README.md
├── AGENTS.MD
├── system_prompt.md
├── biblioteca-smells/          ← 27 arquivos (um por indicador)
├── desafios-aprendizagem/        ← 6 arquivos (D02 a D07)
├── regras/          ← disambiguacao.md + co_smells.md

```

## Desafios Cobertos

| Código | Desafio | Indicadores |
|--------|---------|------------|
| D02 | Dificuldade em compreender Classes | 12 |
| D03 | Dificuldade em compreender Métodos | 10 |
| D04 | Dificuldade em implementar OO | 12 |
| D05 | Dificuldade com Relacionamentos OO | 9 |
| D06 | Dificuldade com Polimorfismo | 4 |
| D07 | Dificuldade com Encapsulamento | 8 |

## Fluxo de Diagnóstico
```
Código do aluno
      ↓
LLM identifica smells (RAG busca chunks de biblioteca-smells/)
      ↓
RAG recupera regras de disambiguação (regras/)
      ↓
LLM mapeia smells → desafios (RAG busca desafios-aprendizagem/)
      ↓
Diagnóstico pedagógico estruturado
```

## Consultas Recomendadas para o Retriever
- Por nome do smell: "Large Class diagnóstico aprendizagem"
- Por desafio: "dificuldade polimorfismo código"
- Por categoria: "D06.01 Cannot Apply Polymorphism"
- Por regra: "disambiguação Large Class co-smells"

## Limitações (conforme artigo original)
1. Mapeamento baseado em análise qualitativa — pode conter viés
2. Um mesmo smell pode indicar múltiplos desafios — use regras de disambiguação
3. Fatores externos (motivação, design instrucional) não são capturados
4. Requer familiaridade do professor com indicadores de qualidade

## Extensões Futuras Sugeridas
- Adicionar exemplos de código Java/Python para cada smell
- Integrar com SonarQube, Checkstyle para extração automática de smells
- Desenvolver dashboard para professores rastrearem desafios por turma
- Estudos longitudinais para validar intervenções pedagógicas
