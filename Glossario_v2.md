# Glossário v2.2 — COGME (Operational Knowledge Base)

**Data:** 19/09/2026  
**Status:** Ativo — convergente ao TAP v3 + OKB v2.2 + ADRs 001-003  
**Hierarquia de autoridade:** TAP > OKB > Glossário > ADRs  
**Referência matriz:** TAP v3 (18/09/2026)  
**Declaração de obsolescência:** PMBOK 6ª (2017) tratado como dicionário de processos; métricas EVM marcadas como LEGADO.

---

## 1. GOVERNANÇA E GERENCIAMENTO DE PROJETOS

| Termo | Definição | Contexto COGME | Fonte |
|-------|-----------|----------------|-------|
| **PMBOK 7ª** | Guia do PMI baseado em 12 princípios e 8 domínios de desempenho (valor, sistemas, equipe, etc.) | Governança primária do projeto | TAP §1.c |
| **PMBOK 6ª** | Guia do PMI com 49 processos em 10 áreas de conhecimento (2017) | Dicionário complementar — **obsolescência assumida** | OKB §1.3 |
| **Princípios PMBOK 7ª** | 12 diretrizes de comportamento (foco no valor, pensamento sistêmico, liderança, etc.) | Base da governança híbrida | TAP §1.c |
| **Domínios de Desempenho** | 8 áreas inter-relacionadas: Stakeholders, Equipe, Abordagem, Planejamento, Trabalho, Entrega, Medição, Incerteza | Mapeamento de rituais Kanban | ADR-002 |
| **CCB** | Change Control Board — Comitê de Controle de Mudanças | **GP Leonardo (membro único)** — TAP v3 §1.c | OKB §1.2 |
| **GP** | Gerente de Projeto | Leonardo David Silva Setti | TAP §1.b |
| **PMO** | Project Management Office | Escritório de Projetos (referência acadêmica) | TAP |
| **Stakeholder** | Parte interessada | Prof. Nivaldo (avaliador) + equipe (3 membros) | TAP §6 |
| **Sponsor** | Patrocinador | N/A (orçamento zero) | TAP §11 |
| **Tailoring** | Adaptação de processos ao contexto | Governança híbrida declarada | TAP §1.c |
| **GMV** | Governança Mínima Viável | Princípio de priorização documental (foco em valor) | OKB §5.2 |
| **SSOT** | Single Source of Truth | GitHub Projects como fonte única de verdade | ADR-002 |
| **Baseline** | Linha de base (escopo, cronograma, custos) | No COGME: baseline empírica de métricas de fluxo (23/09–03/10) | ADR-003 |
| **Work Breakdown Structure (WBS)** | Estrutura Analítica do Projeto (EAP) | 12 fases + 37 pacotes de trabalho | TAP §4 |
| **Project Charter** | Termo de Abertura do Projeto (TAP) | Documento autorizativo (v3 — 18/09/2026) | TAP |

---

## 2. DOMÍNIOS DE DESEMPENHO PMBOK 7ª

| Domínio | Definição | Mapeamento Kanban (ADR-002) |
|---------|-----------|----------------------------|
| **Stakeholders** | Engajamento de partes interessadas | Refinement semanal |
| **Equipe** | Gestão de recursos humanos + prevenção de burnout | Daily assíncrona + WIP limits |
| **Abordagem de Desenvolvimento** | Seleção de método (preditivo, ágil, híbrido) | Fluxo contínuo Kanban |
| **Planejamento** | Evolução progressiva do escopo | Refinement + priorização |
| **Trabalho do Projeto** | Execução de atividades | Pull system |
| **Entrega** | Geração de valor | DoD + Code Review |
| **Medição** | Coleta e análise de métricas | Cycle Time, Throughput, CFD |
| **Incerteza** | Gestão de riscos e ambiguidades | Retrospectiva + Risk backlog |

---

## 3. PROCESSOS PMBOK 6ª (DICIONÁRIO COMPLEMENTAR — OBSOLESCÊNCIA ASSUMIDA)

| ID | Processo | Área | Status no COGME |
|----|----------|------|-----------------|
| 4.1 | Desenvolver Termo de Abertura | Integração | ✅ Aplicado (TAP v3) |
| 4.2 | Desenvolver Plano de Gerenciamento | Integração | ✅ Aplicado (8 planos) |
| 4.3 | Orientar e Gerenciar Trabalho | Integração | ⚠️ Substituído por Kanban |
| 4.5 | Monitorar e Controlar Trabalho | Integração | ⚠️ Substituído por métricas de fluxo |
| 4.6 | Realizar Controle Integrado de Mudanças | Integração | ✅ Aplicado (CCB = GP) |
| 5.1 | Planejar Gerenciamento do Escopo | Escopo | ✅ Aplicado |
| 5.2 | Coletar Requisitos | Escopo | ✅ Aplicado (REQ-01 a REQ-15) |
| 5.3 | Definir Escopo | Escopo | ✅ Aplicado (EAP v2.0) |
| 5.4 | Criar EAP | Escopo | ✅ Aplicado |
| 5.5 | Validar Escopo | Escopo | ⏳ UAT (M3) |
| 5.6 | Controlar Escopo | Escopo | ⚠️ Substituído por backlog Kanban |
| 6.1–6.4 | Cronograma (processos) | Cronograma | ⚠️ Substituído por fluxo contínuo |
| 6.5 | Desenvolver Cronograma | Cronograma | ✅ Aplicado (marcos M1–M4) |
| 7.1–7.4 | Custos (processos) | Custos | ⚠️ Inaplicável (orçamento zero) |
| 8.1–8.3 | Qualidade (processos) | Qualidade | ✅ Aplicado (12 PDCAs + Ishikawa) |
| 9.1–9.6 | Recursos (processos) | Recursos | ⚠️ Simplificado (3 pessoas) |
| 10.1–10.3 | Comunicações (processos) | Comunicações | ⚠️ Simplificado (GitHub Issues) |
| 11.1 | Identificar Riscos | Riscos | ✅ Aplicado (R1–R5) |
| 11.2–11.7 | Riscos (outros processos) | Riscos | ⚠️ Simplificado (GMV) |
| 12.1–12.3 | Aquisições | Aquisições | ❌ Excluído (orçamento zero) |
| 13.1–13.4 | Partes Interessadas | Partes Interessadas | ❌ Excluído (simplificado) |

---

## 4. METODOLOGIA ÁGIL / KANBAN

| Termo | Definição | Contexto COGME | Fonte |
|-------|-----------|----------------|-------|
| **Kanban** | Método de fluxo contínuo com WIP limits | Método de execução oficial | TAP §1.c, ADR-002 |
| **Pull System** | Trabalho puxado por capacidade (não empurrado) | Cards movidos conforme disponibilidade | ADR-002 |
| **WIP Limit** | Work In Progress Limit — limite de trabalho em progresso | 3 cards/pessoa em `In Progress` | ADR-002 |
| **Flow** | Fluxo de trabalho através do sistema | Backlog → Ready → In Progress → Review → Done | ADR-002 |
| **Cycle Time** | Tempo médio de um card do `In Progress` ao `Done` | Meta: ≤ 3 dias | ADR-003 |
| **Throughput** | Cards concluídos por unidade de tempo | Meta: ≥ 5 cards/semana | ADR-003 |
| **CFD** | Cumulative Flow Diagram — visualização de gargalos | Sem bandas largas (meta) | ADR-003 |
| **DoR** | Definition of Ready — critérios para card entrar em `Ready` | A definir (M1) | ADR-002 |
| **DoD** | Definition of Done — critérios para card ir para `Done` | A definir (M1) | ADR-002 |
| **Backlog** | Lista priorizada de trabalho pendente | GitHub Projects | ADR-002 |
| **Refinement** | Refinamento do backlog | Semanal (30min) | ADR-002 |
| **Retrospectiva** | Ritual de melhoria contínua | Quinzenal | ADR-002 |
| **Daily** | Reunião diária de sincronização | Assíncrona (GitHub Issues, 15min) | ADR-002 |
| **Sprint** | Iteração time-boxed (Scrum) | **NÃO UTILIZADO** — fluxo contínuo | OKB §5.1 |
| **Incremento** | Entrega de valor funcional | MVP funcional (M3) | TAP §3 |
| **User Story** | História de usuário (formato: "Como [papel], quero [ação], para [benefício]") | REQ-01 a REQ-15 | TAP §5 |
| **Epic** | Grande funcionalidade composta por múltiplas histórias | MVP completo | TAP §5 |

---

## 5. MÉTRICAS E INDICADORES

### 5.1 Métricas ATIVAS (Kanban — ADR-003)

| Métrica | Fórmula | Meta | Frequência |
|---------|---------|------|------------|
| **Cycle Time** | Média (Done − In Progress) | ≤ 3 dias | Semanal |
| **Throughput** | Cards concluídos / semana | ≥ 5 cards | Semanal |
| **CFD** | Visualização de gargalos | Sem bandas largas | Semanal |
| **WIP em fluxo** | Cards em `In Progress` | ≤ 9 (3 × 3 pessoas) | Contínuo |
| **Coverage** | Linhas testadas / totais | ≥ 80% | Por push (CI) |
| **Lead Time** | Tempo total (Backlog → Done) | A calibrar (baseline) | Semanal |

### 5.2 Métricas LEGADO (NÃO APLICÁVEIS — ADR-003)

| Métrica | Status | Justificativa |
|---------|--------|---------------|
| **SPI** (Schedule Performance Index) | ❌ LEGADO | Inaplicável — fluxo contínuo |
| **CPI** (Cost Performance Index) | ❌ LEGADO | Inaplicável — orçamento zero |
| **EVM** (Earned Value Management) | ❌ LEGADO | Inaplicável — AC = 0 |
| **PV** (Planned Value) | ❌ LEGADO | Inaplicável — escopo emergente |
| **EV** (Earned Value) | ❌ LEGADO | Inaplicável — sem linha de base |
| **AC** (Actual Cost) | ❌ LEGADO | Inaplicável — orçamento zero |

---

## 6. STACK TECNOLÓGICA (ADR-001)

| Camada | Tecnologia | Licença | Justificativa |
|--------|------------|---------|---------------|
| **Backend** | Python 3.11 + FastAPI | PSF / MIT | Assíncrono nativo, ecossistema maduro |
| **Banco** | SQLite | Public Domain | Zero-config, ACID, adequado ao MVP |
| **PDF** | WeasyPrint | BSD-3-Clause | HTML/CSS → PDF, FOSS |
| **Testes** | pytest + coverage.py | MIT | Padrão Python, integração CI |
| **CI/CD** | GitHub Actions (Free Tier) | Proprietário gratuito | Nativo ao SSOT |
| **Frontend** | HTML5 + CSS3 + JS vanilla | — | KISS, sem framework pesado |
| **LLM (SDD)** | QwenStudio | Licença autorizada | TAP §3 (Inovação) |
| **SO** | Arch Linux (Zen Kernel) | GPL | Ambiente de desenvolvimento |
| **Container** | Docker | Apache 2.0 | Isolamento de ambiente |
| **Versionamento** | Git | GPL | Controle de versão |
| **Repositório** | GitHub | Proprietário gratuito | SSOT + CI/CD |

---

## 7. QUALIDADE E TESTES

| Termo | Definição | Contexto COGME | Fonte |
|-------|-----------|----------------|-------|
| **Coverage** | Cobertura de código por testes | Meta: ≥ 80% | TAP §3 (Qualidade) |
| **TDD** | Test-Driven Development | Adotado desde N5 | TAP §10 (R4) |
| **Unit Test** | Teste unitário (função/método isolado) | pytest | TAP §3 |
| **Integration Test** | Teste de integração (múltiplos componentes) | pytest + SQLite | TAP §3 |
| **UAT** | User Acceptance Testing | 100% fluxos críticos | TAP §3 |
| **PDCA** | Plan-Do-Check-Act (ciclo de melhoria) | 12 PDCAs consolidados | TAP §3 (Qualidade) |
| **Ishikawa 6M** | Diagrama de causa e efeito (Mão de obra, Máquina, Material, Método, Medida, Meio ambiente) | Análise de riscos | TAP §3 |
| **Defeito Crítico** | Bug que impede uso do sistema | Zero tolerância em UAT | TAP §3 |
| **Defeito Bloqueante** | Bug que impede teste de outra funcionalidade | Zero tolerância em UAT | TAP §3 |
| **QA** | Quality Assurance | Fase N6 | EAP |
| **QC** | Quality Control | Testes automatizados | EAP |

---

## 8. DEVOPS E CI/CD

| Termo | Definição | Contexto COGME | Fonte |
|-------|-----------|----------------|-------|
| **CI** | Continuous Integration | GitHub Actions | TAP §3 |
| **CD** | Continuous Delivery/Deployment | Não aplicado (MVP local) | TAP §3 |
| **Pipeline** | Sequência automatizada de build/test/deploy | lint + testes ≤ 5min | REQ-11 |
| **Lint** | Análise estática de código | flake8/black (Python) | REQ-11 |
| **Build** | Compilação/empacotamento | Não aplicável (Python interpretado) | — |
| **Deploy** | Implantação em ambiente | Local (homologação) | TAP §8 |
| **Commit** | Registro de alteração no Git | Assinado pelo GP | TAP §3.2.e |
| **Branch** | Ramificação no Git | main + feature branches | — |
| **Pull Request (PR)** | Solicitação de merge | Code Review obrigatório | ADR-002 |
| **Merge** | Integração de branch | Após aprovação | — |
| **Tag** | Marca de versão no Git | Release final (M4) | TAP §3.2.g |
| **Release** | Versão publicada | MVP funcional (M3) | TAP §3 |

---

## 9. DOCUMENTOS E ARTEFATOS

| Artefato | Definição | Status | Fonte |
|----------|-----------|--------|-------|
| **TAP** | Termo de Abertura do Projeto | ✅ v3 (18/09/2026) | TAP |
| **EAP** | Estrutura Analítica do Projeto | ✅ v2.0 | TAP §4 |
| **OKB** | Operational Knowledge Base | ✅ v2.2 | OKB |
| **ADR** | Architectural Decision Record | ✅ 001, 002, 003 | REQ-12 |
| **Plano de Integração** | Gestão de dependências entre áreas | ⏳ Até 21/09 | OKB §3.1 |
| **Plano de Escopo** | Gestão do escopo do projeto | ⏳ Até 21/09 | OKB §3.1 |
| **Plano de Cronograma** | Gestão do tempo (marcos) | ⏳ Até 21/09 | OKB §3.1 |
| **Plano de Custos** | Gestão de custos (orçamento zero) | ⏳ Até 21/09 | OKB §3.1 |
| **Plano de Qualidade** | Gestão da qualidade (12 PDCAs) | ⏳ Até 21/09 | OKB §3.1 |
| **Plano de Recursos** | Gestão de recursos humanos | ⏳ Até 21/09 | OKB §3.1 |
| **Plano de Comunicações** | Gestão de comunicações | ⏳ Até 21/09 | OKB §3.1 |
| **Plano de Riscos** | Gestão de riscos (R1–R5) | ⏳ Até 21/09 | OKB §3.1 |
| **Catálogo de Prompts SDD** | Registro de prompts de IA | ⏳ Até 03/10 | REQ-13 |
| **Lições Aprendidas** | Registro de aprendizados | Contínuo | EAP N9.2, N12.1 |

---

## 10. PREMISSAS, RESTRIÇÕES E RISCOS

### 10.1 Premissas (TAP §9)

| ID | Premissa | Status |
|----|----------|--------|
| P1 | Governança híbrida (PMBOK 7ª + 6ª + Kanban) | ✅ Vigente |
| P2 | FOSS absoluto | ✅ Vigente |
| P3 | SDD com IA auditável | ✅ Vigente |
| P4 | Código-fonte é deliverable formal | ✅ Vigente |
| P5 | 20h/semana por membro | ✅ Vigente |
| P6 | Hardware adequado e suficiente | ✅ Revisada (hardware.md) |
| P7 | GP = CCB único; Prof. Nivaldo = avaliador | ✅ Vigente |
| P8 | Aquisições e Partes Interessadas simplificadas | ✅ Vigente |

### 10.2 Restrições (TAP §8)

| Categoria | Restrição |
|-----------|-----------|
| Escopo | MVP acadêmico; desenvolvimento do zero |
| Cronograma | 2 bimestres; marco 22/09/2026 |
| Custo | Orçamento zero; proibição de ferramentas pagas |
| Recursos | Equipe de 3 pessoas; hardware adequado |
| Qualidade | Testes com tempo limitado; validação acadêmica |
| Riscos | Sem contingência formal; APIs gratuitas |
| Tecnológicas | FOSS obrigatório; SDD experimental; licença open source |

### 10.3 Riscos (TAP §10)

| ID | Risco | Severidade |
|----|-------|------------|
| R1 | Entrega parcial (22/09) não concluída | ALTA |
| R2 | Stack instável/incompatível | ALTA |
| R3 | Sobrecarga da equipe (burnout) | ALTA |
| R4 | Coverage < 80% | ALTA |
| R5 | API externa indisponível | MÉDIA-ALTA |

---

## 11. BRANDS E FERRAMENTAS

| Brand/Ferramenta | Categoria | Licença | Uso no COGME |
|------------------|-----------|---------|--------------|
| **Python** | Linguagem | PSF | Backend |
| **FastAPI** | Framework Web | MIT | API REST |
| **SQLite** | Banco de Dados | Public Domain | Cache + persistência |
| **WeasyPrint** | Gerador PDF | BSD-3 | Emissão de invoice |
| **pytest** | Framework de Testes | MIT | Testes automatizados |
| **coverage.py** | Medidor de Coverage | Apache 2.0 | Métrica de qualidade |
| **GitHub** | Plataforma DevOps | Proprietário gratuito | SSOT + CI/CD |
| **GitHub Projects** | Gestão de Trabalho | Proprietário gratuito | Kanban |
| **GitHub Actions** | CI/CD | Proprietário gratuito | Pipeline |
| **Docker** | Containerização | Apache 2.0 | Isolamento de ambiente |
| **Arch Linux** | Sistema Operacional | GPL | Ambiente de desenvolvimento |
| **GNOME** | Desktop Environment | GPL | Interface gráfica |
| **QwenStudio** | LLM (IA Generativa) | Licença autorizada | SDD |
| **AMD Ryzen 7 8700G** | CPU | — | Hardware local |
| **Radeon 780M** | GPU | — | Hardware local |
| **Kingston NV2** | SSD NVMe | — | Armazenamento |

---

## 12. ACRÔNIMOS E SIGLAS GERAIS

| Acrônimo | Significado | Contexto |
|----------|-------------|----------|
| **ADS** | Análise e Desenvolvimento de Sistemas | Curso Fatec |
| **API** | Application Programming Interface | Backend |
| **ACID** | Atomicity, Consistency, Isolation, Durability | SQLite |
| **CI/CD** | Continuous Integration / Continuous Delivery | DevOps |
| **CFD** | Cumulative Flow Diagram | Kanban |
| **CCB** | Change Control Board | Governança |
| **DER** | Diagrama Entidade-Relacionamento | Modelagem de dados |
| **DoD** | Definition of Done | Kanban |
| **DoR** | Definition of Ready | Kanban |
| **EAP** | Estrutura Analítica do Projeto | PMBOK |
| **EVM** | Earned Value Management | LEGADO |
| **FOSS** | Free and Open Source Software | Restrição |
| **Fatec** | Faculdade de Tecnologia | Instituição |
| **GMV** | Governança Mínima Viável | Princípio |
| **GP** | Gerente de Projeto | Papel |
| **HTML** | HyperText Markup Language | Frontend |
| **IA** | Inteligência Artificial | SDD |
| **IOF** | Imposto sobre Operações Financeiras | Regra de negócio |
| **KISS** | Keep It Simple, Stupid | Princípio |
| **LLM** | Large Language Model | SDD |
| **MVP** | Minimum Viable Product | Escopo |
| **NVMe** | Non-Volatile Memory Express | Hardware |
| **OSI** | Open Source Initiative | Licenças |
| **PDF** | Portable Document Format | Entrega |
| **PDCA** | Plan-Do-Check-Act | Qualidade |
| **PMI** | Project Management Institute | Padrão |
| **PMO** | Project Management Office | Referência |
| **PR** | Pull Request | Git |
| **RAM** | Random Access Memory | Hardware |
| **REST** | Representational State Transfer | API |
| **SDD** | Specification-Driven Development | Abordagem |
| **SMART** | Specific, Measurable, Achievable, Relevant, Time-bound | Objetivos |
| **SO** | Sistema Operacional | Hardware |
| **SPI** | Schedule Performance Index | LEGADO |
| **SQL** | Structured Query Language | Banco de dados |
| **SSOT** | Single Source of Truth | Kanban |
| **TAP** | Termo de Abertura do Projeto | Governança |
| **TDD** | Test-Driven Development | Qualidade |
| **UAT** | User Acceptance Testing | Qualidade |
| **UX/UI** | User Experience / User Interface | Design |
| **WBS** | Work Breakdown Structure (EAP) | PMBOK |
| **WIP** | Work In Progress | Kanban |
| **YAGNI** | You Aren't Gonna Need It | Princípio |

---

## 13. TERMOS TÉCNICOS ESPECÍFICOS

| Termo | Definição | Contexto COGME |
|-------|-----------|----------------|
| **Adapter Pattern** | Padrão de projeto para abstrair provedores externos | API de câmbio (R5) |
| **Async/Await** | Paradigma de programação assíncrona | FastAPI |
| **Cache** | Armazenamento temporário de dados | SQLite (REQ-07) |
| **Endpoint** | URL de acesso a recurso da API | FastAPI routes |
| **Invoice** | Fatura comercial internacional | PDF gerado (REQ-04) |
| **Mock** | Simulação de dado/serviço | Fallback de API (R5) |
| **Spread** | Taxa de intermediação financeira | Cálculo cambial (REQ-03) |
| **Throughput** | Vazão de trabalho | Métrica Kanban |

---

**Glossário v2.2 emitido por:** GP Leonardo David Silva Setti  
**Aprovação:** CCB (GP — membro único, TAP v3 §1.c)  
**Data:** 19/09/2026  
**Status:** ✅ Convergente ao TAP v3 + OKB v2.2 + ADRs 001-003  
**Próxima revisão:** Após M1 (22/09/2026) ou quando nova decisão arquitetural for registrada (ADR-004+)