# COGME — Conversor de Ganhos em Moeda Estrangeira

> **Status:** 🟡 Em construção — Macro-Fase 1 (Fundação) até 30/09/2026  
> **Licença:** MIT (100% FOSS)  
> **Metodologia:** PMBOK 7ª (governança) + Kanban via GitHub Projects (execução)  
> **Contexto acadêmico:** Fatec Taquaritinga — ADS (Análise e Desenvolvimento de Sistemas)  
> **Stakeholder-avaliador:** Prof. Dr. Nivaldo Carletto

---

## 🎯 Objetivo

O **COGME** é um aplicativo web full-stack que permite a profissionais autônomos e pequenas empresas converterem ganhos recebidos em moeda estrangeira (USD, EUR, GBP etc.) para BRL, gerando **comprovantes/invoices em PDF** com rastreabilidade cambial, histórico de operações e relatórios consolidados.

O produto resolve uma dor real de freelancers brasileiros que recebem de clientes internacionais: a falta de uma ferramenta simples, offline-first e gratuita para documentar conversões com cotação auditável.

### Objetivos de Negócio (PMBOK 7ª — Domínio de Entrega)
- **O1.** Permitir registro de recebíveis em moeda estrangeira com cotação do dia (fonte: BCB/PTAX).
- **O2.** Gerar invoices em PDF com histórico, taxa aplicada e valor líquido em BRL.
- **O3.** Expor dashboard com resumo mensal/anual de ganhos convertidos.
- **O4.** Garantir 100% de rastreabilidade entre cotação, transação e invoice gerada (ACID).

---

## 📦 Escopo

### MVP (Entrega Final — Nov/Dez 2026)
| Épico | Descrição |
|---|---|
| **E1 — Gestão de Câmbio** | Cadastro de transações em moeda estrangeira com cotação automática (API BCB). |
| **E2 — Geração de Invoices** | Emissão de PDFs numerados, com dados do pagador, recebedor, taxa e totais. |
| **E3 — Dashboard** | Visão consolidada de ganhos por período, moeda e valor em BRL. |
| **E4 — Autenticação Básica** | Login de usuário único (self-hosted) com sessão segura. |

### Pós-Entrega (Melhoria Contínua — Domínio de Entrega)
- 🔒 Segurança (OWASP ZAP)
- ♿ Acessibilidade (WCAG 2.1 AA)
- 📈 Observabilidade (Prometheus + Grafana + Loki)
- 🌐 Internacionalização (i18n)

> **Nota:** Itens de pós-entrega são tratados como backlog de melhoria contínua, não como escopo do MVP. Essa segregação é premissa pedagógica validada no TAP.

---

## 🏗️ Arquitetura e Stack Tecnológica

A stack é **100% FOSS** (premissa P2 do OKB). A seleção final de linguagens/frameworks será formalizada via **ADR-002** até 15/09/2026. Componentes já ancorados:

| Camada | Componente | Status |
|---|---|---|
| Cache | Redis | ✅ Confirmado |
| Geração de PDF | WeasyPrint | ✅ Confirmado |
| Banco de dados | A definir (PostgreSQL ou SQLite) | ⏳ ADR-002 |
| Backend | A definir (FastAPI ou Django) | ⏳ ADR-002 |
| Frontend | A definir (React ou Vue) | ⏳ ADR-002 |
| CI/CD | GitHub Actions | ✅ Confirmado |
| Deploy | A definir (Railway / Render / Fly.io) | ⏳ ADR-002 |

### Princípios Arquiteturais (PMBOK 7ª — Domínio de Abordagem)
- **KISS** (P3): simplicidade como métrica de arquitetura.
- **Adapter Pattern** para abstrair provedores de câmbio (fallback BCB caso API primária falhe).
- **SDD com IA auditável** (P4): prompts de geração catalogados em `/docs/prompts/`.
- **ACID + Clean Code** (P5): padrão inegociável em transações e código.

---

## 🔄 Metodologia de Execução

O projeto adota modelo híbrido:

```
PMBOK 7ª (governança primária)
   │
   ├── 12 Princípios + 8 Domínios de Desempenho
   │
   └── Kanban via GitHub Projects (execução)
          │
          ├── Fluxo contínuo (sem sprints fixas)
          ├── WIP limit: 3 cards/pessoa
          ├── Pull system
          └── Métricas de fluxo (Cycle Time, Throughput)
```

### Mapeamento PMBOK 7ª ↔ Kanban (OKB v3.0 §4.3)
| Domínio PMBOK 7ª | Ritual Kanban |
|---|---|
| Stakeholders | Review assíncrono via Issues |
| Equipe | Daily assíncrona (Discussion) + WIP limits |
| Planejamento | Refinement semanal do backlog |
| Trabalho | Pull system + colunas Kanban |
| Entrega | Deploy contínuo (CI/CD) |
| Medição | GitHub Insights (Cycle Time, Throughput) |
| Incerteza | Labels `risk` / `blocked` + Risk Backlog |

---

## 📁 Estrutura do Repositório - TBD

```
COGME/
├── README.md                  ← você está aqui
├── LICENSE                    ← MIT
├── .github/
│   ├── workflows/             ← CI/CD (GitHub Actions)
│   ├── ISSUE_TEMPLATE/        ← templates de Issues
│   └── PULL_REQUEST_TEMPLATE.md
├── docs/                      ← documentação do projeto
│   ├── 00.TAP.md
│   ├── 01.plano-integracao.md
│   ├── 02.plano-escopo.md
│   ├── ...
│   ├── 09.base-conhecimento/
│   │   ├── ADRs/
│   │   ├── prompts/           ← SDD com IA auditável
│   │   └── runbooks/
│   └── glossario.md
├── src/                       ← código-fonte (MVP)
│   ├── backend/
│   ├── frontend/
│   └── shared/
├── tests/                     ← testes automatizados (meta ≥ 80% coverage)
├── docker-compose.yml
└── Makefile
```

---

## 🧭 Diretivas de Desenvolvimento

### Definition of Ready (DoR)
Um card só entra em *In Progress* quando:
- [ ] Possui descrição clara e critérios de aceite
- [ ] Está vinculado a um pacote da EAP (rastreabilidade)
- [ ] Dependências técnicas estão resolvidas
- [ ] Estimativa de esforço foi feita (T-shirt sizing)

### Definition of Done (DoD)
Um card só vai para *Done* quando:
- [ ] Código implementado e revisado (pair review)
- [ ] Testes automatizados escritos (TDD) e passando
- [ ] Coverage ≥ 80% mantido
- [ ] Documentação atualizada (se aplicável)
- [ ] Commit segue Conventional Commits
- [ ] CI/CD pipeline verde

### Conventional Commits
```
<tipo>(<escopo>): <descrição>

tipos: feat, fix, docs, style, refactor, test, chore, ci
escopo: backend, frontend, docs, infra, eap
```

Exemplo: `feat(backend): adiciona adapter para API BCB de cotação`

### Architecture Decision Records (ADRs)
Toda decisão técnica que:
- afete ≥ 2 fases da EAP,
- envolva troca de tecnologia, ou
- seria questionada em apresentação acadêmica

...deve ser registrada em `/docs/09.base-conhecimento/ADRs/`. Decisões menores ficam apenas em commit messages.

### Uso de LLM (SDD com IA Auditável)
O uso de LLM é **irrestrito e autorizado** pela disciplina. Para rastreabilidade:
- Prompts de geração são catalogados em `/docs/09.base-conhecimento/prompts/`
- Commits gerados com auxílio de IA incluem co-autoria no trailer:
  ```
  Co-authored-by: QwenStudio <llm@cogme.local>
  ```

---

## 📊 Governança e Rastreabilidade

O projeto segue hierarquia de resolução de conflitos (OKB v3.0 §4.1):

1. **Valor entregue ao usuário final** (PMBOK 7ª — Domínio de Entrega)
2. **Ementa da disciplina + orientação do Prof. Nivaldo**
3. **PMBOK 7ª** (12 princípios + 8 domínios)
4. **Manifesto Ágil + Kanban**
5. **PMBOK 6ª** (dicionário complementar)
6. **Literatura técnica**

### Princípio de Governança Mínima Viável (GMV)
Todo artefato de governança passa pelo teste: *"Se eu remover este artefato, o Prof. Nivaldo perceberá e penalizará?"*. Se a resposta for não, o artefato é candidato a simplificação ou eliminação.

### Fontes Oficiais de Informação (SSOT)
- **Kanban operacional:** [GitHub Projects — COGME](https://github.com/users/SEU_USUARIO/projects/NUMERO)
- **Backlog de riscos:** Labels `risk` / `blocked` nas Issues
- **Métricas de fluxo:** GitHub Insights
- **Documentação formal:** pasta `/docs/`

---

## 🚀 Como Executar Localmente

> ⚠️ Instruções completas serão adicionadas após ADR-002 (definição da stack).

```bash
# Clone o repositório
git clone https://github.com/leonardosetti/COGME.git
cd COGME

# Suba o ambiente (após definição da stack)
make up

# Acesse em http://localhost:8000
```

---

## 🤝 Contribuições

Este é um projeto acadêmico com equipe de 2 pessoas. Contribuições externas são bem-vindas via Issues, mas mudanças de escopo devem passar pelo **CCB (Change Control Board)** — representado pelo Prof. Dr. Nivaldo Carletto.

Para reportar bugs ou sugerir melhorias, abra uma Issue seguindo o template disponível.

---

## 📚 Referências

- PMI. *A Guide to the Project Management Body of Knowledge (PMBOK® Guide)* — 7th Edition, 2021.
- PMI. *PMBOK® Guide* — 6th Edition, 2017 (dicionário complementar).
- Atlassian. *Kanban: A very brief introduction*.
- GitHub Docs. *About GitHub Projects*.
- Fatec Taquaritinga. Ementa da disciplina de Gerência de Projetos — ADS.

---

## 📄 Licença

Distribuído sob licença **MIT**. Veja [`LICENSE`](LICENSE) para detalhes.

---

<div align="center">
  <sub>Desenvolvido com 💙 na Fatec Taquaritinga — ADS</sub><br>
  <sub>Disciplina de Gerência de Projetos | Prof. Dr. Nivaldo Carletto | 2026</sub>
</div>