# OKB v2.2 — Operational Knowledge Base (Consolidada)

**Data:** 19/09/2026  
**Status:** Ativa — convergente ao TAP v3 (18/09/2026)  
**Hierarquia de autoridade:** TAP > OKB > Glossário > ADRs  
**Referência matriz:** TAP v3 (18/09/2026) — Leonardo David Silva Setti

---

## 1. DECLARAÇÃO DE GOVERNANÇA (Convergente ao TAP §1.c)

### 1.1 Modelo Híbrido Declarado
- **Governança primária:** PMBOK 7ª edição — princípios e domínios de desempenho
- **Dicionário complementar:** PMBOK 6ª edição — processos utilizados **somente quando necessário**, com **obsolescência assumida** (edição 2017 vs. realidade ágil 2026)
- **Método de execução:** Kanban via GitHub Projects (SSOT — Single Source of Truth)
- **Abordagem de desenvolvimento:** Specification-Driven Development (SDD) com IA generativa auditável

### 1.2 Autoridade de Mudança (CCB)
- **CCB = GP (Leonardo David Silva Setti)** — membro único, conforme TAP v3 §1.c
- **Prof. Dr. Nivaldo Carletto:** stakeholder-avaliador **nos marcos M1–M4**, sem ingerência operacional
- **Trade-off aceito:** Velocidade decisória > colegialidade (justificável academicamente pela simplificação pedagógica do TAP §9 P7)

### 1.3 Obsolescência Formalmente Declarada
> **Declaração de obsolescência assumida:** O PMBOK 6ª (2017) é tratado como dicionário de processos. Processos preditivos (ex: 4.1, 5.2, 6.5, 11.1) são citados apenas para rastreabilidade acadêmica. **Métricas EVM (SPI/CPI) são LEGADO e NÃO APLICÁVEIS** — substituídas por métricas de fluxo Kanban (Cycle Time, Throughput, CFD), conforme TAP §3 "Métricas e Indicadores" e Domínio de Medição PMBOK 7ª.

---

## 2. CORREÇÕES CRÍTICAS APLICADAS (v2.1 → v2.2)

| Item | v2.1 (Inconsistente) | v2.2 (Corrigido — TAP v3) | Domínio PMBOK 7ª |
|------|----------------------|---------------------------|------------------|
| CCB | "Prof. Nivaldo" | **GP (Leonardo)** — membro único | Abordagem de Desenvolvimento |
| EVM (SPI/CPI) | Métricas ativas (meta ≥ 0.9) | **LEGADO — NÃO APLICÁVEL** | Medição |
| Hardware | "Modesto" (P6) | **Adequado e suficiente** (P6 revisada) | Recursos |
| ADRs | Inexistentes | **3 ADRs obrigatórias** (REQ-12) | Trabalho do Projeto |
| Métricas | Híbridas (EVM + fluxo) | **Exclusivamente fluxo Kanban** | Medição |
| PMBOK 6ª | Sem ressalva | **Obsolescência assumida formalmente** | Abordagem de Desenvolvimento |

---

## 3. ESTRUTURA DO OKB v2.2

### 3.1 Artefatos Obrigatórios (Rastreabilidade TAP → EAP)

| Artefato | Fase EAP | Status | Responsável |
|----------|----------|--------|-------------|
| TAP v3 | N1.2 | ✅ Aprovado (18/09/2026) | Leonardo |
| EAP v2.0 | N1.2 | ✅ Aprovado | Leonardo |
| Plano de Integração | N1.2 | ⏳ Até 21/09 | Leonardo |
| Plano de Escopo | N1.2 | ⏳ Até 21/09 | Fabricio |
| Plano de Cronograma | N1.2 | ⏳ Até 21/09 | Fabricio |
| Plano de Custos | N1.2 | ⏳ Até 21/09 | Fabricio |
| Plano de Qualidade | N1.3 | ⏳ Até 21/09 | Edson |
| ADR-001 (Stack) | N9.1 | ✅ Emitida (19/09) | Leonardo |
| ADR-002 (Kanban) | N9.1 | ✅ Emitida (19/09) | Leonardo |
| ADR-003 (Métricas) | N9.1 | ✅ Emitida (19/09) | Leonardo |
| Catálogo de Prompts SDD | N9.3 | ⏳ Até 03/10 | Leonardo |

### 3.2 Premissas Vigentes (TAP §9)

| ID | Premissa | Status |
|----|----------|--------|
| P1 | Governança híbrida (PMBOK 7ª + 6ª dicionário + Kanban) | ✅ Vigente |
| P2 | FOSS absoluto | ✅ Vigente |
| P3 | SDD com IA auditável | ✅ Vigente |
| P4 | Código-fonte é deliverable formal | ✅ Vigente |
| P5 | 20h/semana por membro | ✅ Vigente |
| P6 | Hardware adequado e suficiente | ✅ **Revisada** (hardware.md comprova) |
| P7 | GP = CCB único; Prof. Nivaldo = avaliador de marcos | ✅ Vigente |
| P8 | Aquisições e Partes Interessadas simplificadas | ✅ Vigente |

### 3.3 Restrições Vigentes (TAP §8)

- Escopo restrito ao MVP acadêmico
- Prazo letivo inegociável (M1: 22/09/2026)
- Orçamento zero (proibição de aquisições pagas)
- Equipe de 3 pessoas (múltiplos papéis)
- Stack 100% FOSS
- Licenciamento final open source (MIT/GPL)

---

## 4. ADRs EMITIDAS

### ADR-001: Stack Tecnológica FOSS

**Status:** Aprovada  
**Data:** 19/09/2026  
**Decisor:** GP Leonardo (CCB)  
**Rastreabilidade:** TAP §3 (Inovação) + §8 (FOSS) + EAP N4.1, N5.1–N5.4

#### Contexto
O projeto exige stack 100% FOSS (restrição TAP §8.4), com capacidade de:
- Backend assíncrono para simulação cambial (REQ-01, latência ≤ 2s)
- Geração de PDF (REQ-04, ≤ 3s)
- Cache local (REQ-07)
- Testes automatizados (REQ-08, coverage ≥ 80%)

#### Decisão
Adoção da seguinte stack (todas licenças OSI-approved):

| Camada | Tecnologia | Licença | Justificativa |
|--------|------------|---------|---------------|
| Backend | Python 3.11 + FastAPI | PSF / MIT | Assíncrono nativo, ecossistema maduro |
| Banco | SQLite | Public Domain | Zero-config, ACID, adequado ao MVP |
| Geração PDF | WeasyPrint | BSD-3-Clause | HTML/CSS → PDF, FOSS |
| Testes | pytest + coverage.py | MIT | Padrão Python, integração CI |
| CI/CD | GitHub Actions (Free Tier) | Proprietário gratuito | Nativo ao SSOT |
| Frontend | HTML5 + CSS3 + JS vanilla | — | KISS, sem framework pesado |
| LLM (SDD) | QwenStudio | Licença autorizada | TAP §3 (Inovação) |

#### Consequências
- ✅ **Positivas:** Zero custo, auditabilidade total, comunidade ativa, compatível com hardware local (TAP P6 revisada)
- ⚠️ **Riscos:** SQLite limita concorrência (aceitável para MVP acadêmico); WeasyPrint exige dependências nativas (glibc, Pango)
- 🔄 **Fallback:** Se FastAPI apresentar curva de aprendizado excessiva → Flask (MIT) como alternativa

#### Trade-offs Aceitos
- Simplicidade (KISS) > Performance extrema
- FOSS absoluto > Conveniência de soluções proprietárias
- SQLite > PostgreSQL (complexidade operacional desnecessária para MVP)

---

### ADR-002: Kanban como Método de Execução

**Status:** Aprovada  
**Data:** 19/09/2026  
**Decisor:** GP Leonardo (CCB)  
**Rastreabilidade:** TAP §1.c + §3 (Métricas) + EAP N1.5, N7

#### Contexto
O TAP declara Kanban como método de execução (P1), mas o glossário v2.1 mencionava "Sprint" e "Sprint Planning" (incompatível com fluxo contínuo). É necessário operacionalizar o método de forma consistente.

#### Decisão
- **Ferramenta:** GitHub Projects (SSOT)
- **Colunas do fluxo:** `Backlog` → `Ready (DoR)` → `In Progress` → `Code Review` → `Done (DoD)`
- **WIP Limits:** 3 cards em `In Progress` por pessoa (Domínio de Equipe PMBOK 7ª — prevenção de burnout, TAP §10 R3)
- **Pull system:** Trabalho puxado por capacidade, não empurrado por cronograma rígido
- **Rituais:**
  - **Daily assíncrona:** GitHub Issues (15min/dia)
  - **Refinement semanal:** Product Backlog (30min)
  - **Retrospectiva quinzenal:** Risk backlog + lições aprendidas
- **Sprints:** **NÃO utilizadas** — fluxo contínuo (TAP §3 "Métricas")

#### Consequências
- ✅ **Positivas:** Flexibilidade, visibilidade total, métricas de fluxo nativas (GitHub Insights)
- ⚠️ **Riscos:** Requer disciplina de WIP limits; risco de cards parados em `Code Review`
- 🔄 **Fallback:** Se throughput cair abaixo de 3 cards/semana por 2 semanas consecutivas → revisar WIP limits

#### Mapeamento Domínios PMBOK 7ª → Rituais Kanban

| Domínio PMBOK 7ª | Ritual Kanban | Artefato |
|------------------|---------------|----------|
| Stakeholders | Refinement semanal | Backlog refinado |
| Equipe | Daily assíncrona + WIP limits | GitHub Projects |
| Abordagem de Desenvolvimento | Fluxo contínuo (sem sprints) | CFD |
| Planejamento | Refinement + Priorização | Backlog ordenado |
| Trabalho do Projeto | Pull system | Cards em fluxo |
| Entrega | DoD + Code Review | Incrementos validados |
| Medição | Cycle Time + Throughput | GitHub Insights |
| Incerteza | Retrospectiva + Risk backlog | Lições aprendidas |

#### Trade-offs Aceitos
- Fluxo contínuo > Iterações time-boxed (adequado à equipe de 3 pessoas)
- GitHub Projects > Jira/Trello (integração nativa ao SSOT, zero custo)

---

### ADR-003: Métricas de Fluxo (Substituição de EVM)

**Status:** Aprovada  
**Data:** 19/09/2026  
**Decisor:** GP Leonardo (CCB)  
**Rastreabilidade:** TAP §3 (Métricas) + §11.3 (implícito) + Domínio de Medição PMBOK 7ª

#### Contexto
O glossário v2.1 listava SPI/CPI (EVM — PMBOK 6ª) como métricas ativas. O TAP §3 declara explicitamente uso de **métricas de fluxo Kanban**. Há conflito que deve ser resolvido.

#### Análise Técnica
- **EVM (SPI/CPI):** Projetado para ambientes preditivos com linha de base de custos. Inaplicável ao COGME porque:
  - Orçamento zero (TAP §11) → AC (Actual Cost) = 0 → CPI indeterminado
  - Escopo emergente (Kanban) → PV (Planned Value) não faz sentido em fluxo contínuo
- **Métricas de fluxo Kanban:** Alinhadas ao Domínio de Medição PMBOK 7ª e à realidade ágil do projeto

#### Decisão
**Métricas oficiais do COGME (exclusivas):**

| Métrica | Fórmula | Meta | Frequência |
|---------|---------|------|------------|
| **Cycle Time** | Média (Done − In Progress) | ≤ 3 dias | Semanal |
| **Throughput** | Cards concluídos / semana | ≥ 5 cards | Semanal |
| **CFD (Cumulative Flow Diagram)** | Visualização de gargalos | Sem bandas largas | Semanal |
| **WIP em fluxo** | Cards em `In Progress` | ≤ 9 (3 × 3 pessoas) | Contínuo |
| **Coverage** | Linhas testadas / totais | ≥ 80% | Por push (CI) |

**Métricas LEGADO (NÃO APLICÁVEIS):**
- ❌ SPI (Schedule Performance Index)
- ❌ CPI (Cost Performance Index)
- ❌ EVM (Earned Value Management)

> **Declaração formal:** SPI/CPI são removidos do glossário v2.2 e marcados como "LEGADO — NÃO APLICÁVEL — Substituído por métricas de fluxo Kanban (ADR-003)".

#### Consequências
- ✅ **Positivas:** Alinhamento ao Manifesto Ágil, métricas nativas do GitHub, foco em valor entregue
- ⚠️ **Riscos:** Exige calibração inicial (23/09 a 03/10) para estabelecer baseline realista
- 🔄 **Fallback:** Se baseline indicar throughput < 3 cards/semana após 03/10 → revisar escopo do MVP (gestão de mudanças)

#### Período de Calibração
- **Início:** 23/09/2026
- **Fim:** 03/10/2026
- **Objetivo:** Coletar dados reais para estabelecer metas factíveis (TAP §3 "Métricas e Indicadores")
- **Saída:** Baseline documentada + metas ajustadas (se necessário via change-request)

#### Trade-offs Aceitos
- Métricas de fluxo > EVM (adequação ao contexto ágil)
- Baseline empírica > Metas arbitrárias (Domínio de Medição PMBOK 7ª)

---

## 5. GLOSSÁRIO v2.2 — CORREÇÕES APLICADAS

### 5.1 Termos Corrigidos

| Termo | v2.1 | v2.2 (Corrigido) |
|-------|------|------------------|
| CCB | "Comitê de controle de mudanças (Prof. Nivaldo)" | **"Comitê de controle de mudanças (GP Leonardo — membro único, TAP v3 §1.c)"** |
| SPI | "Índice de desempenho do cronograma (meta: ≥ 0.9)" | **"LEGADO — NÃO APLICÁVEL — Substituído por Cycle Time (ADR-003)"** |
| CPI | "Índice de desempenho de custos (meta: ≥ 0.9)" | **"LEGADO — NÃO APLICÁVEL — Substituído por Throughput (ADR-003)"** |
| EVM | "Gestão de valor agregado (substituído por métricas de fluxo)" | **"LEGADO — NÃO APLICÁVEL — Orçamento zero inviabiliza EVM (ADR-003)"** |
| Sprint | "Iteração time-boxed (não usado no COGME)" | **"NÃO UTILIZADO — Fluxo contínuo Kanban (ADR-002)"** |
| Hardware (P6) | "Modesto" (restrição) | **"Adequado e suficiente" (premissa revisada — hardware.md comprova)** |

### 5.2 Termos Adicionados

| Termo | Definição | Contexto |
|-------|-----------|----------|
| SSOT | Single Source of Truth | GitHub Projects como fonte única de verdade (ADR-002) |
| Baseline (Kanban) | Dados empíricos de fluxo após calibração | Período 23/09 a 03/10 (ADR-003) |
| GMV | Governança Mínima Viável | Princípio de priorização documental (TAP §10 R1) |
| DoR | Definition of Ready | Critérios para card entrar em `Ready` (ADR-002) |
| DoD | Definition of Done | Critérios para card ir para `Done` (ADR-002) |

---

## 6. RASTREABILIDADE CONSOLIDADA (TAP → OKB → ADRs)

| TAP § | OKB v2.2 | ADR | Domínio PMBOK 7ª |
|-------|----------|-----|------------------|
| §1.c (Governança) | §1.1, §1.2 | ADR-002 | Abordagem de Desenvolvimento |
| §3 (Métricas) | §3.2 (P1–P8) | ADR-003 | Medição |
| §3 (Inovação) | §4 (ADRs) | ADR-001 | Trabalho do Projeto |
| §8 (Restrições FOSS) | §3.3 | ADR-001 | Abordagem de Desenvolvimento |
| §9 (Premissas) | §3.2 (P6 revisada) | — | Recursos |
| §10 (Riscos) | §3.2 (P5 — burnout) | ADR-002 (WIP limits) | Equipe |
| REQ-12 (ADRs) | §4 (3 ADRs emitidas) | ADR-001, 002, 003 | Trabalho do Projeto |

---

## 7. PRÓXIMOS PASSOS (Pré-M1: 22/09/2026)

| Ação | Responsável | Prazo | Prioridade |
|------|-------------|-------|------------|
| Consolidar OKB v2.2 no repositório | Leonardo | 20/09 | **CRÍTICA** |
| Atualizar glossário para v2.2 | Leonardo | 20/09 | ALTA |
| Configurar GitHub Projects (colunas + WIP) | Leonardo | 20/09 | **CRÍTICA** |
| Redigir Plano de Integração (GMV) | Leonardo | 21/09 | ALTA |
| Redigir Plano de Escopo | Fabricio | 21/09 | ALTA |
| Redigir Plano de Qualidade (12 PDCAs + Ishikawa) | Edson | 21/09 | ALTA |
| Submeter M1 via GitHub | Leonardo | 22/09 | **CRÍTICA** |

---

**OKB v2.2 emitido por:** GP Leonardo David Silva Setti  
**Aprovação:** CCB (GP — membro único, TAP v3 §1.c)  
**Data:** 19/09/2026  
**Status:** ✅ Convergente ao TAP v3 — pronto para M1