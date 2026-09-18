# 1 INTEGRAÇÃO

**Plano de Gerenciamento da Integração**
**Projeto:** COGME — Conversor de Ganhos em Moeda Estrangeira
**Versão:** 1.0
**Data:** 19/09/2026
**Autores:** Leonardo David Silva Setti (GP), Fabricio de Lima Cabral, Edson Luis Silva
**Stakeholder-Avaliador:** Prof. Dr. Nivaldo Carleto — Fatec Taquaritinga / ADS

> *Este plano deriva diretamente das Premissas P1 (governança híbrida), P3 (SDD com LLM), P4 (código como deliverable) e P7 (stakeholder-avaliador único nos marcos), e das Restrições de Cronograma e Custo do TAP, respeitando o Domínio de Abordagem de Desenvolvimento e o Domínio de Trabalho do Projeto do PMBOK® 7ª edição.*

---

## 1.1 Identificação e Propósito

Este Plano de Gerenciamento da Integração coordena a execução integrada do projeto COGME, garantindo que os sete planos de área subsequentes (Escopo, Cronograma, Custos, Qualidade, Recursos, Comunicações e Riscos), o código-fonte e os artefatos de governança permaneçam coerentes com os Objetivos SMART aprovados no TAP.

**Função ontológica:** O TAP *autoriza*; este plano *coordena*. Ele não duplica conteúdo do TAP — define os mecanismos de coerência entre todos os artefatos do ciclo de vida.

- **Domínio PMBOK 7ª:** Abordagem de Desenvolvimento.
- **Processo PMBOK 6ª (dicionário, obsolescência assumida):** 4.2 — Desenvolver o Plano de Gerenciamento do Projeto.

---

## 1.2 Modelo de Governança Híbrida

O projeto adota um modelo trifásico de governança, declarado no TAP (§1.c):

| Camada                   | Fonte Normativa                                                                  | Função no COGME                                              |
| ------------------------ | -------------------------------------------------------------------------------- | -------------------------------------------------------------- |
| Governança primária    | PMBOK® 7ª edição — 12 Princípios + 8 Domínios de Desempenho               | Define*por que* e *para quê*; orienta decisões por valor |
| Dicionário complementar | PMBOK® 6ª edição — processos citados apenas para rastreabilidade acadêmica | Fornece vocabulário estrutural quando necessário             |
| Método de execução    | Manifesto Ágil (4 valores) + Kanban (fluxo contínuo)                           | Define*como* o trabalho é executado diariamente             |

### 1.2.1 Hierarquia de Resolução de Conflitos

Em caso de conflito entre fontes normativas, aplica-se a seguinte ordem de precedência:

1. Valor entregue ao usuário final (Domínio de Entrega — PMBOK 7ª)
2. Ementa da disciplina + orientação do Prof. Dr. Nivaldo Carleto
3. PMBOK® 7ª edição (princípios e domínios)
4. Manifesto Ágil + Kanban (método de execução)
5. PMBOK® 6ª edição (dicionário de processos)

**Trade-off declarado:** Esta hierarquia favorece velocidade de entrega sobre completude documental, alinhada ao Princípio "Foco em Valor" (PMBOK 7ª) e ao Valor Ágil "Software funcionando sobre documentação abrangente".

### 1.2.2 Papéis de Governança

| Papel                   | Titular                                   | Responsabilidade                                                                                                    |
| ----------------------- | ----------------------------------------- | ------------------------------------------------------------------------------------------------------------------- |
| Gerente de Projeto (GP) | Leonardo David Silva Setti                | Decisor operacional único; CCB de membro único; autoridade para aprovações, rejeições e controle de mudanças |
| Desenvolvedores         | Fabricio de Lima Cabral, Edson Luis Silva | Execução técnica; revisão em pares; self-report de carga horária                                               |
| Stakeholder-Avaliador   | Prof. Dr. Nivaldo Carleto                 | Avaliação acadêmica nos marcos M1–M4; sem ingerência em decisões operacionais                                 |

### 1.2.3 Governança Mínima Viável (GMV)

Todo artefato de governança deve justificar sua existência pelo teste GMV:

| Pergunta                                                             | Se SIM            | Se NÃO                  |
| -------------------------------------------------------------------- | ----------------- | ------------------------ |
| O Prof. Dr. Nivaldo Carleto exigirá este artefato na avaliação?   | Produzir completo | Simplificar ou eliminar  |
| Este artefato evita retrabalho futuro?                               | Produzir          | Avaliar custo-benefício |
| Este artefato é útil para a equipe (não apenas para avaliação)? | Produzir          | Eliminar                 |

Se ≥ 2 respostas forem NÃO, o artefato é candidato a simplificação ou eliminação. Decisão final do GP.

### 1.2.4 Obsolescência do PMBOK 6ª (Declaração Formal)

O PMBOK® 6ª edição (2017) é tratado exclusivamente como dicionário de processos. Processos preditivos são citados apenas para rastreabilidade acadêmica e blindagem terminológica. Métricas EVM (SPI/CPI) são declaradas **LEGADO — NÃO APLICÁVEIS**, substituídas por métricas de fluxo Kanban conforme ADR-003.

---

## 1.3 GitHub Projects como Fonte Única de Verdade (SSOT)

O repositório GitHub e seu módulo GitHub Projects constituem o artefato primário de integração, cronograma e monitoramento, conforme ADR-002. Esta decisão substitui qualquer ferramenta preditiva de planejamento como instrumento ativo.

**Justificativa:** Para uma equipe de 3 pessoas com fluxo contínuo, ferramentas preditivas impõem overhead de manutenção desproporcional ao valor gerado. O Kanban via GitHub Projects fornece visibilidade em tempo real, métricas nativas de fluxo e rastreabilidade automática via commits.

- **Domínio PMBOK 7ª:** Medição + Trabalho do Projeto.
- **Valor Ágil:** "Indivíduos e interações sobre processos e ferramentas."

### 1.3.1 Mapeamento Kanban ↔ Processos PMBOK 6ª

| Coluna Kanban (ADR-002) | Processo PMBOK 6ª                   | Domínio PMBOK 7ª | Regra Operacional                   |
| ----------------------- | ------------------------------------ | ------------------ | ----------------------------------- |
| Backlog                 | 5.2 Coletar Requisitos               | Planejamento       | Card criado com DoR pendente        |
| Ready (DoR)             | 4.3 Orientar Trabalho (preparação) | Trabalho           | DoR atendido; aguardando capacidade |
| In Progress             | 4.3 Orientar e Gerenciar Trabalho    | Trabalho           | WIP limit: máx. 3 cards/pessoa     |
| Code Review             | 4.5 Monitorar e Controlar            | Medição          | Revisão em pares obrigatória      |
| Done (DoD)              | 5.4 Criar EAP (aceite do pacote)     | Entrega            | DoD atendido; commit mergeado       |

### 1.3.2 Regras de Fluxo e Rituais

**Regras de fluxo (ADR-002):**

- **Pull system:** Cards migram para "In Progress" somente quando há capacidade disponível (WIP limit respeitado).
- **WIP limit:** 3 cards em "In Progress" por pessoa (Domínio de Equipe — prevenção de burnout, R3 do TAP §10).
- **SDD com LLM:** Código gerado com apoio de IA passa por revisão humana obrigatória antes do merge. Commits declaram co-autoria.

**Rituais (ADR-002):**

| Ritual            | Formato                            | Cadência | Duração |
| ----------------- | ---------------------------------- | --------- | --------- |
| Daily assíncrona | GitHub Issues                      | Diária   | 15 min    |
| Refinement        | Product Backlog (GitHub Projects)  | Semanal   | 30 min    |
| Retrospectiva     | Risk backlog + lições aprendidas | Quinzenal | 30 min    |

**Nota:** Sprints time-boxed NÃO são utilizadas. O fluxo é contínuo (ADR-002).

---

## 1.4 Desenvolvimento e Manutenção do Plano de Gerenciamento

**Processo PMBOK 6ª (dicionário):** 4.2 — Desenvolver o Plano de Gerenciamento do Projeto.

Os oito planos de área são versionados no repositório GitHub sob `/docs/`. Cada plano:

- Inicia com frase de rastreabilidade ao TAP (Premissa + Restrição + Domínio PMBOK 7ª).
- Possui extensão máxima de 4 páginas (princípio GMV).
- É versionado via Conventional Commits: `docs(plano-integracao): atualização §X`.
- Passa por revisão em pares antes de ser considerado "Done".

**Regra de coerência cruzada:** Nenhum plano pode contradizer datas de marcos (M1–M4), premissas (P1–P8) ou restrições (§8) do TAP. Inconsistências detectadas em revisão acionam correção imediata antes do merge.

---

## 1.5 Orientação e Gestão do Trabalho do Projeto

**Processo PMBOK 6ª (dicionário):** 4.3 — Orientar e Gerenciar o Trabalho do Projeto.
**Domínio PMBOK 7ª:** Trabalho do Projeto.

### 1.5.1 Execução Diária

- Trabalho puxado do backlog conforme capacidade (pull system).
- Cada card no GitHub Projects possui: título padronizado (ex: `N5.1 — Backend: Lógica de Negócio`), label de fase, responsável e critério de aceite.
- Commits seguem Conventional Commits (`feat`, `fix`, `docs`, `test`, `ci`, `chore`).

### 1.5.2 Gestão do Conhecimento

**Processo PMBOK 6ª (dicionário):** 4.4 — Gerenciar o Conhecimento do Projeto.

- Estrutura de conhecimento: `/docs/` no repositório (planos, diagramas, lições aprendidas, catálogo de prompts SDD).
- Lições aprendidas registradas ao final de cada macro-fase (MF1, MF2, MF3).
- Decisões que afetam ≥ 2 fases da EAP, envolvem troca de tecnologia ou seriam questionadas pelo Prof. Dr. Nivaldo Carleto em avaliação são formalmente registradas via **ADR** (Architecture Decision Record), conforme REQ-12 e fase N9.1 da EAP. Decisões menores ficam em commit messages.

---

## 1.6 Monitoramento e Controle Integrado

**Processo PMBOK 6ª (dicionário):** 4.5 — Monitorar e Controlar o Trabalho do Projeto.
**Domínio PMBOK 7ª:** Medição.

### 1.6.1 Métricas de Fluxo Kanban (Oficiais — ADR-003)

Dada a restrição de orçamento zero (TAP §11), o Earned Value Management é inaplicável. As métricas de desempenho são exclusivamente baseadas no fluxo Kanban:

| Métrica                      | Definição                                        | Meta (pós-calibração) | Frequência   |
| ----------------------------- | -------------------------------------------------- | ------------------------ | ------------- |
| Cycle Time                    | Tempo médio de um card do "In Progress" ao "Done" | ≤ 3 dias                | Semanal       |
| Throughput                    | Cards concluídos por semana                       | ≥ 5 cards/semana        | Semanal       |
| CFD (Cumulative Flow Diagram) | Visualização de gargalos no fluxo                | Sem bandas largas        | Semanal       |
| WIP em fluxo                  | Cards ativos em "In Progress"                      | ≤ 9 (3 × 3 pessoas)    | Contínuo     |
| Coverage                      | Linhas testadas / linhas totais                    | ≥ 80%                   | Por push (CI) |
| Burnout (self-report)         | Carga horária semanal declarada                   | ≤ 20h/pessoa            | Semanal       |

### 1.6.2 Métricas Legado (Não Aplicáveis — ADR-003)

| Métrica                         | Status    | Justificativa                                               |
| -------------------------------- | --------- | ----------------------------------------------------------- |
| SPI (Schedule Performance Index) | ❌ LEGADO | Inaplicável — fluxo contínuo sem linha de base preditiva |
| CPI (Cost Performance Index)     | ❌ LEGADO | Inaplicável — orçamento zero (AC = 0)                    |
| EVM (Earned Value Management)    | ❌ LEGADO | Inaplicável — escopo emergente + orçamento nulo          |

### 1.6.3 Período de Calibração

De 23/09/2026 a 03/10/2026, as métricas são coletadas sem meta fixa, estabelecendo a baseline empírica de desempenho real da equipe. Após calibração, metas são ajustadas com base na média observada ± 20% e formalizadas via ADR.

**Trade-off declarado:** Abre-se mão da formalidade EVM em favor de métricas acionáveis e nativas do método, conforme Domínio de Medição (PMBOK 7ª) e ADR-003.

---

## 1.7 Controle Integrado de Mudanças

**Processo PMBOK 6ª (dicionário):** 4.6 — Realizar o Controle Integrado de Mudanças.
**Domínio PMBOK 7ª:** Incerteza.

### 1.7.1 Autoridade de Mudança (CCB)

O Gerente de Projeto (Leonardo David Silva Setti) atua como Change Control Board (CCB) de membro único, com autoridade formal delegada pelo TAP (§1.b, §9 P7). O Prof. Dr. Nivaldo Carleto não participa do fluxo de aprovação de mudanças; sua atuação restringe-se à avaliação acadêmica nos marcos M1–M4.

### 1.7.2 Fluxo de Solicitação de Mudança

| Etapa | Ação                                               | Responsável              | Prazo                    |
| ----- | ---------------------------------------------------- | ------------------------- | ------------------------ |
| 1     | Abertura de GitHub Issue com label`change-request` | Qualquer membro da equipe | Imediato                 |
| 2     | Análise de impacto (escopo, prazo, qualidade)       | GP (Leonardo)             | ≤ 48h                   |
| 3     | Aprovação ou rejeição via comentário na Issue   | GP (Leonardo)             | ≤ 24h após análise    |
| 4     | Atualização do backlog + planos afetados + commit  | Equipe                    | ≤ 24h após aprovação |

### 1.7.3 Limiar de Formalidade

- **Mudanças que NÃO alteram marcos (M1–M4) nem escopo do MVP:** Aprovadas pelo GP com registro em commit e comentário na Issue.
- **Mudanças que ALTERAM marcos ou escopo do MVP:** Aprovadas pelo GP com registro formal via ADR e comunicação ao Prof. Dr. Nivaldo Carleto no marco de avaliação subsequente.

**Valor Ágil aplicado:** "Responder a mudanças sobre seguir um plano." O processo é leve, mas auditável.

---

## 1.8 Encerramento do Projeto ou Fase

**Processo PMBOK 6ª (dicionário):** 4.7 — Encerrar o Projeto ou Fase.
**Domínio PMBOK 7ª:** Entrega.

### 1.8.1 Critérios de Encerramento por Macro-Fase

| Macro-Fase          | Período            | Critério de Encerramento                                                                               |
| ------------------- | ------------------- | ------------------------------------------------------------------------------------------------------- |
| MF1: Fundação     | 01/09 – 30/09/2026 | TAP aprovado + 8 planos v0.1 + EAP sincronizada + Stack definida (ADR-001) + Ambiente configurado       |
| MF2: Construção   | 01/10 – 15/11/2026 | MVP funcional + ≥ 80% coverage + UAT aprovado + Pipeline CI verde                                      |
| MF3: Consolidação | 16/11 – 15/12/2026 | Documentação consolidada + Apresentação final + Validação acadêmica no marco M4 + Tag de release |

### 1.8.2 Encerramento Formal do Projeto

- Tag de release final no repositório GitHub.
- Lições aprendidas finais consolidadas.
- Verificação dos cinco Objetivos SMART do TAP §3.
- Validação acadêmica pelo Prof. Dr. Nivaldo Carleto no marco M4.

---

## 1.9 Condições de Fracasso e Escalation

Derivado do TAP §3.3 (Condições de Fracasso), os seguintes gatilhos acionam ação corretiva imediata pelo GP:

| Gatilho                                           | Ação                                                     |
| ------------------------------------------------- | ---------------------------------------------------------- |
| Desvio > 3 dias úteis em qualquer marco (M1–M4) | Issue`change-request` + proposta de replanejamento + ADR |
| Coverage < 70% por 2 semanas consecutivas         | Revisão de prioridade de testes + ajuste de escopo        |
| Burnout detectado (> 20h/semana por 2 semanas)    | Redução de WIP + redistribuição de cards               |
| Scope creep > 15% do backlog original             | Congelamento de novas features + CCB (GP)                  |
| MVP não funcional em homologação até M3       | Contingência técnica: redução de escopo não-crítico  |

**Nota:** Escalation ao Prof. Dr. Nivaldo Carleto ocorre apenas nos marcos de avaliação ou quando o GP identificar risco de não cumprimento dos critérios SMART do TAP §3.

---

## 1.10 Declaração de Rastreabilidade

| Seção             | Origem no TAP                            | Domínio PMBOK 7ª           | Processo PMBOK 6ª |
| ------------------- | ---------------------------------------- | ---------------------------- | ------------------ |
| 1.2 (Governança)   | §1.c + Premissa P1                      | Abordagem de Desenvolvimento | 4.1, 4.2           |
| 1.3 (GitHub SSOT)   | Premissa P1 + §3 (Métricas)            | Medição + Trabalho         | 4.3, 4.5           |
| 1.5 (Orientação)  | Premissas P3, P4, P5                     | Trabalho do Projeto          | 4.3, 4.4           |
| 1.6 (Monitoramento) | §3 (Métricas) + §11 (Orçamento zero) | Medição                    | 4.5                |
| 1.7 (Mudanças)     | §3.3 (Fracasso) + Premissa P7           | Incerteza                    | 4.6                |
| 1.8 (Encerramento)  | §6 (Marcos M1–M4)                      | Entrega                      | 4.7                |
| 1.9 (Escalation)    | §3.3 (Fracasso) + §10 (Riscos)         | Incerteza                    | 4.5, 4.6           |

**Verificação:** 100% das seções possuem rastreabilidade a ao menos uma premissa, restrição ou objetivo SMART do TAP.

---

## 1.11 Premissas e Restrições Aplicáveis

| Tipo              | Referência TAP                         | Impacto neste Plano                     |
| ----------------- | --------------------------------------- | --------------------------------------- |
| Premissa P1       | Governança híbrida                    | Fundamenta 1.2                          |
| Premissa P3       | SDD com LLM autorizado                  | Fundamenta 1.5.2                        |
| Premissa P5       | ≤ 20h/semana por membro                | Fundamenta 1.3.2 e 1.9                  |
| Premissa P6       | Hardware adequado e suficiente          | Fundamenta 1.3 (viabilidade local)      |
| Premissa P7       | Stakeholder-avaliador único nos marcos | Fundamenta 1.2.2 e 1.7.1                |
| Restrição §8.2 | Prazo letivo inegociável               | Fundamenta 1.9                          |
| Restrição §8.4 | Orçamento zero                         | Fundamenta 1.6.2 (inaplicabilidade EVM) |

---

## Controle de Versões

| Versão | Data       | Alteração      | Responsável         |
| ------- | ---------- | ---------------- | -------------------- |
| 1.0     | 19/09/2026 | Emissão inicial | Leonardo D. S. Setti |

---

*Fim da Seção 1 — Integração | COGME v1.0*

---

## CHECKLIST DE VALIDAÇÃO

- [X] Versões internas de artefatos removidas (TAP v3 → TAP, EAP v2.0 → EAP)
- [X] ACRs mantidos como identificadores únicos (ADR-001, ADR-002, ADR-003)
- [X] REQs mantidos como identificadores únicos (REQ-12)
- [X] Edições normativas preservadas (PMBOK® 7ª, PMBOK® 6ª)
- [X] Todas as menções: "Prof. Dr. Nivaldo Carleto" (nunca abreviado)
- [X] Zero menções a Gantt
- [X] CCB = GP Leonardo (membro único)
- [X] Prof. Dr. Nivaldo Carleto = avaliador nos marcos (sem ingerência operacional)
- [X] M4: "validação acadêmica" (não "Termo de Aceite assinado")
- [X] EVM declarado LEGADO — NÃO APLICÁVEL (ADR-003)
- [X] Obsolescência PMBOK 6ª declarada formalmente
- [X] Colunas Kanban alinhadas à ADR-002: Backlog → Ready (DoR) → In Progress → Code Review → Done (DoD)
- [X] Numeração hierárquica: 1, 1.1, 1.2, 1.2.1...
- [X] Frase de rastreabilidade inicial presente
- [X] Extensão ≤ 5 páginas
- [X] Zero meta-comentários sobre versões anteriores

---

*GP Sênior PMBOK 7ª / PMO — Co-Autor Crítico*
*Projeto COGME | Fatec Taquaritinga | 19/09/2026*
*Faltam 3 dias úteis para o Marco M1 (22/09/2026)*

# ANÁLISE — RODADA 4 (GP Leonardo)

## Contexto da Rodada

Todos os artefatos de referência foram convergidos: TAP v3 (18/09), OKB v2.2 (19/09), Glossário v2.2 (19/09), ADRs 001–003 emitidas. Não há mais divergência entre documentos. O Plano de Integração pode ser redigido como documento **limpo, assertivo e autossuficiente**, sem notas de transição ou reinterpretação.

## Pontos de Alinhamento Confirmados

| Item                      | Estado Convergente                                                 | Fonte                                |
| ------------------------- | ------------------------------------------------------------------ | ------------------------------------ |
| CCB                       | GP Leonardo — membro único                                       | TAP v3 §1.c, OKB §1.2, P7          |
| Prof. Dr. Nivaldo Carleto | Avaliador acadêmico nos marcos M1–M4                             | TAP v3, OKB §1.2                    |
| EVM (SPI/CPI)             | LEGADO — NÃO APLICÁVEL                                          | OKB §1.3, ADR-003, Glossário §5.2 |
| PMBOK 6ª                 | Obsolescência assumida (dicionário)                              | OKB §1.3, Glossário §3            |
| Colunas Kanban            | Backlog → Ready (DoR) → In Progress → Code Review → Done (DoD) | ADR-002                              |
| EAP                       | 12 fases + 37 pacotes Nível 2                                     | TAP v3 §4                           |
| Hardware                  | Adequado e suficiente (P6 revisada)                                | TAP v3 §9, hardware.md              |
| M4                        | Validação acadêmica (não "Termo de Aceite assinado")           | TAP v3 §6                           |
| ADRs                      | Artefatos formais do projeto (N9.1, REQ-12)                        | TAP v3 §5, OKB §4                  |

## Decisão de Redação

Nenhum conflito residual. Procedo à redação integral.

---

# 1 INTEGRAÇÃO

**Plano de Gerenciamento da Integração**
**Projeto:** COGME — Conversor de Ganhos em Moeda Estrangeira
**Versão:** 1.0
**Data:** 19/09/2026
**Autores:** Leonardo David Silva Setti (GP), Fabricio de Lima Cabral, Edson Luis Silva
**Stakeholder-Avaliador:** Prof. Dr. Nivaldo Carleto — Fatec Taquaritinga / ADS

> *Este plano deriva diretamente das Premissas P1 (governança híbrida), P3 (SDD com LLM), P4 (código como deliverable) e P7 (stakeholder-avaliador único nos marcos), e das Restrições de Cronograma e Custo do TAP v3, respeitando o Domínio de Abordagem de Desenvolvimento e o Domínio de Trabalho do Projeto do PMBOK® 7ª edição.*

---

## 1.1 Identificação e Propósito

Este Plano de Gerenciamento da Integração coordena a execução integrada do projeto COGME, garantindo que os sete planos de área subsequentes (Escopo, Cronograma, Custos, Qualidade, Recursos, Comunicações e Riscos), o código-fonte e os artefatos de governança permaneçam coerentes com os Objetivos SMART aprovados no Termo de Abertura do Projeto (TAP v3).

**Função ontológica:** O TAP *autoriza*; este plano *coordena*. Ele não duplica conteúdo do TAP — define os mecanismos de coerência entre todos os artefatos do ciclo de vida.

- **Domínio PMBOK 7ª:** Abordagem de Desenvolvimento.
- **Processo PMBOK 6ª (dicionário, obsolescência assumida):** 4.2 — Desenvolver o Plano de Gerenciamento do Projeto.

---

## 1.2 Modelo de Governança Híbrida

O projeto adota um modelo trifásico de governança, declarado no TAP v3 (§1.c):

| Camada                   | Fonte Normativa                                                                  | Função no COGME                                              |
| ------------------------ | -------------------------------------------------------------------------------- | -------------------------------------------------------------- |
| Governança primária    | PMBOK® 7ª edição — 12 Princípios + 8 Domínios de Desempenho               | Define*por que* e *para quê*; orienta decisões por valor |
| Dicionário complementar | PMBOK® 6ª edição — processos citados apenas para rastreabilidade acadêmica | Fornece vocabulário estrutural quando necessário             |
| Método de execução    | Manifesto Ágil (4 valores) + Kanban (fluxo contínuo)                           | Define*como* o trabalho é executado diariamente             |

### 1.2.1 Hierarquia de Resolução de Conflitos

Em caso de conflito entre fontes normativas, aplica-se a seguinte ordem de precedência:

1. Valor entregue ao usuário final (Domínio de Entrega — PMBOK 7ª)
2. Ementa da disciplina + orientação do Prof. Dr. Nivaldo Carleto
3. PMBOK® 7ª edição (princípios e domínios)
4. Manifesto Ágil + Kanban (método de execução)
5. PMBOK® 6ª edição (dicionário de processos)

**Trade-off declarado:** Esta hierarquia favorece velocidade de entrega sobre completude documental, alinhada ao Princípio "Foco em Valor" (PMBOK 7ª) e ao Valor Ágil "Software funcionando sobre documentação abrangente".

### 1.2.2 Papéis de Governança

| Papel                   | Titular                                   | Responsabilidade                                                                                                    |
| ----------------------- | ----------------------------------------- | ------------------------------------------------------------------------------------------------------------------- |
| Gerente de Projeto (GP) | Leonardo David Silva Setti                | Decisor operacional único; CCB de membro único; autoridade para aprovações, rejeições e controle de mudanças |
| Desenvolvedores         | Fabricio de Lima Cabral, Edson Luis Silva | Execução técnica; revisão em pares; self-report de carga horária                                               |
| Stakeholder-Avaliador   | Prof. Dr. Nivaldo Carleto                 | Avaliação acadêmica nos marcos M1–M4; sem ingerência em decisões operacionais                                 |

### 1.2.3 Governança Mínima Viável (GMV)

Todo artefato de governança deve justificar sua existência pelo teste GMV:

| Pergunta                                                             | Se SIM            | Se NÃO                  |
| -------------------------------------------------------------------- | ----------------- | ------------------------ |
| O Prof. Dr. Nivaldo Carleto exigirá este artefato na avaliação?   | Produzir completo | Simplificar ou eliminar  |
| Este artefato evita retrabalho futuro?                               | Produzir          | Avaliar custo-benefício |
| Este artefato é útil para a equipe (não apenas para avaliação)? | Produzir          | Eliminar                 |

Se ≥ 2 respostas forem NÃO, o artefato é candidato a simplificação ou eliminação. Decisão final do GP.

### 1.2.4 Obsolescência do PMBOK 6ª (Declaração Formal)

O PMBOK® 6ª edição (2017) é tratado exclusivamente como dicionário de processos. Processos preditivos são citados apenas para rastreabilidade acadêmica e blindagem terminológica. Métricas EVM (SPI/CPI) são declaradas **LEGADO — NÃO APLICÁVEIS**, substituídas por métricas de fluxo Kanban conforme ADR-003.

---

## 1.3 GitHub Projects como Fonte Única de Verdade (SSOT)

O repositório GitHub e seu módulo GitHub Projects constituem o artefato primário de integração, cronograma e monitoramento, conforme ADR-002. Esta decisão substitui qualquer ferramenta preditiva de planejamento como instrumento ativo.

**Justificativa:** Para uma equipe de 3 pessoas com fluxo contínuo, ferramentas preditivas impõem overhead de manutenção desproporcional ao valor gerado. O Kanban via GitHub Projects fornece visibilidade em tempo real, métricas nativas de fluxo e rastreabilidade automática via commits.

- **Domínio PMBOK 7ª:** Medição + Trabalho do Projeto.
- **Valor Ágil:** "Indivíduos e interações sobre processos e ferramentas."

### 1.3.1 Mapeamento Kanban ↔ Processos PMBOK 6ª

| Coluna Kanban (ADR-002) | Processo PMBOK 6ª                   | Domínio PMBOK 7ª | Regra Operacional                   |
| ----------------------- | ------------------------------------ | ------------------ | ----------------------------------- |
| Backlog                 | 5.2 Coletar Requisitos               | Planejamento       | Card criado com DoR pendente        |
| Ready (DoR)             | 4.3 Orientar Trabalho (preparação) | Trabalho           | DoR atendido; aguardando capacidade |
| In Progress             | 4.3 Orientar e Gerenciar Trabalho    | Trabalho           | WIP limit: máx. 3 cards/pessoa     |
| Code Review             | 4.5 Monitorar e Controlar            | Medição          | Revisão em pares obrigatória      |
| Done (DoD)              | 5.4 Criar EAP (aceite do pacote)     | Entrega            | DoD atendido; commit mergeado       |

### 1.3.2 Regras de Fluxo e Rituais

**Regras de fluxo (ADR-002):**

- **Pull system:** Cards migram para "In Progress" somente quando há capacidade disponível (WIP limit respeitado).
- **WIP limit:** 3 cards em "In Progress" por pessoa (Domínio de Equipe — prevenção de burnout, R3 do TAP §10).
- **SDD com LLM:** Código gerado com apoio de IA passa por revisão humana obrigatória antes do merge. Commits declaram co-autoria.

**Rituais (ADR-002):**

| Ritual            | Formato                            | Cadência | Duração |
| ----------------- | ---------------------------------- | --------- | --------- |
| Daily assíncrona | GitHub Issues                      | Diária   | 15 min    |
| Refinement        | Product Backlog (GitHub Projects)  | Semanal   | 30 min    |
| Retrospectiva     | Risk backlog + lições aprendidas | Quinzenal | 30 min    |

**Nota:** Sprints time-boxed NÃO são utilizadas. O fluxo é contínuo (ADR-002).

---

## 1.4 Desenvolvimento e Manutenção do Plano de Gerenciamento

**Processo PMBOK 6ª (dicionário):** 4.2 — Desenvolver o Plano de Gerenciamento do Projeto.

Os oito planos de área são versionados no repositório GitHub sob `/docs/`. Cada plano:

- Inicia com frase de rastreabilidade ao TAP v3 (Premissa + Restrição + Domínio PMBOK 7ª).
- Possui extensão máxima de 4 páginas (princípio GMV).
- É versionado via Conventional Commits: `docs(plano-integracao): atualização §X`.
- Passa por revisão em pares antes de ser considerado "Done".

**Regra de coerência cruzada:** Nenhum plano pode contradizer datas de marcos (M1–M4), premissas (P1–P8) ou restrições (§8) do TAP v3. Inconsistências detectadas em revisão acionam correção imediata antes do merge.

---

## 1.5 Orientação e Gestão do Trabalho do Projeto

**Processo PMBOK 6ª (dicionário):** 4.3 — Orientar e Gerenciar o Trabalho do Projeto.
**Domínio PMBOK 7ª:** Trabalho do Projeto.

### 1.5.1 Execução Diária

- Trabalho puxado do backlog conforme capacidade (pull system).
- Cada card no GitHub Projects possui: título padronizado (ex: `N5.1 — Backend: Lógica de Negócio`), label de fase, responsável e critério de aceite.
- Commits seguem Conventional Commits (`feat`, `fix`, `docs`, `test`, `ci`, `chore`).

### 1.5.2 Gestão do Conhecimento

**Processo PMBOK 6ª (dicionário):** 4.4 — Gerenciar o Conhecimento do Projeto.

- Estrutura de conhecimento: `/docs/` no repositório (planos, diagramas, lições aprendidas, catálogo de prompts SDD).
- Lições aprendidas registradas ao final de cada macro-fase (MF1, MF2, MF3).
- Decisões que afetam ≥ 2 fases da EAP, envolvem troca de tecnologia ou seriam questionadas pelo Prof. Dr. Nivaldo Carleto em avaliação são formalmente registradas via **ADR** (Architecture Decision Record), conforme REQ-12 e fase N9.1 da EAP. Decisões menores ficam em commit messages.

---

## 1.6 Monitoramento e Controle Integrado

**Processo PMBOK 6ª (dicionário):** 4.5 — Monitorar e Controlar o Trabalho do Projeto.
**Domínio PMBOK 7ª:** Medição.

### 1.6.1 Métricas de Fluxo Kanban (Oficiais — ADR-003)

Dada a restrição de orçamento zero (TAP v3 §11), o Earned Value Management é inaplicável. As métricas de desempenho são exclusivamente baseadas no fluxo Kanban:

| Métrica                      | Definição                                        | Meta (pós-calibração) | Frequência   |
| ----------------------------- | -------------------------------------------------- | ------------------------ | ------------- |
| Cycle Time                    | Tempo médio de um card do "In Progress" ao "Done" | ≤ 3 dias                | Semanal       |
| Throughput                    | Cards concluídos por semana                       | ≥ 5 cards/semana        | Semanal       |
| CFD (Cumulative Flow Diagram) | Visualização de gargalos no fluxo                | Sem bandas largas        | Semanal       |
| WIP em fluxo                  | Cards ativos em "In Progress"                      | ≤ 9 (3 × 3 pessoas)    | Contínuo     |
| Coverage                      | Linhas testadas / linhas totais                    | ≥ 80%                   | Por push (CI) |
| Burnout (self-report)         | Carga horária semanal declarada                   | ≤ 20h/pessoa            | Semanal       |

### 1.6.2 Métricas Legado (Não Aplicáveis — ADR-003)

| Métrica                         | Status    | Justificativa                                               |
| -------------------------------- | --------- | ----------------------------------------------------------- |
| SPI (Schedule Performance Index) | ❌ LEGADO | Inaplicável — fluxo contínuo sem linha de base preditiva |
| CPI (Cost Performance Index)     | ❌ LEGADO | Inaplicável — orçamento zero (AC = 0)                    |
| EVM (Earned Value Management)    | ❌ LEGADO | Inaplicável — escopo emergente + orçamento nulo          |

### 1.6.3 Período de Calibração

De 23/09/2026 a 03/10/2026, as métricas são coletadas sem meta fixa, estabelecendo a baseline empírica de desempenho real da equipe. Após calibração, metas são ajustadas com base na média observada ± 20% e formalizadas via ADR.

**Trade-off declarado:** Abre-se mão da formalidade EVM em favor de métricas acionáveis e nativas do método, conforme Domínio de Medição (PMBOK 7ª) e ADR-003.

---

## 1.7 Controle Integrado de Mudanças

**Processo PMBOK 6ª (dicionário):** 4.6 — Realizar o Controle Integrado de Mudanças.
**Domínio PMBOK 7ª:** Incerteza.

### 1.7.1 Autoridade de Mudança (CCB)

O Gerente de Projeto (Leonardo David Silva Setti) atua como Change Control Board (CCB) de membro único, com autoridade formal delegada pelo TAP v3 (§1.b, §9 P7). O Prof. Dr. Nivaldo Carleto não participa do fluxo de aprovação de mudanças; sua atuação restringe-se à avaliação acadêmica nos marcos M1–M4.

### 1.7.2 Fluxo de Solicitação de Mudança

| Etapa | Ação                                               | Responsável              | Prazo                    |
| ----- | ---------------------------------------------------- | ------------------------- | ------------------------ |
| 1     | Abertura de GitHub Issue com label`change-request` | Qualquer membro da equipe | Imediato                 |
| 2     | Análise de impacto (escopo, prazo, qualidade)       | GP (Leonardo)             | ≤ 48h                   |
| 3     | Aprovação ou rejeição via comentário na Issue   | GP (Leonardo)             | ≤ 24h após análise    |
| 4     | Atualização do backlog + planos afetados + commit  | Equipe                    | ≤ 24h após aprovação |

### 1.7.3 Limiar de Formalidade

- **Mudanças que NÃO alteram marcos (M1–M4) nem escopo do MVP:** Aprovadas pelo GP com registro em commit e comentário na Issue.
- **Mudanças que ALTERAM marcos ou escopo do MVP:** Aprovadas pelo GP com registro formal via ADR e comunicação ao Prof. Dr. Nivaldo Carleto no marco de avaliação subsequente.

**Valor Ágil aplicado:** "Responder a mudanças sobre seguir um plano." O processo é leve, mas auditável.

---

## 1.8 Encerramento do Projeto ou Fase

**Processo PMBOK 6ª (dicionário):** 4.7 — Encerrar o Projeto ou Fase.
**Domínio PMBOK 7ª:** Entrega.

### 1.8.1 Critérios de Encerramento por Macro-Fase

| Macro-Fase          | Período            | Critério de Encerramento                                                                               |
| ------------------- | ------------------- | ------------------------------------------------------------------------------------------------------- |
| MF1: Fundação     | 01/09 – 30/09/2026 | TAP aprovado + 8 planos v0.1 + EAP sincronizada + Stack definida (ADR-001) + Ambiente configurado       |
| MF2: Construção   | 01/10 – 15/11/2026 | MVP funcional + ≥ 80% coverage + UAT aprovado + Pipeline CI verde                                      |
| MF3: Consolidação | 16/11 – 15/12/2026 | Documentação consolidada + Apresentação final + Validação acadêmica no marco M4 + Tag de release |

### 1.8.2 Encerramento Formal do Projeto

- Tag de release final no repositório GitHub.
- Lições aprendidas finais consolidadas.
- Verificação dos cinco Objetivos SMART do TAP v3 §3.
- Validação acadêmica pelo Prof. Dr. Nivaldo Carleto no marco M4.

---

## 1.9 Condições de Fracasso e Escalation

Derivado do TAP v3 §3.3 (Condições de Fracasso), os seguintes gatilhos acionam ação corretiva imediata pelo GP:

| Gatilho                                           | Ação                                                     |
| ------------------------------------------------- | ---------------------------------------------------------- |
| Desvio > 3 dias úteis em qualquer marco (M1–M4) | Issue`change-request` + proposta de replanejamento + ADR |
| Coverage < 70% por 2 semanas consecutivas         | Revisão de prioridade de testes + ajuste de escopo        |
| Burnout detectado (> 20h/semana por 2 semanas)    | Redução de WIP + redistribuição de cards               |
| Scope creep > 15% do backlog original             | Congelamento de novas features + CCB (GP)                  |
| MVP não funcional em homologação até M3       | Contingência técnica: redução de escopo não-crítico  |

**Nota:** Escalation ao Prof. Dr. Nivaldo Carleto ocorre apenas nos marcos de avaliação ou quando o GP identificar risco de não cumprimento dos critérios SMART do TAP v3 §3.

---

## 1.10 Declaração de Rastreabilidade

| Seção             | Origem no TAP v3                         | Domínio PMBOK 7ª           | Processo PMBOK 6ª |
| ------------------- | ---------------------------------------- | ---------------------------- | ------------------ |
| 1.2 (Governança)   | §1.c + Premissa P1                      | Abordagem de Desenvolvimento | 4.1, 4.2           |
| 1.3 (GitHub SSOT)   | Premissa P1 + §3 (Métricas)            | Medição + Trabalho         | 4.3, 4.5           |
| 1.5 (Orientação)  | Premissas P3, P4, P5                     | Trabalho do Projeto          | 4.3, 4.4           |
| 1.6 (Monitoramento) | §3 (Métricas) + §11 (Orçamento zero) | Medição                    | 4.5                |
| 1.7 (Mudanças)     | §3.3 (Fracasso) + Premissa P7           | Incerteza                    | 4.6                |
| 1.8 (Encerramento)  | §6 (Marcos M1–M4)                      | Entrega                      | 4.7                |
| 1.9 (Escalation)    | §3.3 (Fracasso) + §10 (Riscos)         | Incerteza                    | 4.5, 4.6           |

**Verificação:** 100% das seções possuem rastreabilidade a ao menos uma premissa, restrição ou objetivo SMART do TAP v3.

---

## 1.11 Premissas e Restrições Aplicáveis

| Tipo              | Referência TAP v3                      | Impacto neste Plano                     |
| ----------------- | --------------------------------------- | --------------------------------------- |
| Premissa P1       | Governança híbrida                    | Fundamenta 1.2                          |
| Premissa P3       | SDD com LLM autorizado                  | Fundamenta 1.5.2                        |
| Premissa P5       | ≤ 20h/semana por membro                | Fundamenta 1.3.2 e 1.9                  |
| Premissa P6       | Hardware adequado e suficiente          | Fundamenta 1.3 (viabilidade local)      |
| Premissa P7       | Stakeholder-avaliador único nos marcos | Fundamenta 1.2.2 e 1.7.1                |
| Restrição §8.2 | Prazo letivo inegociável               | Fundamenta 1.9                          |
| Restrição §8.4 | Orçamento zero                         | Fundamenta 1.6.2 (inaplicabilidade EVM) |

---

## Controle de Versões

| Versão | Data       | Alteração                                                          | Responsável         |
| ------- | ---------- | -------------------------------------------------------------------- | -------------------- |
| 1.0     | 19/09/2026 | Emissão inicial — convergente ao TAP v3 + OKB v2.2 + ADRs 001–003 | Leonardo D. S. Setti |

---

*Fim da Seção 1 — Integração | COGME v1.0*

---

## CHECKLIST DE VALIDAÇÃO

- [X] Todas as menções: "Prof. Dr. Nivaldo Carleto" (nunca abreviado)
- [X] Zero menções a Gantt
- [X] ADR referenciado como artefato formal do projeto (N9.1, REQ-12)
- [X] CCB = GP Leonardo (membro único)
- [X] Prof. Dr. Nivaldo Carleto = avaliador nos marcos (sem ingerência operacional)
- [X] M4: "validação acadêmica" (não "Termo de Aceite assinado")
- [X] EVM declarado LEGADO — NÃO APLICÁVEL (ADR-003)
- [X] Obsolescência PMBOK 6ª declarada formalmente
- [X] Colunas Kanban alinhadas à ADR-002: Backlog → Ready (DoR) → In Progress → Code Review → Done (DoD)
- [X] 37 pacotes EAP (TAP v3)
- [X] P6: hardware adequado e suficiente
- [X] Numeração hierárquica: 1, 1.1, 1.2, 1.2.1...
- [X] Frase de rastreabilidade inicial presente
- [X] Extensão ≤ 5 páginas
- [X] Zero meta-comentários sobre versões anteriores

---

*GP Sênior PMBOK 7ª / PMO — Co-Autor Crítico*
*Projeto COGME | Fatec Taquaritinga | 19/09/2026*
*Faltam 3 dias úteis para o Marco M1 (22/09/2026).*

# Seção 2 — Escopo (v0.1 para revisão em pares)

---

**2 ESCOPO**

**Plano de Gerenciamento do Escopo**

**Projeto:** COGME — Conversor de Ganhos em Moeda Estrangeira
**Versão:** 0.1 (revisão em pares)
**Data:** 19/09/2026
**Autores:** Leonardo David Silva Setti (GP), Fabricio de Lima Cabral, Edson Luis Silva
**Stakeholder-Avaliador:** Prof. Dr. Nivaldo Carleto — Fatec Taquaritinga / ADS

Este plano deriva diretamente das Premissas P1 (governança híbrida), P2 (FOSS absoluto), P4 (código como deliverable) e P8 (simplificação pedagógica), e das Restrições de Escopo, Cronograma e Qualidade do Termo de Abertura do Projeto (TAP), respeitando o Domínio de Planejamento e o Domínio de Entrega do PMBOK® 7ª edição.

### 2.1 Identificação e Propósito

Este Plano de Gerenciamento do Escopo define os mecanismos pelos quais o escopo do COGME será coletado, declarado, decomposto, validado e controlado ao longo do ciclo de vida. Sua função ontológica é complementar ao TAP e à Estrutura Analítica do Projeto (EAP) v2.0: enquanto o TAP autoriza o escopo de alto nível e a EAP o decompõe estruturalmente, este plano governa sua evolução e coerência com os Objetivos SMART aprovados.

O plano ancora-se em dois referenciais normativos: o Domínio de Planejamento e o Domínio de Entrega do PMBOK® 7ª edição, que orientam a evolução progressiva do escopo e a geração de valor; e, como dicionário complementar com obsolescência formalmente declarada, os processos 5.1 a 5.6 do PMBOK® 6ª edição.

### 2.2 Abordagem Híbrida de Gerenciamento do Escopo

Conforme Premissa P1 e ADR-002, o escopo é gerenciado em duas camadas complementares. A primeira, denominada linha de base estrutural, é materializada pela EAP v2.0, composta por 12 fases de Nível 1 e 37 pacotes de trabalho de Nível 2, e define o escopo obrigatório do MVP acadêmico. A segunda, denominada fluxo emergente, é operacionalizada pelo backlog Kanban no GitHub Projects, que define a ordem de execução e permite evolução progressiva.

O trade-off declarado nesta abordagem privilegia a completude acadêmica, garantida pela EAP, em detrimento da rigidez preditiva, e simultaneamente assegura adaptabilidade por meio do fluxo contínuo Kanban, em conformidade com o valor ágil "responder a mudanças sobre seguir um plano". Mudanças fora da EAP acionam o processo de controle integrado de mudanças definido no Plano de Integração, seção 1.7.

### 2.3 Coleta e Gestão de Requisitos

#### 2.3.1 Métodos de Levantamento

Os requisitos do COGME foram coletados por meio de duas técnicas complementares, em conformidade com o processo 5.2 do PMBOK® 6ª. A primeira técnica foi a análise de domínio, realizada a partir da identificação da dor do público-alvo — profissionais brasileiros que prestam serviços ao exterior em moeda estrangeira — e do mapeamento das ferramentas dispersas atualmente utilizadas para simulação cambial. A segunda técnica foi o brainstorm estruturado da equipe de projeto, do qual derivaram as quinze necessidades funcionais e não funcionais consolidadas como requisitos.

Esta combinação de técnicas é justificável pelo contexto acadêmico do projeto, que dispensa técnicas de maior formalidade como grupos focais ou prototipação de requisitos, em conformidade com o princípio de Governança Mínima Viável (GMV) declarado no Plano de Integração, seção 1.2.3.

#### 2.3.2 Inventário de Requisitos

Os quinze requisitos foram consolidados no TAP, seção 5, e distribuídos em seis entregas principais, cada uma rastreável a um Objetivo SMART e a uma fase da EAP:

a) MVP Web Funcional (Fase N5): REQ-01 a REQ-07, abrangendo simulação cambial em tempo real, cinco regimes de contratação, aplicação de spread e IOF, emissão de invoice em PDF, tempo de resposta inferior a três segundos, interface responsiva e cache de cotações.

b) Garantia da Qualidade (Fase N6): REQ-08 a REQ-10, abrangendo cobertura de testes superior a oitenta por cento, testes de aceitação com cem por cento dos fluxos críticos e aplicação de ferramentas da qualidade.

c) DevOps e CI/CD (Fase N7): REQ-11, referente ao pipeline de integração contínua.

d) Base de Conhecimento (Fase N9): REQ-12 e REQ-13, abrangendo ADRs e rastreabilidade de prompts de Specification-Driven Development (SDD).

e) Documentação Técnica (Fase N11): REQ-14, referente à documentação consolidada de arquitetura e APIs.

f) Conformidade FOSS (Fases N1 e N4): REQ-15, referente ao licenciamento integralmente aberto.

#### 2.3.3 Formato dos Requisitos e Conversão a Posteriori

Os requisitos REQ-01 a REQ-15 foram formalizados com critérios de aceite mensuráveis, rastreabilidade ao TAP e vínculo à fase da EAP correspondente, formato suficiente para o marco M1. A conversão formal para o formato canônico de User Story — "Como [papel], quero [ação], para [benefício]" com critérios no formato Given/When/Then — será realizada a posteriori, até o marco M2 (30/09/2026), conforme fase N2.3 da EAP. Esta decisão é justificada pela restrição de prazo letivo e pelo princípio GMV, que prioriza artefatos com valor imediato para a execução técnica.

#### 2.3.4 Abordagem Specification-Driven Development (SDD)

O escopo do COGME inclui, como requisito formal (REQ-12 e REQ-13), a utilização de Specification-Driven Development com apoio de Inteligência Artificial Generativa, conforme Premissa P3 e Objetivo SMART de Inovação do TAP. O detalhamento operacional desta abordagem — prompts, modelos, handoffs — não compõe este plano, sendo alocado no Catálogo de Prompts SDD (fase N9.3) e nos Architectural Decision Records (fase N9.1). A política de co-autoria em commits e a rastreabilidade integral dos prompts constituem critérios de aceite dos requisitos REQ-12 e REQ-13.

#### 2.3.5 Priorização MoSCoW

O backlog será classificado no Refinement semanal de 23/09/2026 conforme o método MoSCoW. A classe Must compreende os requisitos REQ-01 a REQ-09, REQ-11 e REQ-15, indispensáveis ao MVP. A classe Should compreende os requisitos REQ-10, REQ-12, REQ-13 e REQ-14, importantes mas não bloqueantes. As classes Could e Won't não possuem itens no escopo atual, sendo a última utilizada para registrar explicitamente as exclusões descritas na seção 2.4.

### 2.4 Declaração de Escopo do Projeto

Em respeito ao princípio GMV e para evitar proliferação documental, a Declaração de Escopo é consolidada neste plano, em vez de constituir artefato separado.

#### 2.4.1 Fronteira do Escopo

O escopo aprovado (IN) compreende: simulação cambial USD/EUR para BRL em tempo real; cinco regimes de contratação (hora, dia, semana, mês, valor fixo); cálculo de spread e IOF; emissão de invoice em PDF via WeasyPrint; interface web responsiva FOSS; cache SQLite de cotações; cobertura de testes superior a oitenta por cento e UAT com cem por cento dos fluxos críticos; pipeline de integração contínua com lint e testes em até cinco minutos; três ADRs e catálogo de prompts SDD; stack integralmente FOSS auditável.

A fronteira OUT do escopo é fundamentada no princípio YAGNI (*You Aren't Gonna Need It*), em conformidade com a restrição de escopo do TAP §8.1. Funcionalidades não essenciais ao MVP acadêmico — tais como suporte a moedas além de USD e EUR, cadastro multiusuário ou autenticação, integração com plataformas de transferência (Wise, Husky, similares), emissão de notas fiscais brasileiras (NF-e/NFS-e), aplicativo mobile nativo, banco de dados relacional multiusuário (PostgreSQL), testes de carga ou estresse, continuous deployment para produção, documentação para usuário final em PDF e uso de bibliotecas proprietárias ou serviços pagos — são explicitamente excluídas do ciclo atual, podendo ser reconsideradas apenas mediante solicitação formal de mudança (Plano de Integração §1.7) em ciclos futuros. Esta exclusão explícita operacionaliza a restrição de MVP e evita scope creep por acréscimo incremental de funcionalidades não autorizadas.

#### 2.4.2 Critérios de Aceite do Escopo

O escopo será considerado aceito quando todos os requisitos Must estiverem operacionais em UAT; quando a cobertura de testes atingir oitenta por cento validada via integração contínua; quando não houver defeitos críticos ou bloqueantes; quando cem por cento das dependências possuírem licenças aprovadas pela Open Source Initiative; e quando houver validação acadêmica pelo Prof. Dr. Nivaldo Carleto no marco M4.

#### 2.4.3 Artefatos Técnicos Não Abrangidos por Este Plano

Para evitar invasão de contexto, declara-se explicitamente que não compõem o escopo deste plano os seguintes artefatos, os quais serão produzidos em fases específicas da EAP e alocados nos repositórios adequados:

a) Diagramas UML completos: o TAP e a EAP não exigem modelagem UML formal. A arquitetura da solução (fase N3.1) será documentada por meio de diagrama de componentes em formato Markdown ou PlantUML, suficiente para o contexto acadêmico.

b) Diagrama Entidade-Relacionamento (DER): o DER será produzido na fase N3.3 e versionado no repositório, não compondo este plano.

c) Estrutura de diretórios do repositório: detalhe de implementação alocado na fase N5 e documentado no arquivo README.md do projeto.

d) Arquivos de configuração de integração contínua: arquivos YAML do GitHub Actions serão produzidos na fase N7.1 e versionados no diretório .github/workflows/.

### 2.5 Estrutura Analítica do Projeto

A EAP v2.0, aprovada no TAP, seção 4, constitui a linha de base estrutural do escopo. Ela é composta pelo nível 0 (raiz COGME), doze fases de nível 1 (N1 a N12), trinta e sete pacotes de trabalho de nível 2, e três macro-fases (MF1 Fundação, MF2 Construção, MF3 Consolidação).

Duas regras de governança aplicam-se à EAP. Primeira: nenhum pacote de trabalho pode ser adicionado, removido ou renomeado sem aprovação formal via change-request no GitHub, em interface com o Plano de Integração, seção 1.7. Segunda: cada pacote de trabalho de nível 2 deve ser decomponível em cards Kanban com esforço estimado inferior ou igual a oito horas; pacotes maiores serão subdivididos no Refinement semanal.

### 2.6 Definition of Ready e Definition of Done

Em conformidade com o Domínio de Entrega e o Domínio de Medição do PMBOK® 7ª, e para operacionalizar os gates de qualidade do fluxo Kanban, formalizam-se os critérios de Definition of Ready (DoR) e Definition of Done (DoD), anteriormente marcados como "a definir" no Glossário v2.2.

O DoR, gate de entrada, exige que o card possua título padronizado, descrição com critério de aceite mensurável, rastreabilidade à fase da EAP e ao requisito do TAP, estimativa de esforço inferior ou igual a oito horas, dependências identificadas, responsável atribuído e revisão no Refinement semanal.

O DoD, gate de saída, exige que o código esteja implementado e commitado em feature branch; que os testes unitários estejam escritos com cobertura do módulo superior ou igual a oitenta por cento; que o pipeline de integração contínua esteja verde; que o Code Review tenha sido aprovado por pelo menos um par; que a documentação esteja atualizada quando aplicável; que o card tenha sido movido para Done com data registrada; e que, se o código foi gerado com apoio de Specification-Driven Development, o commit declare co-autoria conforme Critério de Inovação Controlada do TAP, seção 3.2.e.

### 2.7 Validação e Controle de Escopo

Os processos 5.5 (Validar o Escopo) e 5.6 (Controlar o Escopo) do PMBOK® 6ª são operacionalizados no COGME por meio de rituais Kanban, conforme ADR-002. A validação ocorre por Code Review e User Acceptance Testing no marco M3, com evidência em Pull Request aprovado e relatório de UAT. O controle ocorre por Refinement semanal e análise do Cumulative Flow Diagram, com evidência no GitHub Projects e no GitHub Insights.

A prevenção de scope creep aciona alerta quando o backlog cresce superior a quinze por cento em relação à linha de base de trinta e sete pacotes. Neste caso, o GP congela novas features, analisa impacto via change-request e decide em até quarenta e oito horas. A métrica de controle é o Throughput semanal superior ou igual a cinco cards; se o Throughput for inferior a três cards por semana durante duas semanas consecutivas, o escopo é revisado conforme fallback da ADR-003.

### 2.8 Gestão de Mudanças de Escopo

Qualquer alteração no escopo segue o fluxo definido no Plano de Integração, seção 1.7: abertura de Issue com label change-request, análise de impacto pelo GP em até quarenta e oito horas, aprovação ou rejeição em até vinte e quatro horas, e atualização do backlog, da EAP quando aplicável, e commit. Mudanças que alterem marcos ou o escopo do MVP exigem ADR e comunicação ao Prof. Dr. Nivaldo no marco subsequente.

### 2.9 Condições de Fracasso e Escalation

Derivados do TAP, seção 3.3, os seguintes gatilhos específicos de escopo acionam ação corretiva: requisito Must não implementado até M3, com contingência de redução de escopo Should; EAP com mais de quinze por cento de pacotes não iniciados até M2, com replanejamento e ADR; UAT com defeito crítico ou bloqueante, com retrabalho imediato e congelamento de novas features; scope creep superior a quinze por cento, com congelamento e decisão do CCB; e cobertura de requisitos inferior a cem por cento dos Must, com bloqueio do M3.

### 2.10 Declaração de Rastreabilidade

Cada seção deste plano possui rastreabilidade a ao menos um objetivo SMART, premissa ou restrição do TAP, ao domínio de desempenho do PMBOK® 7ª correspondente, e ao processo do PMBOK® 6ª utilizado como dicionário. A seção 2.2 rastreia ao TAP seção 1.c e à Premissa P1, vinculando-se aos domínios de Planejamento e Entrega e ao processo 5.1. A seção 2.3 rastreia ao TAP seção 3 e seção 5, vinculando-se ao domínio de Entrega e ao processo 5.2. A seção 2.4 rastreia ao TAP seção 3, seção 8 e seção 9 (Premissa P2), vinculando-se ao domínio de Entrega e ao processo 5.3, com a fronteira OUT adicionalmente fundamentada no princípio YAGNI. A seção 2.5 rastreia ao TAP seção 4, vinculando-se ao domínio de Planejamento e ao processo 5.4. As seções 2.6 e 2.7 rastreiam ao TAP seção 3, vinculando-se aos domínios de Entrega e Medição e aos processos 5.5 e 5.6. A seção 2.8 rastreia ao TAP seção 3.3, vinculando-se ao domínio de Incerteza e ao processo 4.6. A seção 2.9 rastreia ao TAP seção 3.3 e seção 10, vinculando-se ao domínio de Incerteza e ao processo 5.6.

### 2.11 Premissas e Restrições Aplicáveis

As premissas aplicáveis a este plano são: P1 (governança híbrida), que fundamenta a seção 2.2; P2 (FOSS absoluto), que fundamenta a fronteira OUT da seção 2.4.1; P4 (código como deliverable), que fundamenta o DoD da seção 2.6; e P8 (simplificação de Aquisições e Partes Interessadas), que fundamenta o escopo enxuto.

As restrições aplicáveis são: restrição de escopo (MVP acadêmico), que fundamenta a fronteira IN/OUT e a aplicação do princípio YAGNI na seção 2.4.1; restrição de cronograma (prazo letivo inegociável), que fundamenta os gatilhos da seção 2.9; e restrição de qualidade (tempo restrito para testes), que fundamenta o DoD com cobertura da seção 2.6.

---

**Controle de Versões**

| Versão | Data       | Alteração                                                                                                                                                                                                                     | Responsável         |
| ------- | ---------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | -------------------- |
| 0.0     | 19/09/2026 | Emissão para análise prévia — decisões de escopo da seção                                                                                                                                                                | Leonardo D. S. Setti |
| 0.1     | 19/09/2026 | Inserção do princípio YAGNI na seção 2.4.1 como fundamentação da fronteira OUT; ajuste de rastreabilidade na seção 2.10; manutenção do princípio KISS exclusivamente na ADR-001 (segregação de responsabilidades) | Leonardo D. S. Setti |

---

**Status da seção:** ✅ v0.1 emitida — pronta para revisão em pares (Fabricio + Edson).
**Próximo passo:** Após correções pontuais da equipe, emitir v1.0 formatada em ABNT para submissão ao marco M1 (22/09/2026).

---

## Resumo das Alterações v0.0 → v0.1

| Alteração                       | Seção | Justificativa Técnica                                                                                                                                                     |
| --------------------------------- | ------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Inserção do parágrafo YAGNI    | 2.4.1   | Operacionaliza a restrição de escopo do TAP §8.1; justifica a fronteira OUT como decisão de governança, não apenas lista de exclusões                               |
| Ajuste de rastreabilidade         | 2.10    | Inclusão da referência ao princípio YAGNI e à Premissa P2 na rastreabilidade da seção 2.4                                                                            |
| Reforço da restrição de escopo | 2.11    | Menção explícita ao YAGNI como princípio aplicado à fronteira IN/OUT                                                                                                  |
| Manutenção do KISS na ADR-001   | —      | Segregação de responsabilidades: KISS é princípio de arquitetura (ADR-001), não de governança de escopo; inseri-lo aqui violaria o próprio KISS e o princípio SSOT |
