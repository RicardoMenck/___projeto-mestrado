# SMELL: Swiss Army Knife

**Tipo:** Design Smell (Anti-Pattern)
**Referência:** Brown et al. [6]
**Categoria:** Design

## Descrição
Classe com muitas responsabilidades ou utilitários não relacionados. Viola o SRP de forma extrema — a classe tenta fazer tudo.

## Como reconhecer no código
- Classe chamada "Utils", "Helper", "Manager" com dezenas de métodos estáticos
- Classe que mistura persistência, regra de negócio, interface e log
- Interface com muitos métodos de naturezas completamente diferentes

## Desafios de aprendizagem associados

| Desafio | Categorias | Confiança | Contexto de ativação |
|---------|-----------|-----------|----------------------|
| D02 – Classes | D02.04 | Alta | Não sabe identificar classes corretas — coloca tudo em utilitária |
| D04 – Paradigma OO | D04.03, D04.05, D04.06 | Alta | Não assimilou que classes devem ter responsabilidades coesas |

## Regras de disambiguação
- **Swiss Army Knife + Large Class** → Priorizar **D04.05**
- **Swiss Army Knife + ISP violado** → Priorizar **D02.04**
- **Swiss Army Knife isolado** → **D04.03**

## Intervenção pedagógica sugerida
- Ensinar coesão de classe como conceito central
- Exercícios de distribuição de responsabilidades entre classes
- Revisar Interface Segregation Principle (ISP)
