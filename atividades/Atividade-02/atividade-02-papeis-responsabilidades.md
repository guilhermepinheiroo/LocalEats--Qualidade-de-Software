# Atividade 2: Organização da Qualidade no LocalEats

## 1. Identificação

- **Unidade Curricular:** Qualidade de Software
- **Metodologia:** Problem-Based Learning (PBL)
- **Projeto:** LocalEats
- **Modalidade:** Individual
- **Integrante:** Guilherme Pinheiro

## Tarefa 1 — Diagnóstico da situação

### Problemas organizacionais

| Problema identificado | Possível consequência para o produto ou para a equipe |
|---|---|
| As funcionalidades chegam aos usuários com defeitos. | Defeitos podem chegar à produção sem serem identificados previamente, prejudicando a experiência do usuário e aumentando o custo de correção. |
| Os critérios para considerar uma funcionalidade pronta não estão claros. | Diferentes integrantes podem considerar uma mesma funcionalidade concluída em momentos diferentes, permitindo que requisitos de qualidade ou testes ainda pendentes sejam ignorados. |
| Os defeitos são identificados, mas nem sempre são registrados ou acompanhados. | A equipe pode perder o histórico dos problemas, esquecer correções pendentes e não conseguir acompanhar adequadamente a situação dos defeitos. |

### A qualidade deve ser responsabilidade exclusiva do QA?

Não. A qualidade deve ser responsabilidade compartilhada entre os diferentes papéis envolvidos no desenvolvimento. O QA possui responsabilidades importantes de planejamento, análise e execução de testes, mas desenvolvedores, responsáveis pelo produto, analistas, liderança técnica e DevOps também influenciam diretamente a qualidade. A divisão clara das responsabilidades evita que problemas sejam descobertos somente no final do processo.

## Tarefa 2 — Papéis e competências

| Integrante | Papel analisado | Responsabilidades relacionadas à qualidade | Competências técnicas | Competências comportamentais |
|---|---|---|---|---|
| Guilherme Pinheiro | Responsável pelo produto (Product Owner) | Definir e priorizar requisitos; esclarecer critérios de aceitação; validar se o resultado atende às necessidades do usuário; priorizar defeitos conforme impacto no produto; participar da decisão de disponibilização de versões. | Levantamento e priorização de requisitos, critérios de aceitação, conhecimento do produto e análise de valor para o usuário. | Comunicação, visão de produto, tomada de decisão, organização e capacidade de negociação. |
| Guilherme Pinheiro | Analista de sistemas/negócio | Detalhar requisitos, identificar regras de negócio, esclarecer fluxos e apoiar a definição dos critérios de aceitação. | Análise de requisitos, modelagem de processos, documentação e compreensão das regras de negócio. | Pensamento analítico, comunicação, atenção aos detalhes e colaboração. |
| Guilherme Pinheiro | Desenvolvedor | Implementar funcionalidades conforme requisitos, criar testes unitários, corrigir defeitos, revisar código e contribuir para a prevenção de problemas. | Programação, testes unitários, controle de versão, revisão de código e depuração. | Responsabilidade, colaboração, organização e abertura para revisão. |
| Guilherme Pinheiro | QA / Analista de qualidade | Planejar testes, especificar e executar testes, analisar riscos, registrar defeitos, acompanhar resultados e apoiar a avaliação da qualidade antes da disponibilização. | Técnicas e níveis de teste, elaboração de casos de teste, análise de riscos, testes funcionais e gestão de defeitos. | Pensamento crítico, atenção aos detalhes, comunicação e imparcialidade na análise. |
| Guilherme Pinheiro | DevOps | Apoiar ambientes de teste e produção, automatizar etapas do processo de entrega, monitorar a disponibilização e contribuir para a estabilidade das versões. | CI/CD, gerenciamento de ambientes, automação, versionamento e monitoramento. | Organização, colaboração, responsabilidade e capacidade de resposta a incidentes. |
| Guilherme Pinheiro | Liderança técnica | Orientar decisões técnicas, apoiar revisões de código, garantir padrões técnicos e participar da avaliação de riscos técnicos e da disponibilização da versão. | Arquitetura, revisão de código, padrões de desenvolvimento, análise técnica de riscos e integração de ferramentas. | Liderança, comunicação, tomada de decisão, orientação da equipe e resolução de conflitos. |

## Tarefa 3 — Matriz RACI

**Legenda:** R = Responsável pela execução; A = Aprovador; C = Consultado; I = Informado.

| Atividade de qualidade | Responsável pelo produto | Analista | Desenvolvedor | QA | DevOps | Liderança técnica |
|---|---:|---:|---:|---:|---:|---:|
| Definir critérios de aceitação | **A** | **R** | C | C | I | C |
| Revisar requisitos | **A** | **R** | C | C | I | C |
| Implementar a funcionalidade | C | C | **R/A** | I | I | C |
| Revisar o código | I | I | **R** | C | I | **A** |
| Criar testes unitários | I | C | **R/A** | C | I | C |
| Planejar e executar testes do sistema | I | C | C | **R/A** | I | C |
| Registrar e acompanhar defeitos | I | C | C | **R/A** | I | I |
| Priorizar a correção dos defeitos | **A** | C | C | **R** | I | C |
| Aprovar a disponibilização da versão | **A** | I | C | C | **R** | C |

### Lacuna ou conflito encontrado

Um ponto que exige atenção é a aprovação da disponibilização da versão. O DevOps executa as atividades técnicas de entrega, mas não deve ser o único responsável por decidir se a versão está adequada para o usuário. Por isso, a matriz atribui **R ao DevOps** para a disponibilização técnica e **A ao responsável pelo produto** para a decisão final. QA e liderança técnica são consultados para fornecer informações de qualidade e riscos.

Outra situação relevante é a revisão de código: o desenvolvedor participa da execução da revisão, enquanto a liderança técnica possui a responsabilidade final pela decisão técnica. Isso evita concentrar todas as atividades de qualidade no QA.

## Práticas recomendadas

| Prática recomendada | Problema que ajuda a resolver | Papéis envolvidos |
|---|---|---|
| **Definição de Pronto (Definition of Done) com critérios de aceitação e testes mínimos** | Reduz a falta de clareza sobre quando uma funcionalidade pode ser considerada concluída e diminui a possibilidade de funcionalidades incompletas chegarem à entrega. | Responsável pelo produto, analista, desenvolvedor, QA e liderança técnica. |
| **Registro e acompanhamento de defeitos em uma ferramenta compartilhada, com prioridade e responsável definidos** | Evita que defeitos identificados sejam esquecidos ou não acompanhados e deixa claro quem deve atuar em cada correção. | QA, desenvolvedor, responsável pelo produto e liderança técnica. |

## Uso de inteligência artificial

**Ferramenta utilizada:** ChatGPT.

**Como foi utilizada:** utilizada como apoio para interpretar o cenário do LocalEats, estruturar os papéis, sugerir responsabilidades e organizar a matriz RACI.

**Como as respostas foram verificadas:** as propostas foram comparadas com as regras fornecidas na atividade, principalmente a exigência de responsabilidade compartilhada e as regras da matriz RACI: cada atividade possui pelo menos um R e exatamente um A.
