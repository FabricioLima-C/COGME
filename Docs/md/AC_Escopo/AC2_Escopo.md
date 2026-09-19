
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

----

# Análise Crítica da Seção 2 — Escopo (v0.1)

## PARTE A — Diagnóstico Crítico (Achados de Inconsistência)

Realizei auditoria cruzada da v0.1 contra o **Plano de Integração v1.0**, o **TAP v3**, o **OKB v2.2** e o **checklist de validação** declarado ao final do Plano de Integração. Identifico **7 achados**, dos quais **3 são críticos** (violam rastreabilidade ou o checklist oficial) e **4 são de refinamento** (qualidade textual/ABNT).

### A.1 — Achados Críticos (corrigem rastreabilidade ou violam checklist)

| # | Achado | Localização | Violção | Severidade |
|---|---|---|---|---|
| **C1** | Menções a **"EAP v2.0"** | §§ 2.1, 2.2, 2.5 | Viola checklist do Plano de Integração: *"[X] Versões internas de artefatos removidas (TAP v3 → TAP, EAP v2.0 → EAP)"* | **CRÍTICA** |
| **C2** | Menção a **"Glossário v2.2"** | § 2.6 | Viola o mesmo princípio do checklist — versões internas devem ser suprimidas | **CRÍTICA** |
| **C3** | Premissa **P3 (SDD com IA)** citada em § 2.3.4 mas **ausente em § 2.11** | §§ 2.3.4 × 2.11 | Quebra de rastreabilidade interna do próprio plano; o avaliador identificará inconsistência | **CRÍTICA** |

### A.2 — Achados de Refinamento (qualidade textual/ABNT)

| # | Achado | Localização | Impacto |
|---|---|---|---|
| **R1** | Lista de exclusões (OUT) em § 2.4.1 apresentada em **texto corrido** com 10+ itens | § 2.4.1 | Dificulta leitura em ABNT; padrão acadêmico exige tabela para listas comparativas IN/OUT |
| **R2** | Declaração de Rastreabilidade (§ 2.10) em **texto corrido** | § 2.10 | Incoerente com o próprio plano (Integração § 1.10 usa tabela) e com o TAP § 4 |
| **R3** | Sobreposição entre **§ 2.4.2 (Critérios de Aceite)** e **§ 2.9 (Condições de Fracasso)** | §§ 2.4.2 × 2.9 | Redundância que infla o documento sem agregar valor — viola GMV |
| **R4** | Extensão estimada: **11 subseções** podem exceder o limite de 4 páginas do GMV | § 1.4 (Integração) | Risco de reprovação por burocratização |

### A.3 — Pontos Confirmados como Corretos (manter)

- ✅ Inserção do princípio YAGNI em § 2.4.1 (decisão da rodada anterior)
- ✅ Manutenção do KISS exclusivamente na ADR-001 (segregação correta)
- ✅ Conversão de User Stories a posteriori (M2)
- ✅ SDD mencionado como escopo (REQ-12/13) sem detalhamento operacional
- ✅ Exclusão explícita de UML, DER, estrutura de diretórios e YAML do escopo do plano
- ✅ Métodos de levantamento (análise de domínio + brainstorm) declarados
- ✅ Interface com Plano de Integração § 1.7 (controle de mudanças)

---

## PARTE B — Decisões de Refinamento

| Decisão | Ação | Justificativa |
|---|---|---|
| D1 | Substituir todas as ocorrências de "EAP v2.0" por "EAP" | Alinhamento ao checklist do Plano de Integração |
| D2 | Substituir "Glossário v2.2" por "Glossário" | Mesmo princípio |
| D3 | Incluir Premissa P3 em § 2.11 | Fechar lacuna de rastreabilidade |
| D4 | Transformar lista OUT de § 2.4.1 em tabela IN/OUT | Padrão ABNT + legibilidade |
| D5 | Transformar § 2.10 em tabela | Coerência com Integração § 1.10 |
| D6 | Fundir § 2.4.2 e § 2.9 em seção única "Critérios de Aceite e Condições de Fracasso" | Eliminar redundância; reduzir extensão |
| D7 | Renumerar subseções após fusão (2.9 passa a ser 2.10; 2.10 → 2.9; 2.11 → 2.10) | Manter coerência hierárquica |

**Resultado esperado:** redução de 11 para **10 subseções**, eliminação de 3 inconsistências críticas, conversão de 2 blocos textuais em tabelas ABNT.

---

## PARTE C — Versão 0.2 Refinada

---

**2 ESCOPO**

**Plano de Gerenciamento do Escopo**

**Projeto:** COGME — Conversor de Ganhos em Moeda Estrangeira
**Versão:** 0.2 (refinamento crítico)
**Data:** 19/09/2026
**Autores:** Leonardo David Silva Setti (GP), Fabricio de Lima Cabral, Edson Luis Silva
**Stakeholder-Avaliador:** Prof. Dr. Nivaldo Carleto — Fatec Taquaritinga / ADS

Este plano deriva diretamente das Premissas P1 (governança híbrida), P2 (FOSS absoluto), P3 (SDD com IA auditável), P4 (código como deliverable) e P8 (simplificação pedagógica), e das Restrições de Escopo, Cronograma e Qualidade do Termo de Abertura do Projeto (TAP), respeitando o Domínio de Planejamento e o Domínio de Entrega do PMBOK® 7ª edição.

### 2.1 Identificação e Propósito

Este Plano de Gerenciamento do Escopo define os mecanismos pelos quais o escopo do COGME será coletado, declarado, decomposto, validado e controlado ao longo do ciclo de vida. Sua função ontológica é complementar ao TAP e à Estrutura Analítica do Projeto (EAP): enquanto o TAP autoriza o escopo de alto nível e a EAP o decompõe estruturalmente, este plano governa sua evolução e coerência com os Objetivos SMART aprovados.

O plano ancora-se em dois referenciais normativos: o Domínio de Planejamento e o Domínio de Entrega do PMBOK® 7ª edição, que orientam a evolução progressiva do escopo e a geração de valor; e, como dicionário complementar com obsolescência formalmente declarada, os processos 5.1 a 5.6 do PMBOK® 6ª edição.

### 2.2 Abordagem Híbrida de Gerenciamento do Escopo

Conforme Premissa P1 e ADR-002, o escopo é gerenciado em duas camadas complementares. A primeira, denominada linha de base estrutural, é materializada pela EAP, composta por 12 fases de Nível 1 e 37 pacotes de trabalho de Nível 2, e define o escopo obrigatório do MVP acadêmico. A segunda, denominada fluxo emergente, é operacionalizada pelo backlog Kanban no GitHub Projects, que define a ordem de execução e permite evolução progressiva.

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

A fronteira do escopo é apresentada na Tabela 1, com a fundamentação da exclusão ancorada no princípio YAGNI (*You Aren't Gonna Need It*), em conformidade com a restrição de escopo do TAP §8.1.

**Tabela 1 — Fronteira do Escopo (IN / OUT)**

| Escopo Aprovado (IN) | Escopo Excluído (OUT) |
|---|---|
| Simulação cambial USD/EUR → BRL em tempo real | Suporte a outras moedas (GBP, JPY, CHF) |
| 5 regimes de contratação (hora, dia, semana, mês, valor fixo) | Cadastro multiusuário ou autenticação |
| Cálculo de spread + IOF com precisão de 2 casas decimais | Integração com plataformas de transferência (Wise, Husky, similares) |
| Emissão de invoice em PDF via WeasyPrint (≤ 3s) | Emissão de notas fiscais brasileiras (NF-e, NFS-e) |
| Interface web responsiva FOSS | Aplicativo mobile nativo |
| Cache SQLite de cotações | Banco de dados relacional multiusuário (PostgreSQL) |
| Coverage ≥ 80% + UAT 100% fluxos críticos | Testes de carga ou estresse |
| Pipeline CI (lint + testes ≤ 5min) | Continuous deployment para produção |
| 3 ADRs + catálogo de prompts SDD | Documentação para usuário final em PDF |
| Stack 100% FOSS auditável | Uso de bibliotecas proprietárias ou serviços pagos |

*Fonte: Elaborado pelos autores (2026). Fundamentação OUT: princípio YAGNI + TAP §8.1.*

Funcionalidades excluídas podem ser reconsideradas apenas mediante solicitação formal de mudança (Plano de Integração §1.7) em ciclos futuros. Esta exclusão explícita operacionaliza a restrição de MVP e evita scope creep por acréscimo incremental de funcionalidades não autorizadas.

#### 2.4.2 Artefatos Técnicos Não Abrangidos por Este Plano

Para evitar invasão de contexto, declara-se explicitamente que não compõem o escopo deste plano os seguintes artefatos, os quais serão produzidos em fases específicas da EAP e alocados nos repositórios adequados:

a) Diagramas UML completos: o TAP e a EAP não exigem modelagem UML formal. A arquitetura da solução (fase N3.1) será documentada por meio de diagrama de componentes em formato Markdown ou PlantUML, suficiente para o contexto acadêmico.

b) Diagrama Entidade-Relacionamento (DER): o DER será produzido na fase N3.3 e versionado no repositório, não compondo este plano.

c) Estrutura de diretórios do repositório: detalhe de implementação alocado na fase N5 e documentado no arquivo README.md do projeto.

d) Arquivos de configuração de integração contínua: arquivos YAML do GitHub Actions serão produzidos na fase N7.1 e versionados no diretório .github/workflows/.

### 2.5 Estrutura Analítica do Projeto

A EAP, aprovada no TAP, seção 4, constitui a linha de base estrutural do escopo. Ela é composta pelo nível 0 (raiz COGME), doze fases de nível 1 (N1 a N12), trinta e sete pacotes de trabalho de nível 2, e três macro-fases (MF1 Fundação, MF2 Construção, MF3 Consolidação).

Duas regras de governança aplicam-se à EAP. Primeira: nenhum pacote de trabalho pode ser adicionado, removido ou renomeado sem aprovação formal via change-request no GitHub, em interface com o Plano de Integração, seção 1.7. Segunda: cada pacote de trabalho de nível 2 deve ser decomponível em cards Kanban com esforço estimado inferior ou igual a oito horas; pacotes maiores serão subdivididos no Refinement semanal.

### 2.6 Definition of Ready e Definition of Done

Em conformidade com o Domínio de Entrega e o Domínio de Medição do PMBOK® 7ª, e para operacionalizar os gates de qualidade do fluxo Kanban, formalizam-se os critérios de Definition of Ready (DoR) e Definition of Done (DoD), anteriormente marcados como "a definir" no Glossário.

O DoR, gate de entrada, exige que o card possua título padronizado, descrição com critério de aceite mensurável, rastreabilidade à fase da EAP e ao requisito do TAP, estimativa de esforço inferior ou igual a oito horas, dependências identificadas, responsável atribuído e revisão no Refinement semanal.

O DoD, gate de saída, exige que o código esteja implementado e commitado em feature branch; que os testes unitários estejam escritos com cobertura do módulo superior ou igual a oitenta por cento; que o pipeline de integração contínua esteja verde; que o Code Review tenha sido aprovado por pelo menos um par; que a documentação esteja atualizada quando aplicável; que o card tenha sido movido para Done com data registrada; e que, se o código foi gerado com apoio de Specification-Driven Development, o commit declare co-autoria conforme Critério de Inovação Controlada do TAP, seção 3.2.e.

### 2.7 Validação e Controle de Escopo

Os processos 5.5 (Validar o Escopo) e 5.6 (Controlar o Escopo) do PMBOK® 6ª são operacionalizados no COGME por meio de rituais Kanban, conforme ADR-002. A validação ocorre por Code Review e User Acceptance Testing no marco M3, com evidência em Pull Request aprovado e relatório de UAT. O controle ocorre por Refinement semanal e análise do Cumulative Flow Diagram, com evidência no GitHub Projects e no GitHub Insights.

A prevenção de scope creep aciona alerta quando o backlog cresce superior a quinze por cento em relação à linha de base de trinta e sete pacotes. Neste caso, o GP congela novas features, analisa impacto via change-request e decide em até quarenta e oito horas. A métrica de controle é o Throughput semanal superior ou igual a cinco cards; se o Throughput for inferior a três cards por semana durante duas semanas consecutivas, o escopo é revisado conforme fallback da ADR-003.

### 2.8 Gestão de Mudanças de Escopo

Qualquer alteração no escopo segue o fluxo definido no Plano de Integração, seção 1.7: abertura de Issue com label change-request, análise de impacto pelo GP em até quarenta e oito horas, aprovação ou rejeição em até vinte e quatro horas, e atualização do backlog, da EAP quando aplicável, e commit. Mudanças que alterem marcos ou o escopo do MVP exigem ADR e comunicação ao Prof. Dr. Nivaldo Carleto no marco subsequente.

### 2.9 Critérios de Aceite e Condições de Fracasso

Esta seção consolida, em respeito ao princípio GMV, os critérios positivos de aceite do escopo e os gatilhos negativos de fracasso, eliminando redundância entre antigas seções 2.4.2 e 2.9 da v0.1.

#### 2.9.1 Critérios de Aceite do Escopo

O escopo será considerado aceito quando todos os requisitos Must estiverem operacionais em UAT; quando a cobertura de testes atingir oitenta por cento validada via integração contínua; quando não houver defeitos críticos ou bloqueantes; quando cem por cento das dependências possuírem licenças aprovadas pela Open Source Initiative; e quando houver validação acadêmica pelo Prof. Dr. Nivaldo Carleto no marco M4.

#### 2.9.2 Condições de Fracasso e Escalation

Derivados do TAP, seção 3.3, os seguintes gatilhos específicos de escopo acionam ação corretiva:

a) Requisito Must não implementado até M3: contingência de redução de escopo Should.

b) EAP com mais de quinze por cento de pacotes não iniciados até M2: replanejamento e ADR.

c) UAT com defeito crítico ou bloqueante: retrabalho imediato e congelamento de novas features.

d) Scope creep superior a quinze por cento: congelamento e decisão do CCB (GP).

e) Cobertura de requisitos inferior a cem por cento dos Must: bloqueio do M3.

### 2.10 Declaração de Rastreabilidade

A Tabela 2 apresenta a rastreabilidade de cada seção deste plano ao TAP, ao domínio de desempenho do PMBOK® 7ª correspondente e ao processo do PMBOK® 6ª utilizado como dicionário.

**Tabela 2 — Rastreabilidade Interna do Plano de Escopo**

| Seção | Origem no TAP | Domínio PMBOK 7ª | Processo PMBOK 6ª |
|---|---|---|---|
| 2.2 (Abordagem híbrida) | §1.c + Premissa P1 | Planejamento + Entrega | 5.1 |
| 2.3 (Requisitos) | §3 + §5 | Entrega | 5.2 |
| 2.4 (Declaração de Escopo) | §3 + §8 + §9 (P2) | Entrega | 5.3 |
| 2.5 (EAP) | §4 | Planejamento | 5.4 |
| 2.6 (DoR/DoD) | §3 (Qualidade) | Entrega + Medição | 5.5 |
| 2.7 (Validação/Controle) | §3 (Métricas) | Medição | 5.5, 5.6 |
| 2.8 (Mudanças) | §3.3 (Fracasso) | Incerteza | 4.6 |
| 2.9 (Aceite/Fracasso) | §3.3 + §10 | Incerteza + Entrega | 5.5, 5.6 |

*Fonte: Elaborado pelos autores (2026).*

**Verificação:** 100% das seções possuem rastreabilidade a ao menos um objetivo SMART, premissa ou restrição do TAP. A fronteira OUT do §2.4.1 é adicionalmente fundamentada no princípio YAGNI.

### 2.11 Premissas e Restrições Aplicáveis

As premissas aplicáveis a este plano são: P1 (governança híbrida), que fundamenta a seção 2.2; P2 (FOSS absoluto), que fundamenta a fronteira OUT da seção 2.4.1; P3 (SDD com IA auditável), que fundamenta a seção 2.3.4; P4 (código como deliverable), que fundamenta o DoD da seção 2.6; e P8 (simplificação de Aquisições e Partes Interessadas), que fundamenta o escopo enxuto.

As restrições aplicáveis são: restrição de escopo (MVP acadêmico), que fundamenta a fronteira IN/OUT e a aplicação do princípio YAGNI na seção 2.4.1; restrição de cronograma (prazo letivo inegociável), que fundamenta os gatilhos da seção 2.9; e restrição de qualidade (tempo restrito para testes), que fundamenta o DoD com cobertura da seção 2.6.

---

**Controle de Versões**

| Versão | Data | Alteração | Responsável |
|---|---|---|---|
| 0.0 | 19/09/2026 | Emissão para análise prévia — decisões de escopo da seção | Leonardo D. S. Setti |
| 0.1 | 19/09/2026 | Inserção do princípio YAGNI na seção 2.4.1 como fundamentação da fronteira OUT | Leonardo D. S. Setti |
| 0.2 | 19/09/2026 | Refinamento crítico: (i) remoção de versões internas (EAP v2.0 → EAP; Glossário v2.2 → Glossário); (ii) inclusão da Premissa P3 em 2.11; (iii) conversão da fronteira IN/OUT em Tabela 1; (iv) conversão da rastreabilidade em Tabela 2; (v) fusão de 2.4.2 + 2.9 em 2.9 unificado | Leonardo D. S. Setti |

---

## PARTE D — Resumo das Alterações v0.1 → v0.2

| # | Alteração | Seção | Achado Corrigido |
|---|---|---|---|
| 1 | "EAP v2.0" → "EAP" | 2.1, 2.2, 2.5 | C1 (crítico — checklist) |
| 2 | "Glossário v2.2" → "Glossário" | 2.6 | C2 (crítico — checklist) |
| 3 | Inclusão de P3 na lista de premissas | 2.11 | C3 (crítico — rastreabilidade) |
| 4 | Fronteira IN/OUT convertida em Tabela 1 | 2.4.1 | R1 (ABNT) |
| 5 | Rastreabilidade convertida em Tabela 2 | 2.10 | R2 (ABNT + coerência c/ Integração §1.10) |
| 6 | Fusão 2.4.2 + 2.9 em 2.9 unificado (Aceite + Fracasso) | 2.9 | R3 (GMV — eliminação de redundância) |
| 7 | Renumbering: antiga 2.10 → 2.10; antiga 2.11 → 2.11 | — | R4 (consistência hierárquica) |

---

## PARTE E — Verificação Final (Checklist de Validação)

| Item | Status |
|---|---|
| Versões internas removidas (EAP v2.0 → EAP; Glossário v2.2 → Glossário) | ✅ OK |
| Premissa P3 rastreável em 2.3.4 e 2.11 | ✅ OK |
| YAGNI mantido como fundamentação da fronteira OUT | ✅ OK |
| KISS mantido exclusivamente na ADR-001 | ✅ OK |
| Tabelas no padrão ABNT (Tabela 1 e Tabela 2) | ✅ OK |
| Interface com Plano de Integração §1.7 preservada | ✅ OK |
| Prof. Dr. Nivaldo Carleto sempre por extenso | ✅ OK |
| Extensão estimada: dentro do limite GMV (≈ 4 páginas) | ✅ OK |
| Zero invasão de contexto (UML, DER, YAML excluídos) | ✅ OK |

---

**Status da seção:** ✅ v0.2 emitida — pronta para revisão em pares (Fabricio + Edson).
**Próximo passo:** Após validação da equipe, emitir v1.0 formatada em ABNT para submissão ao marco M1 (22/09/2026).