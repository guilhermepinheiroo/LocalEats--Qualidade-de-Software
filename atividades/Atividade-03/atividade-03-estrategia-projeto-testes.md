# Atividade 3: Estratégia e Projeto de Testes do LocalEats

## 1. Identificação

- **Unidade Curricular:** Qualidade de Software
- **Metodologia:** Problem-Based Learning (PBL)
- **Projeto:** LocalEats
- **Modalidade:** Individual
- **Integrante:** Guilherme Pinheiro

## Tarefa 1 — Planejamento dos testes

### 1.1 Objetivo dos testes

Verificar se o LocalEats permite que usuários autenticados realizem pedidos somente quando as condições necessárias estiverem atendidas, evitando pedidos sem dados válidos ou realizados em condições não permitidas. Os testes também devem verificar se o sistema apresenta respostas claras quando uma condição necessária para o pedido não é atendida.

### 1.2 Escopo

| Integrante | Funcionalidade incluída | O que será verificado |
|---|---|---|
| Guilherme Pinheiro | Fazer pedido | Condições necessárias para concluir um pedido, comportamento com dados válidos e tratamento de situações inválidas ou incompletas. |

| Funcionalidade não incluída | Justificativa |
|---|---|
| Criar conta | Não faz parte do fluxo escolhido para o planejamento dos testes de realização de pedidos. |

### 1.3 Abordagem

| Item | Decisão da equipe | Justificativa |
|---|---|---|
| Níveis de teste | Teste de sistema | O fluxo de realização do pedido será analisado pela interface, considerando a interação do usuário com a aplicação. |
| Tipos de teste | Funcional | O objetivo é verificar se as regras e comportamentos esperados da funcionalidade de pedido são atendidos. |
| Perspectiva caixa-preta ou caixa-branca | Caixa-preta | Serão avaliadas entradas, condições e resultados observáveis, sem depender da implementação interna do código. |
| Técnicas de teste | Particionamento de equivalência e tabela de decisão | O particionamento permite representar situações válidas e inválidas de entrada. A tabela de decisão é adequada para verificar combinações de condições, como autenticação e existência de dados necessários para o pedido. |

### 1.4 Ambiente e responsabilidades

| Item | Definição |
|---|---|
| Ambiente necessário | Aplicação LocalEats disponível em `https://local-eats-unisenac.vercel.app/`, navegador web em computador ou dispositivo compatível, conexão com a internet, conta de teste e dados necessários para realizar um pedido. |
| Responsável pelo planejamento | Guilherme Pinheiro |
| Responsável pela especificação dos casos | Guilherme Pinheiro |
| Responsável pela futura execução | Guilherme Pinheiro |

### 1.5 Critérios

| Critério | Definição |
|---|---|
| Entrada | Aplicação disponível, usuário de teste disponível e dados necessários para realizar um pedido disponíveis. |
| Saída | Todos os casos de teste planejados foram executados e os resultados foram registrados. |
| Suspensão | Aplicação indisponível, impossibilidade de autenticar a conta de teste ou ausência dos dados necessários para realizar o fluxo de pedido. |

## Tarefa 2 — Riscos e técnicas de teste

### 2.1 Análise dos riscos

| ID | Integrante | Funcionalidade | Risco | Consequência | Probabilidade | Impacto | Prioridade | Justificativa |
|---|---|---|---|---|---|---|---|---|
| R01 | Guilherme Pinheiro | Fazer pedido | O sistema permitir que um usuário não autenticado conclua um pedido. | Um usuário sem autenticação poderia realizar uma ação que deveria depender da identificação da conta, comprometendo o controle do pedido e sua associação ao usuário correto. | Média | Alta | Alta | A ocorrência pode não ser frequente, mas o impacto é alto porque afeta diretamente o controle do fluxo de pedidos e a identificação do usuário. |
| R02 | Guilherme Pinheiro | Fazer pedido | O sistema permitir a conclusão de um pedido sem que os dados necessários para o pedido estejam válidos ou completos. | O pedido pode ser criado de forma inconsistente, gerar erro no fluxo ou causar uma experiência inadequada para o usuário. | Média | Alta | Alta | O pedido é uma funcionalidade central do LocalEats e dados inválidos ou incompletos podem impedir ou comprometer sua conclusão. |

### 2.2 Aplicação das técnicas

**Integrante responsável:** Guilherme Pinheiro  
**Funcionalidade:** Fazer pedido  
**Riscos relacionados:** R01 e R02

#### Técnica 1 — Tabela de decisão

**Por que a técnica foi escolhida?**

A realização de um pedido depende da combinação de condições. A tabela de decisão permite representar diferentes combinações de autenticação e disponibilidade de dados necessários e verificar o resultado esperado para cada combinação.

**Aplicação da técnica:**

| Regra | Usuário autenticado? | Dados necessários para o pedido válidos/completos? | Resultado esperado |
|---|---|---|---|
| 1 | Sim | Sim | Permitir a conclusão do pedido. |
| 2 | Sim | Não | Impedir a conclusão e solicitar/corrigir os dados necessários. |
| 3 | Não | Sim | Não permitir a conclusão do pedido e solicitar autenticação. |
| 4 | Não | Não | Não permitir a conclusão e solicitar autenticação/dados necessários conforme a situação. |

**Casos derivados:** CT01, CT02 e CT03.

#### Técnica 2 — Particionamento de equivalência

**Por que a técnica foi escolhida?**

A técnica permite dividir as entradas em classes válidas e inválidas, evitando a necessidade de testar todas as combinações possíveis. Para o fluxo de pedido, é relevante representar pelo menos uma situação em que os dados necessários estão completos e outra em que estão incompletos ou inválidos.

**Aplicação da técnica:**

| Classe | Situação | Valor representativo |
|---|---|---|
| Válida | Usuário autenticado e dados necessários do pedido completos | Conta de teste autenticada + pedido preenchido corretamente |
| Inválida | Usuário não autenticado | Sessão sem usuário autenticado |
| Inválida | Dados necessários do pedido incompletos ou inválidos | Pedido sem uma informação obrigatória |

**Casos derivados:** CT01, CT02 e CT03.

## Tarefa 3 — Casos de teste e rastreabilidade

### CT01: Permitir pedido com usuário autenticado e dados válidos

**Integrante responsável:** Guilherme Pinheiro  
**Funcionalidade:** Fazer pedido  
**Risco ou requisito relacionado:** R01 e R02  
**Técnica utilizada:** Tabela de decisão + particionamento de equivalência

**Pré-condição:**

O usuário possui uma conta de teste, está autenticado e existem dados válidos e completos para realizar um pedido.

**Dados de entrada:**

- Usuário: conta de teste autenticada.
- Dados do pedido: informações necessárias preenchidas corretamente.

**Passos:**

1. Acessar a aplicação LocalEats.
2. Entrar com a conta de teste.
3. Selecionar um restaurante disponível.
4. Selecionar os itens necessários para o pedido.
5. Informar/preencher os dados solicitados para concluir o pedido.
6. Confirmar o pedido.

**Resultado esperado:**

O sistema permite a conclusão do pedido e apresenta uma confirmação ou indicação observável de que o pedido foi realizado com sucesso.

---

### CT02: Impedir pedido quando o usuário não está autenticado

**Integrante responsável:** Guilherme Pinheiro  
**Funcionalidade:** Fazer pedido  
**Risco ou requisito relacionado:** R01  
**Técnica utilizada:** Tabela de decisão + particionamento de equivalência

**Pré-condição:**

Não existe uma sessão autenticada para o usuário.

**Dados de entrada:**

- Usuário: não autenticado.
- Dados do pedido: dados que, isoladamente, seriam suficientes para o pedido.

**Passos:**

1. Acessar a aplicação sem realizar autenticação.
2. Acessar o fluxo de realização de pedido, quando disponível.
3. Selecionar os dados necessários para um pedido.
4. Tentar confirmar o pedido.

**Resultado esperado:**

O sistema não conclui o pedido para o usuário não autenticado e solicita que o usuário realize a autenticação antes de continuar.

---

### CT03: Impedir pedido com dados necessários incompletos ou inválidos

**Integrante responsável:** Guilherme Pinheiro  
**Funcionalidade:** Fazer pedido  
**Risco ou requisito relacionado:** R02  
**Técnica utilizada:** Tabela de decisão + particionamento de equivalência

**Pré-condição:**

O usuário está autenticado e existe um restaurante disponível para realizar um pedido.

**Dados de entrada:**

- Usuário: conta de teste autenticada.
- Pedido: dados necessários incompletos ou inválidos.

**Passos:**

1. Acessar a aplicação com o usuário autenticado.
2. Selecionar um restaurante disponível.
3. Iniciar a realização de um pedido.
4. Deixar pelo menos um dado necessário sem preenchimento ou informar um valor inválido.
5. Tentar confirmar o pedido.

**Resultado esperado:**

O sistema não conclui o pedido enquanto os dados necessários estiverem incompletos ou inválidos e apresenta uma indicação compreensível do que precisa ser corrigido.

## 3.2 Matriz de rastreabilidade

| Integrante | Funcionalidade | Risco ou requisito | Técnica utilizada | Casos de teste |
|---|---|---|---|---|
| Guilherme Pinheiro | Fazer pedido | R01: permitir pedido sem autenticação | Tabela de decisão + particionamento de equivalência | CT01 e CT02 |
| Guilherme Pinheiro | Fazer pedido | R02: permitir pedido com dados incompletos ou inválidos | Tabela de decisão + particionamento de equivalência | CT01 e CT03 |

A matriz demonstra que os dois riscos identificados possuem casos de teste relacionados e que os casos foram derivados das técnicas escolhidas.

## Uso de inteligência artificial

**Ferramenta utilizada:** ChatGPT.

**Como foi utilizada:** utilizada como apoio para interpretar as etapas do planejamento, sugerir riscos relacionados à funcionalidade de pedidos, selecionar técnicas adequadas e estruturar os casos de teste e a matriz de rastreabilidade.

**Uma sugestão que precisou ser alterada ou rejeitada:** as sugestões foram ajustadas para não tratar como fato nenhum comportamento interno do LocalEats que não estivesse especificado no enunciado. Os casos foram descritos como planejamento, sem apresentar resultados de execução.

**Como as respostas foram verificadas:** as propostas foram comparadas com as funcionalidades, quantidades mínimas, técnicas permitidas e modelos de casos de teste definidos no arquivo da atividade.
