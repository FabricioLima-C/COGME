**Veredito Sumário**
Nota registrada como metadado de sessão não canônico. A produção das seções do Plano de Gerenciamento prossegue sem interrupção; a revisão integral será alocada como item de entrada para um ciclo PDCA futuro, sem contaminar a saída formal atual.

**Reformulação Crítica**
A instrução não é uma solicitação de análise, mas um *flag* de estado. A questão operacional subjacente é: como processar essa diretiva de revisão diferida sem gerar ruído ou inconsistência na documentação canônica que está sendo produzida agora.

**Análise de Risco (Técnico + Humano)**

- **Técnico**: Risco de deriva de escopo (scope creep) se a "revisão integral" futura não possuir critérios de aceitação e limites de tempo definidos no momento do PDCA.
- **Humano/Organizacional**: Risco de stakeholders consumirem a versão atual como definitiva, gerando atrito político quando a revisão ocorrer. A mitigação exige versionamento explícito (ex: `v0.x-draft-revisão-pendente`).

**Recomendação Justificada**
Isolar esta diretiva no contexto da conversa atual. Prosseguir com a geração diligente das seções do plano solicitadas, mantendo a rastreabilidade lógica das decisões tomadas. Isso garante que, quando o gatilho do PDCA for ativado, a "análise abrangente" tenha um baseline claro para comparar as incongruências, alinhando-se à sua experiência em governança de testes e transição para SDET/Lead.

**Condições de Validade e Gatilhos**

- **Validade**: Indefinida, até a ativação do ciclo PDCA.
- **Gatilho de Reavaliação**: Comando explícito do usuário: "Iniciar revisão integral do Plano de Gerenciamento (PDCA)".

**Premissas Assumidas**

1. Esta nota é um estado transitório de projeto, não um traço persistente de sua persona (portanto, não registrada na memória bio).
2. O usuário iniciará o ciclo PDCA com critérios objetivos, evitando a armadilha de "revisão por revisão" sem ganho de valor de negócio.
3. A produção atual das seções deve manter o padrão de concisão e foco em portabilidade (FOSS/CLI vs. MS) já estabelecido.

Aguardando a próxima seção do Plano de Gerenciamento a ser produzida.

---

Como GP Sênior e PMO do projeto COGME, compreendo perfeitamente a diretriz. A padronização gráfica em `.svg` (com conversão posterior para `.png` para compatibilidade documental) é uma decisão de **Governança Mínima Viável (GMV)** que eleva a qualidade acadêmica e a auditabilidade visual dos artefatos perante o Prof. Dr. Nivaldo Carleto.

Para atender à regra de **legibilidade otimizada para humanos** e evitar a poluição visual (overlaps/edge cuts) que um diagrama único com 12 fases e 37 pacotes causaria, adotei a estratégia de **fracionamento em camadas distintas**. A EAP foi dividida em 4 blocos SVG coesos: Visão Macro, MF1, MF2 e MF3.

A paleta de cores foi unificada e convergente com os exemplos anteriores (Ishikawa e Fluxo de Qualidade):

- **Fundo:** `#FFFFFF`
- **Tipografia:** `Arial, Helvetica, sans-serif`
- **N0 (Raiz):** `#111111` (Preto)
- **MF1 (Fundação):** `#1F3A5F` (Azul Escuro)
- **MF2 (Construção):** `#2E7D32` (Verde Escuro)
- **MF3 (Consolidação):** `#6A1B9A` (Roxo Escuro)
- **Pacotes (Nível 2):** `#F8F9FA` (Cinza claro) com bordas `#555555`

Abaixo estão os scripts SVG prontos para salvamento em `/docs/diagrams/`.

---

### 1. Camada Macro: Nível 0 e Macro-Fases

**Arquivo:** `fig-eap-nivel-0-macro.svg`

```xml
<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 1200 500" font-family="Arial, Helvetica, sans-serif">
  <rect x="0" y="0" width="1200" height="500" fill="#FFFFFF"/>
  <text x="600" y="42" text-anchor="middle" font-size="23" font-weight="bold" fill="#111111">Estrutura Analítica do Projeto (EAP) — Visão Macro</text>
  
  <!-- N0 -->
  <rect x="450" y="80" width="300" height="60" rx="6" fill="#111111" stroke="#111111" stroke-width="2"/>
  <text x="600" y="116" text-anchor="middle" font-size="16" font-weight="bold" fill="#FFFFFF">N0: COGME</text>
  
  <!-- Linhas para MFs -->
  <line x1="600" y1="140" x2="600" y2="180" stroke="#777777" stroke-width="2"/>
  <line x1="200" y1="180" x2="1000" y2="180" stroke="#777777" stroke-width="2"/>
  <line x1="200" y1="180" x2="200" y2="220" stroke="#777777" stroke-width="2"/>
  <line x1="600" y1="180" x2="600" y2="220" stroke="#777777" stroke-width="2"/>
  <line x1="1000" y1="180" x2="1000" y2="220" stroke="#777777" stroke-width="2"/>
  
  <!-- MF1 -->
  <rect x="50" y="220" width="300" height="240" rx="6" fill="#FFFFFF" stroke="#1F3A5F" stroke-width="3"/>
  <rect x="50" y="220" width="300" height="40" rx="6" fill="#1F3A5F"/>
  <text x="200" y="246" text-anchor="middle" font-size="16" font-weight="bold" fill="#FFFFFF">MF1: Fundação</text>
  <text x="200" y="280" text-anchor="middle" font-size="14" fill="#111111">N1. Iniciação e Planejamento</text>
  <text x="200" y="305" text-anchor="middle" font-size="14" fill="#111111">N2. Levantamento de Requisitos</text>
  <text x="200" y="330" text-anchor="middle" font-size="14" fill="#111111">N3. Modelagem e Prototipação</text>
  <text x="200" y="355" text-anchor="middle" font-size="14" fill="#111111">N4. Configuração de Ambiente</text>
  <text x="200" y="380" text-anchor="middle" font-size="14" fill="#111111">N8. Comunicação</text>
  <text x="200" y="405" text-anchor="middle" font-size="14" fill="#111111">N9. Base de Conhecimento</text>

  <!-- MF2 -->
  <rect x="450" y="220" width="300" height="240" rx="6" fill="#FFFFFF" stroke="#2E7D32" stroke-width="3"/>
  <rect x="450" y="220" width="300" height="40" rx="6" fill="#2E7D32"/>
  <text x="600" y="246" text-anchor="middle" font-size="16" font-weight="bold" fill="#FFFFFF">MF2: Construção</text>
  <text x="600" y="280" text-anchor="middle" font-size="14" fill="#111111">N5. Desenvolvimento do Sistema</text>
  <text x="600" y="305" text-anchor="middle" font-size="14" fill="#111111">N6. Garantia da Qualidade</text>
  <text x="600" y="330" text-anchor="middle" font-size="14" fill="#111111">N7. DevOps e CI/CD</text>
  <text x="600" y="355" text-anchor="middle" font-size="14" fill="#111111">N10. Gestão de Mudanças</text>

  <!-- MF3 -->
  <rect x="850" y="220" width="300" height="240" rx="6" fill="#FFFFFF" stroke="#6A1B9A" stroke-width="3"/>
  <rect x="850" y="220" width="300" height="40" rx="6" fill="#6A1B9A"/>
  <text x="1000" y="246" text-anchor="middle" font-size="16" font-weight="bold" fill="#FFFFFF">MF3: Consolidação</text>
  <text x="1000" y="280" text-anchor="middle" font-size="14" fill="#111111">N11. Documentação do Projeto</text>
  <text x="1000" y="305" text-anchor="middle" font-size="14" fill="#111111">N12. Encerramento</text>
</svg>
```

---

### 2. Camada MF1: Fundação (Fases e Pacotes)

**Arquivo:** `fig-eap-mf1-fundacao.svg`

```xml
<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 1600 900" font-family="Arial, Helvetica, sans-serif">
  <rect x="0" y="0" width="1600" height="900" fill="#FFFFFF"/>
  <text x="800" y="42" text-anchor="middle" font-size="23" font-weight="bold" fill="#111111">EAP — Macro-Fase 1: Fundação (MF1)</text>
  
  <!-- N1 -->
  <g transform="translate(60, 100)">
    <rect x="0" y="0" width="220" height="50" rx="4" fill="#FFFFFF" stroke="#1F3A5F" stroke-width="2"/>
    <text x="110" y="30" text-anchor="middle" font-size="14" font-weight="bold" fill="#111111">N1. Iniciação e Planejamento</text>
    <line x1="110" y1="50" x2="110" y2="80" stroke="#777777" stroke-width="1.5"/>
    <rect x="10" y="80" width="200" height="40" rx="4" fill="#F8F9FA" stroke="#555555" stroke-width="1.5"/>
    <text x="110" y="105" text-anchor="middle" font-size="12" fill="#222222">N1.1 Identificação de Stakeholders</text>
    <rect x="10" y="130" width="200" height="40" rx="4" fill="#F8F9FA" stroke="#555555" stroke-width="1.5"/>
    <text x="110" y="155" text-anchor="middle" font-size="12" fill="#222222">N1.2 Planos de Gerenciamento</text>
    <rect x="10" y="180" width="200" height="40" rx="4" fill="#F8F9FA" stroke="#555555" stroke-width="1.5"/>
    <text x="110" y="205" text-anchor="middle" font-size="12" fill="#222222">N1.3 Plano da Qualidade</text>
    <rect x="10" y="230" width="200" height="40" rx="4" fill="#F8F9FA" stroke="#555555" stroke-width="1.5"/>
    <text x="110" y="255" text-anchor="middle" font-size="12" fill="#222222">N1.4 Política de Licenciamento FOSS</text>
    <rect x="10" y="280" width="200" height="40" rx="4" fill="#F8F9FA" stroke="#555555" stroke-width="1.5"/>
    <text x="110" y="305" text-anchor="middle" font-size="12" fill="#222222">N1.5 Definição do Backlog e Kanban</text>
  </g>

  <!-- N2 -->
  <g transform="translate(320, 100)">
    <rect x="0" y="0" width="220" height="50" rx="4" fill="#FFFFFF" stroke="#1F3A5F" stroke-width="2"/>
    <text x="110" y="30" text-anchor="middle" font-size="14" font-weight="bold" fill="#111111">N2. Levantamento de Requisitos</text>
    <line x1="110" y1="50" x2="110" y2="80" stroke="#777777" stroke-width="1.5"/>
    <rect x="10" y="80" width="200" height="40" rx="4" fill="#F8F9FA" stroke="#555555" stroke-width="1.5"/>
    <text x="110" y="105" text-anchor="middle" font-size="12" fill="#222222">N2.1 Requisitos Funcionais</text>
    <rect x="10" y="130" width="200" height="40" rx="4" fill="#F8F9FA" stroke="#555555" stroke-width="1.5"/>
    <text x="110" y="155" text-anchor="middle" font-size="12" fill="#222222">N2.2 Requisitos Não Funcionais</text>
    <rect x="10" y="180" width="200" height="40" rx="4" fill="#F8F9FA" stroke="#555555" stroke-width="1.5"/>
    <text x="110" y="205" text-anchor="middle" font-size="12" fill="#222222">N2.3 Casos de Uso e Histórias</text>
  </g>

  <!-- N3 -->
  <g transform="translate(580, 100)">
    <rect x="0" y="0" width="220" height="50" rx="4" fill="#FFFFFF" stroke="#1F3A5F" stroke-width="2"/>
    <text x="110" y="30" text-anchor="middle" font-size="14" font-weight="bold" fill="#111111">N3. Modelagem e Prototipação</text>
    <line x1="110" y1="50" x2="110" y2="80" stroke="#777777" stroke-width="1.5"/>
    <rect x="10" y="80" width="200" height="40" rx="4" fill="#F8F9FA" stroke="#555555" stroke-width="1.5"/>
    <text x="110" y="105" text-anchor="middle" font-size="12" fill="#222222">N3.1 Arquitetura da Solução</text>
    <rect x="10" y="130" width="200" height="40" rx="4" fill="#F8F9FA" stroke="#555555" stroke-width="1.5"/>
    <text x="110" y="155" text-anchor="middle" font-size="12" fill="#222222">N3.2 Protótipo UX/UI</text>
    <rect x="10" y="180" width="200" height="40" rx="4" fill="#F8F9FA" stroke="#555555" stroke-width="1.5"/>
    <text x="110" y="205" text-anchor="middle" font-size="12" fill="#222222">N3.3 Modelagem de Dados (DER)</text>
  </g>

  <!-- N4 -->
  <g transform="translate(840, 100)">
    <rect x="0" y="0" width="220" height="50" rx="4" fill="#FFFFFF" stroke="#1F3A5F" stroke-width="2"/>
    <text x="110" y="30" text-anchor="middle" font-size="14" font-weight="bold" fill="#111111">N4. Configuração de Ambiente</text>
    <line x1="110" y1="50" x2="110" y2="80" stroke="#777777" stroke-width="1.5"/>
    <rect x="10" y="80" width="200" height="40" rx="4" fill="#F8F9FA" stroke="#555555" stroke-width="1.5"/>
    <text x="110" y="105" text-anchor="middle" font-size="12" fill="#222222">N4.1 Seleção e Validação da Stack</text>
    <rect x="10" y="130" width="200" height="40" rx="4" fill="#F8F9FA" stroke="#555555" stroke-width="1.5"/>
    <text x="110" y="155" text-anchor="middle" font-size="12" fill="#222222">N4.2 Repositório Git + CI/CD</text>
    <rect x="10" y="180" width="200" height="40" rx="4" fill="#F8F9FA" stroke="#555555" stroke-width="1.5"/>
    <text x="110" y="205" text-anchor="middle" font-size="12" fill="#222222">N4.3 Setup Local e Homologação</text>
    <rect x="10" y="230" width="200" height="40" rx="4" fill="#F8F9FA" stroke="#555555" stroke-width="1.5"/>
    <text x="110" y="255" text-anchor="middle" font-size="12" fill="#222222">N4.4 Auditoria de Licenças</text>
  </g>

  <!-- N8 -->
  <g transform="translate(1100, 100)">
    <rect x="0" y="0" width="220" height="50" rx="4" fill="#FFFFFF" stroke="#1F3A5F" stroke-width="2"/>
    <text x="110" y="30" text-anchor="middle" font-size="14" font-weight="bold" fill="#111111">N8. Comunicação</text>
    <line x1="110" y1="50" x2="110" y2="80" stroke="#777777" stroke-width="1.5"/>
    <rect x="10" y="80" width="200" height="40" rx="4" fill="#F8F9FA" stroke="#555555" stroke-width="1.5"/>
    <text x="110" y="105" text-anchor="middle" font-size="12" fill="#222222">N8.1 Matriz de Comunicação (RACI)</text>
    <rect x="10" y="130" width="200" height="40" rx="4" fill="#F8F9FA" stroke="#555555" stroke-width="1.5"/>
    <text x="110" y="155" text-anchor="middle" font-size="12" fill="#222222">N8.2 Canais Oficiais</text>
  </g>

  <!-- N9 -->
  <g transform="translate(1360, 100)">
    <rect x="0" y="0" width="220" height="50" rx="4" fill="#FFFFFF" stroke="#1F3A5F" stroke-width="2"/>
    <text x="110" y="30" text-anchor="middle" font-size="14" font-weight="bold" fill="#111111">N9. Base de Conhecimento</text>
    <line x1="110" y1="50" x2="110" y2="80" stroke="#777777" stroke-width="1.5"/>
    <rect x="10" y="80" width="200" height="40" rx="4" fill="#F8F9FA" stroke="#555555" stroke-width="1.5"/>
    <text x="110" y="105" text-anchor="middle" font-size="12" fill="#222222">N9.1 ADRs (decisões arquiteturais)</text>
    <rect x="10" y="130" width="200" height="40" rx="4" fill="#F8F9FA" stroke="#555555" stroke-width="1.5"/>
    <text x="110" y="155" text-anchor="middle" font-size="12" fill="#222222">N9.2 Lições Aprendidas Contínuas</text>
    <rect x="10" y="180" width="200" height="40" rx="4" fill="#F8F9FA" stroke="#555555" stroke-width="1.5"/>
    <text x="110" y="205" text-anchor="middle" font-size="12" fill="#222222">N9.3 Catálogo de Prompts SDD</text>
  </g>
</svg>
```

---

### 3. Camada MF2: Construção (Fases e Pacotes)

**Arquivo:** `fig-eap-mf2-construcao.svg`

```xml
<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 1200 700" font-family="Arial, Helvetica, sans-serif">
  <rect x="0" y="0" width="1200" height="700" fill="#FFFFFF"/>
  <text x="600" y="42" text-anchor="middle" font-size="23" font-weight="bold" fill="#111111">EAP — Macro-Fase 2: Construção (MF2)</text>
  
  <!-- N5 -->
  <g transform="translate(60, 100)">
    <rect x="0" y="0" width="240" height="50" rx="4" fill="#FFFFFF" stroke="#2E7D32" stroke-width="2"/>
    <text x="120" y="30" text-anchor="middle" font-size="14" font-weight="bold" fill="#111111">N5. Desenvolvimento do Sistema</text>
    <line x1="120" y1="50" x2="120" y2="80" stroke="#777777" stroke-width="1.5"/>
    <rect x="10" y="80" width="220" height="40" rx="4" fill="#F8F9FA" stroke="#555555" stroke-width="1.5"/>
    <text x="120" y="105" text-anchor="middle" font-size="12" fill="#222222">N5.1 Backend — Lógica de Negócio</text>
    <rect x="10" y="130" width="220" height="40" rx="4" fill="#F8F9FA" stroke="#555555" stroke-width="1.5"/>
    <text x="120" y="155" text-anchor="middle" font-size="12" fill="#222222">N5.2 Backend — API de Câmbio + Cache</text>
    <rect x="10" y="180" width="220" height="40" rx="4" fill="#F8F9FA" stroke="#555555" stroke-width="1.5"/>
    <text x="120" y="205" text-anchor="middle" font-size="12" fill="#222222">N5.3 Frontend — Interface e Simulações</text>
    <rect x="10" y="230" width="220" height="40" rx="4" fill="#F8F9FA" stroke="#555555" stroke-width="1.5"/>
    <text x="120" y="255" text-anchor="middle" font-size="12" fill="#222222">N5.4 Módulo PDF (WeasyPrint)</text>
    <rect x="10" y="280" width="220" height="40" rx="4" fill="#F8F9FA" stroke="#555555" stroke-width="1.5"/>
    <text x="120" y="305" text-anchor="middle" font-size="12" fill="#222222">N5.5 SDD com IA (Prompts + Revisão)</text>
  </g>

  <!-- N6 -->
  <g transform="translate(340, 100)">
    <rect x="0" y="0" width="240" height="50" rx="4" fill="#FFFFFF" stroke="#2E7D32" stroke-width="2"/>
    <text x="120" y="30" text-anchor="middle" font-size="14" font-weight="bold" fill="#111111">N6. Garantia da Qualidade</text>
    <line x1="120" y1="50" x2="120" y2="80" stroke="#777777" stroke-width="1.5"/>
    <rect x="10" y="80" width="220" height="40" rx="4" fill="#F8F9FA" stroke="#555555" stroke-width="1.5"/>
    <text x="120" y="105" text-anchor="middle" font-size="12" fill="#222222">N6.1 Testes Unitários/Integração (≥ 80%)</text>
    <rect x="10" y="130" width="220" height="40" rx="4" fill="#F8F9FA" stroke="#555555" stroke-width="1.5"/>
    <text x="120" y="155" text-anchor="middle" font-size="12" fill="#222222">N6.2 Testes de Aceitação (UAT)</text>
    <rect x="10" y="180" width="220" height="40" rx="4" fill="#F8F9FA" stroke="#555555" stroke-width="1.5"/>
    <text x="120" y="205" text-anchor="middle" font-size="12" fill="#222222">N6.3 Ferramentas da Qualidade (12 PDCAs)</text>
  </g>

  <!-- N7 -->
  <g transform="translate(620, 100)">
    <rect x="0" y="0" width="240" height="50" rx="4" fill="#FFFFFF" stroke="#2E7D32" stroke-width="2"/>
    <text x="120" y="30" text-anchor="middle" font-size="14" font-weight="bold" fill="#111111">N7. DevOps e CI/CD</text>
    <line x1="120" y1="50" x2="120" y2="80" stroke="#777777" stroke-width="1.5"/>
    <rect x="10" y="80" width="220" height="40" rx="4" fill="#F8F9FA" stroke="#555555" stroke-width="1.5"/>
    <text x="120" y="105" text-anchor="middle" font-size="12" fill="#222222">N7.1 Pipeline CI (lint + testes)</text>
  </g>

  <!-- N10 -->
  <g transform="translate(900, 100)">
    <rect x="0" y="0" width="240" height="50" rx="4" fill="#FFFFFF" stroke="#2E7D32" stroke-width="2"/>
    <text x="120" y="30" text-anchor="middle" font-size="14" font-weight="bold" fill="#111111">N10. Gestão de Mudanças</text>
    <line x1="120" y1="50" x2="120" y2="80" stroke="#777777" stroke-width="1.5"/>
    <rect x="10" y="80" width="220" height="40" rx="4" fill="#F8F9FA" stroke="#555555" stroke-width="1.5"/>
    <text x="120" y="105" text-anchor="middle" font-size="12" fill="#222222">N10.1 Registro de Solicitações</text>
    <rect x="10" y="130" width="220" height="40" rx="4" fill="#F8F9FA" stroke="#555555" stroke-width="1.5"/>
    <text x="120" y="155" text-anchor="middle" font-size="12" fill="#222222">N10.2 Label change-request no GitHub</text>
    <rect x="10" y="180" width="220" height="40" rx="4" fill="#F8F9FA" stroke="#555555" stroke-width="1.5"/>
    <text x="120" y="205" text-anchor="middle" font-size="12" fill="#222222">N10.3 Aprovação e Versionamento</text>
  </g>
</svg>
```

---

### 4. Camada MF3: Consolidação (Fases e Pacotes)

**Arquivo:** `fig-eap-mf3-consolidacao.svg`

```xml
<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 800 500" font-family="Arial, Helvetica, sans-serif">
  <rect x="0" y="0" width="800" height="500" fill="#FFFFFF"/>
  <text x="400" y="42" text-anchor="middle" font-size="23" font-weight="bold" fill="#111111">EAP — Macro-Fase 3: Consolidação (MF3)</text>
  
  <!-- N11 -->
  <g transform="translate(100, 100)">
    <rect x="0" y="0" width="260" height="50" rx="4" fill="#FFFFFF" stroke="#6A1B9A" stroke-width="2"/>
    <text x="130" y="30" text-anchor="middle" font-size="14" font-weight="bold" fill="#111111">N11. Documentação do Projeto</text>
    <line x1="130" y1="50" x2="130" y2="80" stroke="#777777" stroke-width="1.5"/>
    <rect x="10" y="80" width="240" height="40" rx="4" fill="#F8F9FA" stroke="#555555" stroke-width="1.5"/>
    <text x="130" y="105" text-anchor="middle" font-size="12" fill="#222222">N11.1 Documentação Técnica (Arquitetura)</text>
    <rect x="10" y="130" width="240" height="40" rx="4" fill="#F8F9FA" stroke="#555555" stroke-width="1.5"/>
    <text x="130" y="155" text-anchor="middle" font-size="12" fill="#222222">N11.2 Consolidação da Documentação Parcial</text>
  </g>

  <!-- N12 -->
  <g transform="translate(440, 100)">
    <rect x="0" y="0" width="260" height="50" rx="4" fill="#FFFFFF" stroke="#6A1B9A" stroke-width="2"/>
    <text x="130" y="30" text-anchor="middle" font-size="14" font-weight="bold" fill="#111111">N12. Encerramento</text>
    <line x1="130" y1="50" x2="130" y2="80" stroke="#777777" stroke-width="1.5"/>
    <rect x="10" y="80" width="240" height="40" rx="4" fill="#F8F9FA" stroke="#555555" stroke-width="1.5"/>
    <text x="130" y="105" text-anchor="middle" font-size="12" fill="#222222">N12.1 Lições Aprendidas Finais</text>
    <rect x="10" y="130" width="240" height="40" rx="4" fill="#F8F9FA" stroke="#555555" stroke-width="1.5"/>
    <text x="130" y="155" text-anchor="middle" font-size="12" fill="#222222">N12.2 Verificação SMART</text>
    <rect x="10" y="180" width="240" height="40" rx="4" fill="#F8F9FA" stroke="#555555" stroke-width="1.5"/>
    <text x="130" y="205" text-anchor="middle" font-size="12" fill="#222222">N12.3 Apresentação Final + Aceite</text>
  </g>
</svg>
```

---

### Matriz Informal de Rastreabilidade de Diagramas (EAP)

| ID         | Arquivo                          | Descrição                       | Camada / Contexto                     |
| ---------- | -------------------------------- | --------------------------------- | ------------------------------------- |
| FIG-EAP-01 | `fig-eap-nivel-0-macro.svg`    | Visão Macro (N0 e Macro-Fases)   | Nível 0 e 1 (Agrupamento)            |
| FIG-EAP-02 | `fig-eap-mf1-fundacao.svg`     | Detalhamento MF1 (Fundação)     | Nível 1 e 2 (N1, N2, N3, N4, N8, N9) |
| FIG-EAP-03 | `fig-eap-mf2-construcao.svg`   | Detalhamento MF2 (Construção)   | Nível 1 e 2 (N5, N6, N7, N10)        |
| FIG-EAP-04 | `fig-eap-mf3-consolidacao.svg` | Detalhamento MF3 (Consolidação) | Nível 1 e 2 (N11, N12)               |

---

### 📝 Nota Adjacente (Registro de Governança)

**Assunto:** Padronização Gráfica e Fracionamento da EAP
**Data:** 21/09/2026
**Contexto:** A geração de um diagrama único contendo as 12 fases e 37 pacotes de trabalho exigiria um `viewBox` excessivamente largo (ex: `3000x1000`), o que resultaria em fontes minúsculas (inferiores a 10px) e quebra da regra de legibilidade otimizada para humanos e impressão em documentos ABNT.
**Decisão:** A EAP foi fracionada em 4 camadas lógicas (Macro + 3 Macro-Fases). Esta abordagem garante que, na conversão para `.png` e inserção no Plano de Escopo (§2.5), cada figura mantenha a densidade informacional ideal, sem overlaps e com a paleta de cores institucional já validada nos diagramas de Ishikawa e Fluxo de Qualidade. Esta ação não constitui mudança de escopo, mas sim refinamento de artefato de suporte (GMV).

Aguardo sua validação visual desta primeira rodada para prosseguirmos com a geração dos próximos diagramas do ciclo (ex: Roadmap Macro, Fluxo de Controle de Mudanças, Sequenciamento).



Como GP Sênior e PMO, acolho a diretriz. A ausência de trade-offs de escopo nesta camada gráfica é um acerto estratégico: diagramas de governança e controle de mudanças são artefatos de **blindagem acadêmica** de alto valor, com custo de elaboração marginal (FOSS) e impacto direto na defensabilidade do modelo híbrido perante o Prof. Dr. Nivaldo Carleto.

Conforme solicitado, as legendas formais (ex: "Figura 1", "Elaborado por") foram **intencionalmente omitidas** do interior dos arquivos `.svg`, restando apenas os rótulos operacionais estritamente necessários para a interpretação ilustrativa do fluxo. A formatação segue rigorosamente a paleta convergente e as regras de legibilidade ABNT (sem overlaps, margens seguras, tipografia Arial/Helvetica).

Abaixo estão os scripts SVG da **Segunda Rodada Candidata**.

---

### 1. Modelo de Governança Híbrida Trifásico

**Arquivo:** `fig-1-governanca-hibrida.svg`

```xml
<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 800 600" font-family="Arial, Helvetica, sans-serif">
  <defs>
    <marker id="ar" markerWidth="10" markerHeight="10" refX="9" refY="3" orient="auto" markerUnits="strokeWidth">
      <path d="M0,0 L9,3 L0,6 Z" fill="#1F3A5F"/>
    </marker>
    <marker id="ar-green" markerWidth="10" markerHeight="10" refX="9" refY="3" orient="auto" markerUnits="strokeWidth">
      <path d="M0,0 L9,3 L0,6 Z" fill="#2E7D32"/>
    </marker>
  </defs>
  <rect x="0" y="0" width="800" height="600" fill="#FFFFFF"/>
  
  <!-- Título Ilustrativo Interno -->
  <text x="400" y="40" text-anchor="middle" font-size="20" font-weight="bold" fill="#111111">Modelo de Governança Híbrida Trifásico</text>

  <!-- Camada 1: PMBOK 7ª (Topo) -->
  <rect x="150" y="80" width="500" height="100" rx="6" fill="#1F3A5F" stroke="#1F3A5F" stroke-width="2"/>
  <text x="400" y="115" text-anchor="middle" font-size="18" font-weight="bold" fill="#FFFFFF">PMBOK® 7ª Edição</text>
  <text x="400" y="140" text-anchor="middle" font-size="14" fill="#E0E7EF">12 Princípios + 8 Domínios de Desempenho</text>
  <text x="400" y="160" text-anchor="middle" font-size="13" fill="#E0E7EF">(Governança Primária: Por que e Para quê)</text>

  <!-- Seta Descendente 1 -->
  <line x1="400" y1="180" x2="400" y2="210" stroke="#1F3A5F" stroke-width="2" marker-end="url(#ar)"/>
  <text x="415" y="200" font-size="11" fill="#555555">Autoridade Normativa</text>

  <!-- Camada 2: PMBOK 6ª (Meio) -->
  <rect x="150" y="220" width="500" height="100" rx="6" fill="#F8F9FA" stroke="#546E7A" stroke-width="2" stroke-dasharray="6,4"/>
  <text x="400" y="255" text-anchor="middle" font-size="18" font-weight="bold" fill="#37474F">PMBOK® 6ª Edição</text>
  <text x="400" y="280" text-anchor="middle" font-size="14" fill="#555555">Processos como Dicionário Complementar</text>
  <text x="400" y="300" text-anchor="middle" font-size="13" fill="#C0392B" font-weight="bold">Obsolescência Assumida para Métricas Preditivas (EVM)</text>

  <!-- Seta Descendente 2 -->
  <line x1="400" y1="320" x2="400" y2="350" stroke="#1F3A5F" stroke-width="2" marker-end="url(#ar)"/>
  <text x="415" y="340" font-size="11" fill="#555555">Vocabulário Estrutural</text>

  <!-- Camada 3: Kanban/Ágil (Base) -->
  <rect x="150" y="360" width="500" height="100" rx="6" fill="#2E7D32" stroke="#2E7D32" stroke-width="2"/>
  <text x="400" y="395" text-anchor="middle" font-size="18" font-weight="bold" fill="#FFFFFF">Manifesto Ágil + Kanban (GitHub Projects)</text>
  <text x="400" y="420" text-anchor="middle" font-size="14" fill="#E8F5E9">Fluxo Contínuo, WIP Limits e Métricas de Fluxo</text>
  <text x="400" y="440" text-anchor="middle" font-size="13" fill="#E8F5E9">(Método de Execução: Como o trabalho flui)</text>

  <!-- Setas Laterais de Realimentação -->
  <path d="M 650 410 Q 720 410 720 270 Q 720 130 650 130" fill="none" stroke="#2E7D32" stroke-width="2" stroke-dasharray="5,5" marker-end="url(#ar-green)"/>
  <text x="735" y="275" font-size="12" font-weight="bold" fill="#2E7D32" text-anchor="start">Lições Aprendidas</text>
  <text x="735" y="290" font-size="12" font-weight="bold" fill="#2E7D32" text-anchor="start">e Realimentação</text>
</svg>
```

---

### 2. Fluxo de Controle Integrado de Mudanças

**Arquivo:** `fig-4-controle-mudancas.svg`

```xml
<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 800 650" font-family="Arial, Helvetica, sans-serif">
  <defs>
    <marker id="ar-flow" markerWidth="10" markerHeight="10" refX="9" refY="3" orient="auto" markerUnits="strokeWidth">
      <path d="M0,0 L9,3 L0,6 Z" fill="#1F3A5F"/>
    </marker>
    <marker id="ar-reject" markerWidth="10" markerHeight="10" refX="9" refY="3" orient="auto" markerUnits="strokeWidth">
      <path d="M0,0 L9,3 L0,6 Z" fill="#C0392B"/>
    </marker>
    <marker id="ar-approve" markerWidth="10" markerHeight="10" refX="9" refY="3" orient="auto" markerUnits="strokeWidth">
      <path d="M0,0 L9,3 L0,6 Z" fill="#2E7D32"/>
    </marker>
  </defs>
  <rect x="0" y="0" width="800" height="650" fill="#FFFFFF"/>
  
  <!-- Título Ilustrativo Interno -->
  <text x="400" y="40" text-anchor="middle" font-size="20" font-weight="bold" fill="#111111">Fluxo de Controle Integrado de Mudanças</text>

  <!-- Etapa 1 -->
  <rect x="200" y="70" width="400" height="60" rx="4" fill="#F8F9FA" stroke="#1F3A5F" stroke-width="2"/>
  <text x="400" y="95" text-anchor="middle" font-size="14" font-weight="bold" fill="#111111">1. Abertura de Issue com label</text>
  <text x="400" y="115" text-anchor="middle" font-size="13" fill="#333333">change-request (Qualquer membro | Prazo: Imediato)</text>

  <!-- Seta 1->2 -->
  <line x1="400" y1="130" x2="400" y2="160" stroke="#1F3A5F" stroke-width="2" marker-end="url(#ar-flow)"/>
  <text x="415" y="150" font-size="11" fill="#555555">Imediato</text>

  <!-- Etapa 2 -->
  <rect x="200" y="160" width="400" height="60" rx="4" fill="#F8F9FA" stroke="#1F3A5F" stroke-width="2"/>
  <text x="400" y="185" text-anchor="middle" font-size="14" font-weight="bold" fill="#111111">2. Análise de impacto (escopo, prazo, qualidade)</text>
  <text x="400" y="205" text-anchor="middle" font-size="13" fill="#333333">Responsável: GP (CCB membro único) | Prazo: ≤ 48h</text>

  <!-- Seta 2->3 -->
  <line x1="400" y1="220" x2="400" y2="250" stroke="#1F3A5F" stroke-width="2" marker-end="url(#ar-flow)"/>
  <text x="415" y="240" font-size="11" fill="#555555">≤ 48h</text>

  <!-- Etapa 3: Decisão -->
  <polygon points="400,260 540,300 400,340 260,300" fill="#F4F6F8" stroke="#1F3A5F" stroke-width="2"/>
  <text x="400" y="295" text-anchor="middle" font-size="14" font-weight="bold" fill="#111111">3. Aprovação</text>
  <text x="400" y="315" text-anchor="middle" font-size="12" fill="#333333">pelo CCB (GP)</text>
  <text x="400" y="330" text-anchor="middle" font-size="11" fill="#555555">Prazo: ≤ 24h</text>

  <!-- Ramo de Rejeição -->
  <line x1="540" y1="300" x2="620" y2="300" stroke="#C0392B" stroke-width="2" marker-end="url(#ar-reject)"/>
  <rect x="620" y="270" width="150" height="60" rx="4" fill="#FDECEA" stroke="#C0392B" stroke-width="2"/>
  <text x="695" y="295" text-anchor="middle" font-size="13" font-weight="bold" fill="#C0392B">Rejeitada</text>
  <text x="695" y="315" text-anchor="middle" font-size="11" fill="#333333">Encerramento com</text>
  <text x="695" y="330" text-anchor="middle" font-size="11" fill="#333333">registro na Issue</text>

  <!-- Ramo de Aprovação (Seta para baixo) -->
  <line x1="400" y1="340" x2="400" y2="380" stroke="#2E7D32" stroke-width="2" marker-end="url(#ar-approve)"/>
  <text x="415" y="365" font-size="11" fill="#2E7D32" font-weight="bold">Aprovada</text>

  <!-- Etapa 4 -->
  <rect x="200" y="380" width="400" height="70" rx="4" fill="#F8F9FA" stroke="#1F3A5F" stroke-width="2"/>
  <text x="400" y="410" text-anchor="middle" font-size="14" font-weight="bold" fill="#111111">4. Execução da Mudança</text>
  <text x="400" y="435" text-anchor="middle" font-size="13" fill="#333333">Responsável: Equipe | Prazo: ≤ 24h após aprovação</text>

  <!-- Bifurcação da Etapa 4 -->
  <!-- Ramo Esquerdo: Simples -->
  <path d="M 200 415 L 120 415 L 120 480" fill="none" stroke="#1F3A5F" stroke-width="2" marker-end="url(#ar-flow)"/>
  <rect x="20" y="480" width="200" height="60" rx="4" fill="#E8F5E9" stroke="#2E7D32" stroke-width="2"/>
  <text x="120" y="505" text-anchor="middle" font-size="13" font-weight="bold" fill="#111111">Mudança Simples</text>
  <text x="120" y="525" text-anchor="middle" font-size="12" fill="#333333">Atualização de backlog</text>
  <text x="120" y="540" text-anchor="middle" font-size="12" fill="#333333">+ commit na Issue</text>

  <!-- Ramo Direito: Complexa -->
  <path d="M 600 415 L 680 415 L 680 480" fill="none" stroke="#1F3A5F" stroke-width="2" marker-end="url(#ar-flow)"/>
  <rect x="580" y="480" width="200" height="60" rx="4" fill="#FFF3E0" stroke="#E65100" stroke-width="2"/>
  <text x="680" y="505" text-anchor="middle" font-size="13" font-weight="bold" fill="#111111">Mudança de Marco / Escopo MVP</text>
  <text x="680" y="525" text-anchor="middle" font-size="12" fill="#333333">Registro formal via ADR +</text>
  <text x="680" y="540" text-anchor="middle" font-size="12" fill="#333333">Comunicação no marco subsequente</text>
</svg>
```

---

### Matriz Informal de Rastreabilidade de Diagramas (Atualizada)

| ID                   | Arquivo                          | Descrição                                         | Camada / Contexto                                   |
| -------------------- | -------------------------------- | --------------------------------------------------- | --------------------------------------------------- |
| FIG-EAP-01           | `fig-eap-nivel-0-macro.svg`    | Visão Macro (N0 e Macro-Fases)                     | Nível 0 e 1 (Agrupamento)                          |
| FIG-EAP-02           | `fig-eap-mf1-fundacao.svg`     | Detalhamento MF1 (Fundação)                       | Nível 1 e 2 (N1, N2, N3, N4, N8, N9)               |
| FIG-EAP-03           | `fig-eap-mf2-construcao.svg`   | Detalhamento MF2 (Construção)                     | Nível 1 e 2 (N5, N6, N7, N10)                      |
| FIG-EAP-04           | `fig-eap-mf3-consolidacao.svg` | Detalhamento MF3 (Consolidação)                   | Nível 1 e 2 (N11, N12)                             |
| **FIG-GOV-01** | `fig-1-governanca-hibrida.svg` | **Modelo de Governança Híbrida Trifásico** | **Integração §1.2 (Blindagem Acadêmica)** |
| **FIG-MUD-01** | `fig-4-controle-mudancas.svg`  | **Fluxo de Controle Integrado de Mudanças**  | **Integração §1.7.2 (Auditoria do CCB)**   |

---

### 📝 Nota Adjacente (Registro de Governança)

**Assunto:** Validação da Segunda Rodada de Diagramas (Governança e Mudanças)
**Data:** 21/09/2026
**Contexto:** Atendendo à diretriz de zero trade-offs de escopo e custo marginal, os diagramas `FIG-GOV-01` e `FIG-MUD-01` foram projetados para maximizar a clareza acadêmica. A omissão de legendas internas ("Figura X", "Elaborado por") garante que o SVG seja um ativo gráfico puro, pronto para ser inserido nos documentos `.docx`/`.md` com a formatação ABNT externa controlada pelo autor.
**Próximo Passo:** Aguardo a validação visual desta rodada para prosseguirmos com a geração dos diagramas restantes do ciclo (ex: CFD Saudável vs. Gargalo, Sequenciamento Macro/Caminho Crítico Empírico), mantendo a mesma disciplina estética e de rastreabilidade.

Como GP Sênior e PMO, prossigo com a **Terceira Rodada Candidata** de diagramas, mantendo a disciplina estética convergente e a rastreabilidade na matriz informal.

---

### 1. CFD: Padrão Saudável vs. Padrão com Gargalo
**Arquivo:** `fig-3-cfd-saudavel-vs-gargalo.svg`
```xml
<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 1400 700" font-family="Arial, Helvetica, sans-serif">
  <rect x="0" y="0" width="1400" height="700" fill="#FFFFFF"/>
  <text x="700" y="40" text-anchor="middle" font-size="22" font-weight="bold" fill="#111111">Cumulative Flow Diagram (CFD) — Padrão Saudável vs. Gargalo</text>
  
  <!-- Painel A: CFD Saudável -->
  <g transform="translate(50, 80)">
    <text x="300" y="0" text-anchor="middle" font-size="18" font-weight="bold" fill="#1F3A5F">(a) CFD Saudável — Fluxo Estável</text>
    
    <!-- Eixos -->
    <line x1="50" y1="40" x2="50" y2="480" stroke="#333333" stroke-width="2"/>
    <line x1="50" y1="480" x2="600" y2="480" stroke="#333333" stroke-width="2"/>
    <text x="20" y="260" text-anchor="middle" font-size="12" fill="#555555" transform="rotate(-90, 20, 260)">Cards Acumulados</text>
    <text x="325" y="510" text-anchor="middle" font-size="12" fill="#555555">Tempo (semanas)</text>
    
    <!-- Bandas paralelas e estáveis -->
    <!-- Done (verde) -->
    <path d="M 50 480 L 600 480 L 600 420 L 50 420 Z" fill="#2E7D32" opacity="0.8"/>
    <text x="580" y="455" text-anchor="end" font-size="11" font-weight="bold" fill="#FFFFFF">Done</text>
    
    <!-- Code Review (azul claro) -->
    <path d="M 50 420 L 600 420 L 600 370 L 50 370 Z" fill="#4A90E2" opacity="0.8"/>
    <text x="580" y="400" text-anchor="end" font-size="11" font-weight="bold" fill="#FFFFFF">Code Review</text>
    
    <!-- In Progress (azul médio) -->
    <path d="M 50 370 L 600 370 L 600 310 L 50 310 Z" fill="#1F3A5F" opacity="0.8"/>
    <text x="580" y="345" text-anchor="end" font-size="11" font-weight="bold" fill="#FFFFFF">In Progress</text>
    
    <!-- Ready (laranja) -->
    <path d="M 50 310 L 600 310 L 600 260 L 50 260 Z" fill="#E67E22" opacity="0.8"/>
    <text x="580" y="290" text-anchor="end" font-size="11" font-weight="bold" fill="#FFFFFF">Ready</text>
    
    <!-- Backlog (cinza) -->
    <path d="M 50 260 L 600 260 L 600 200 L 50 200 Z" fill="#7F8C8D" opacity="0.8"/>
    <text x="580" y="235" text-anchor="end" font-size="11" font-weight="bold" fill="#FFFFFF">Backlog</text>
    
    <!-- Anotação -->
    <text x="325" y="540" text-anchor="middle" font-size="12" fill="#2E7D32" font-weight="bold">Bandas paralelas e de largura constante</text>
    <text x="325" y="555" text-anchor="middle" font-size="11" fill="#555555">Fluxo estável — WIP sob controle</text>
  </g>
  
  <!-- Painel B: CFD com Gargalo -->
  <g transform="translate(750, 80)">
    <text x="300" y="0" text-anchor="middle" font-size="18" font-weight="bold" fill="#C0392B">(b) CFD com Gargalo — Code Review</text>
    
    <!-- Eixos -->
    <line x1="50" y1="40" x2="50" y2="480" stroke="#333333" stroke-width="2"/>
    <line x1="50" y1="480" x2="600" y2="480" stroke="#333333" stroke-width="2"/>
    <text x="20" y="260" text-anchor="middle" font-size="12" fill="#555555" transform="rotate(-90, 20, 260)">Cards Acumulados</text>
    <text x="325" y="510" text-anchor="middle" font-size="12" fill="#555555">Tempo (semanas)</text>
    
    <!-- Bandas com gargalo em Code Review -->
    <!-- Done (verde) - estreita -->
    <path d="M 50 480 L 600 480 L 600 450 L 50 450 Z" fill="#2E7D32" opacity="0.8"/>
    <text x="580" y="470" text-anchor="end" font-size="11" font-weight="bold" fill="#FFFFFF">Done</text>
    
    <!-- Code Review (azul claro) - ALARGANDO (gargalo) -->
    <path d="M 50 450 L 200 450 L 350 420 L 500 380 L 600 350 L 600 250 L 500 280 L 350 320 L 200 350 L 50 350 Z" fill="#4A90E2" opacity="0.8"/>
    <text x="580" y="310" text-anchor="end" font-size="11" font-weight="bold" fill="#FFFFFF">Code Review</text>
    
    <!-- Seta indicando alargamento -->
    <path d="M 400 340 L 450 320" stroke="#C0392B" stroke-width="2" marker-end="url(#arrow-red)"/>
    <text x="460" y="315" font-size="10" fill="#C0392B" font-weight="bold">Gargalo</text>
    
    <!-- In Progress (azul médio) - estável -->
    <path d="M 50 350 L 200 350 L 350 320 L 500 280 L 600 250 L 600 200 L 500 230 L 350 270 L 200 300 L 50 300 Z" fill="#1F3A5F" opacity="0.8"/>
    <text x="580" y="230" text-anchor="end" font-size="11" font-weight="bold" fill="#FFFFFF">In Progress</text>
    
    <!-- Ready (laranja) - estável -->
    <path d="M 50 300 L 200 300 L 350 270 L 500 230 L 600 200 L 600 160 L 500 190 L 350 230 L 200 260 L 50 260 Z" fill="#E67E22" opacity="0.8"/>
    <text x="580" y="190" text-anchor="end" font-size="11" font-weight="bold" fill="#FFFFFF">Ready</text>
    
    <!-- Backlog (cinza) - estável -->
    <path d="M 50 260 L 200 260 L 350 230 L 500 190 L 600 160 L 600 120 L 500 150 L 350 190 L 200 220 L 50 220 Z" fill="#7F8C8D" opacity="0.8"/>
    <text x="580" y="150" text-anchor="end" font-size="11" font-weight="bold" fill="#FFFFFF">Backlog</text>
    
    <!-- Anotação -->
    <text x="325" y="540" text-anchor="middle" font-size="12" fill="#C0392B" font-weight="bold">Banda Code Review alargando progressivamente</text>
    <text x="325" y="555" text-anchor="middle" font-size="11" fill="#555555">Gargalo detectado — ação corretiva necessária</text>
  </g>
  
  <!-- Regra de Ação Corretiva (comum aos dois painéis) -->
  <rect x="200" y="620" width="1000" height="60" rx="6" fill="#FFF3E0" stroke="#E65100" stroke-width="2"/>
  <text x="700" y="645" text-anchor="middle" font-size="14" font-weight="bold" fill="#E65100">Regra de Ação Corretiva (Integração §1.6.1)</text>
  <text x="700" y="665" text-anchor="middle" font-size="12" fill="#333333">Se uma banda ultrapassar 2× a largura média das demais por 2 semanas consecutivas → Retrospectiva extraordinária (ADR-002)</text>
  
  <!-- Definição de marker -->
  <defs>
    <marker id="arrow-red" markerWidth="10" markerHeight="10" refX="9" refY="3" orient="auto" markerUnits="strokeWidth">
      <path d="M0,0 L9,3 L0,6 Z" fill="#C0392B"/>
    </marker>
  </defs>
</svg>
```

---

### 2. Sequenciamento Macro e Caminho Crítico Empírico
**Arquivo:** `fig-1-sequenciamento-macro-caminho-critico.svg`
```xml
<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 1400 650" font-family="Arial, Helvetica, sans-serif">
  <defs>
    <marker id="ar-flow" markerWidth="10" markerHeight="10" refX="9" refY="3" orient="auto" markerUnits="strokeWidth">
      <path d="M0,0 L9,3 L0,6 Z" fill="#1F3A5F"/>
    </marker>
    <marker id="ar-green" markerWidth="10" markerHeight="10" refX="9" refY="3" orient="auto" markerUnits="strokeWidth">
      <path d="M0,0 L9,3 L0,6 Z" fill="#2E7D32"/>
    </marker>
  </defs>
  <rect x="0" y="0" width="1400" height="650" fill="#FFFFFF"/>
  <text x="700" y="40" text-anchor="middle" font-size="22" font-weight="bold" fill="#111111">Sequenciamento Macro e Caminho Crítico Empírico</text>
  
  <!-- Faixa Superior: Macro-Fases e Gates -->
  <g transform="translate(100, 80)">
    <text x="600" y="0" text-anchor="middle" font-size="16" font-weight="bold" fill="#1F3A5F">Camada Macro — Macro-Fases e Gates de Controle</text>
    
    <!-- MF1 -->
    <rect x="50" y="30" width="250" height="80" rx="6" fill="#1F3A5F" stroke="#1F3A5F" stroke-width="2"/>
    <text x="175" y="55" text-anchor="middle" font-size="15" font-weight="bold" fill="#FFFFFF">MF1: Fundação</text>
    <text x="175" y="75" text-anchor="middle" font-size="12" fill="#E0E7EF">01/09 – 30/09/2026</text>
    <text x="175" y="95" text-anchor="middle" font-size="11" fill="#E0E7EF">5 planos (Áreas 1–5)</text>
    
    <!-- Gate M2 -->
    <polygon points="320,70 360,50 360,90" fill="#E67E22" stroke="#E67E22" stroke-width="2"/>
    <text x="340" y="115" text-anchor="middle" font-size="11" font-weight="bold" fill="#E67E22">M2</text>
    <text x="340" y="130" text-anchor="middle" font-size="10" fill="#555555">30/09</text>
    
    <!-- Calibração (auxiliar) -->
    <rect x="380" y="50" width="120" height="40" rx="4" fill="#FFF3E0" stroke="#E67E22" stroke-width="2" stroke-dasharray="4,2"/>
    <text x="440" y="70" text-anchor="middle" font-size="11" font-weight="bold" fill="#E65100">Calibração</text>
    <text x="440" y="85" text-anchor="middle" font-size="10" fill="#555555">03/10 (aux)</text>
    
    <!-- MF2 -->
    <rect x="520" y="30" width="250" height="80" rx="6" fill="#2E7D32" stroke="#2E7D32" stroke-width="2"/>
    <text x="645" y="55" text-anchor="middle" font-size="15" font-weight="bold" fill="#FFFFFF">MF2: Construção</text>
    <text x="645" y="75" text-anchor="middle" font-size="12" fill="#E8F5E9">01/10 – 15/11/2026</text>
    <text x="645" y="95" text-anchor="middle" font-size="11" fill="#E8F5E9">MVP funcional + coverage ≥80%</text>
    
    <!-- Gate M3 -->
    <polygon points="790,70 830,50 830,90" fill="#E67E22" stroke="#E67E22" stroke-width="2"/>
    <text x="810" y="115" text-anchor="middle" font-size="11" font-weight="bold" fill="#E67E22">M3</text>
    <text x="810" y="130" text-anchor="middle" font-size="10" fill="#555555">15/11</text>
    
    <!-- MF3 -->
    <rect x="850" y="30" width="250" height="80" rx="6" fill="#6A1B9A" stroke="#6A1B9A" stroke-width="2"/>
    <text x="975" y="55" text-anchor="middle" font-size="15" font-weight="bold" fill="#FFFFFF">MF3: Consolidação</text>
    <text x="975" y="75" text-anchor="middle" font-size="12" fill="#F3E5F5">16/11 – 15/12/2026</text>
    <text x="975" y="95" text-anchor="middle" font-size="11" fill="#F3E5F5">Documentação + Aceite M4</text>
    
    <!-- Gate M4 -->
    <polygon points="1120,70 1160,50 1160,90" fill="#E67E22" stroke="#E67E22" stroke-width="2"/>
    <text x="1140" y="115" text-anchor="middle" font-size="11" font-weight="bold" fill="#E67E22">M4</text>
    <text x="1140" y="130" text-anchor="middle" font-size="10" fill="#555555">15/12</text>
    
    <!-- Setas de fluxo -->
    <line x1="300" y1="70" x2="320" y2="70" stroke="#1F3A5F" stroke-width="2" marker-end="url(#ar-flow)"/>
    <line x1="360" y1="70" x2="380" y2="70" stroke="#1F3A5F" stroke-width="2" marker-end="url(#ar-flow)"/>
    <line x1="500" y1="70" x2="520" y2="70" stroke="#1F3A5F" stroke-width="2" marker-end="url(#ar-flow)"/>
    <line x1="770" y1="70" x2="790" y2="70" stroke="#1F3A5F" stroke-width="2" marker-end="url(#ar-flow)"/>
    <line x1="830" y1="70" x2="850" y2="70" stroke="#1F3A5F" stroke-width="2" marker-end="url(#ar-flow)"/>
    <line x1="1100" y1="70" x2="1120" y2="70" stroke="#1F3A5F" stroke-width="2" marker-end="url(#ar-flow)"/>
  </g>
  
  <!-- Faixa Inferior: Caminho Crítico Empírico -->
  <g transform="translate(100, 280)">
    <text x="600" y="0" text-anchor="middle" font-size="16" font-weight="bold" fill="#2E7D32">Camada Operacional — Detectores do Caminho Crítico Empírico</text>
    
    <!-- Detector 1: Cards P0 -->
    <rect x="50" y="40" width="200" height="100" rx="6" fill="#FDECEA" stroke="#C0392B" stroke-width="2"/>
    <text x="150" y="65" text-anchor="middle" font-size="13" font-weight="bold" fill="#C0392B">Cards P0</text>
    <text x="150" y="85" text-anchor="middle" font-size="11" fill="#333333">Prioridade temporal</text>
    <text x="150" y="100" text-anchor="middle" font-size="11" fill="#333333">crítica do marco</text>
    <text x="150" y="120" text-anchor="middle" font-size="10" fill="#555555">(OKB §9.4)</text>
    
    <!-- Detector 2: Label blocked -->
    <rect x="280" y="40" width="200" height="100" rx="6" fill="#FDECEA" stroke="#C0392B" stroke-width="2"/>
    <text x="380" y="65" text-anchor="middle" font-size="13" font-weight="bold" fill="#C0392B">Label blocked</text>
    <text x="380" y="85" text-anchor="middle" font-size="11" fill="#333333">Dependência registrada</text>
    <text x="380" y="100" text-anchor="middle" font-size="11" fill="#333333">no corpo da Issue</text>
    <text x="380" y="120" text-anchor="middle" font-size="10" fill="#555555">(OKB §9.1)</text>
    
    <!-- Detector 3: Bandas do CFD -->
    <rect x="510" y="40" width="200" height="100" rx="6" fill="#FFF3E0" stroke="#E65100" stroke-width="2"/>
    <text x="610" y="65" text-anchor="middle" font-size="13" font-weight="bold" fill="#E65100">Bandas do CFD</text>
    <text x="610" y="85" text-anchor="middle" font-size="11" fill="#333333">Alargamento &gt; 2×</text>
    <text x="610" y="100" text-anchor="middle" font-size="11" fill="#333333">largura média</text>
    <text x="610" y="120" text-anchor="middle" font-size="10" fill="#555555">(Integração §1.6.1)</text>
    
    <!-- Detector 4: Desvio de Cycle Time -->
    <rect x="740" y="40" width="200" height="100" rx="6" fill="#FFF3E0" stroke="#E65100" stroke-width="2"/>
    <text x="840" y="65" text-anchor="middle" font-size="13" font-weight="bold" fill="#E65100">Desvio Cycle Time</text>
    <text x="840" y="85" text-anchor="middle" font-size="11" fill="#333333">Meta ≤ 3 dias</text>
    <text x="840" y="100" text-anchor="middle" font-size="11" fill="#333333">violada persistentemente</text>
    <text x="840" y="120" text-anchor="middle" font-size="10" fill="#555555">(ADR-003)</text>
    
    <!-- Setas convergindo para Refinement -->
    <line x1="150" y1="140" x2="500" y2="200" stroke="#2E7D32" stroke-width="2" marker-end="url(#ar-green)"/>
    <line x1="380" y1="140" x2="500" y2="200" stroke="#2E7D32" stroke-width="2" marker-end="url(#ar-green)"/>
    <line x1="610" y1="140" x2="500" y2="200" stroke="#2E7D32" stroke-width="2" marker-end="url(#ar-green)"/>
    <line x1="840" y1="140" x2="500" y2="200" stroke="#2E7D32" stroke-width="2" marker-end="url(#ar-green)"/>
    
    <!-- Refinement / Replanejamento -->
    <rect x="400" y="200" width="300" height="80" rx="6" fill="#2E7D32" stroke="#2E7D32" stroke-width="2"/>
    <text x="550" y="230" text-anchor="middle" font-size="14" font-weight="bold" fill="#FFFFFF">Refinement Semanal</text>
    <text x="550" y="250" text-anchor="middle" font-size="12" fill="#E8F5E9">+ Retrospectiva Quinzenal</text>
    <text x="550" y="268" text-anchor="middle" font-size="11" fill="#E8F5E9">Decisão de replanejamento</text>
    
    <!-- Seta para camada macro -->
    <path d="M 550 280 L 550 320 L 600 320" fill="none" stroke="#1F3A5F" stroke-width="2" marker-end="url(#ar-flow)"/>
    <text x="580" y="310" font-size="11" fill="#555555">Ajuste de prioridades</text>
  </g>
  
  <!-- Anotação inferior -->
  <rect x="200" y="600" width="1000" height="40" rx="4" fill="#F4F6F8" stroke="#1F3A5F" stroke-width="1"/>
  <text x="700" y="625" text-anchor="middle" font-size="12" fill="#333333">Caminho crítico identificado empiricamente — sem rede CPM preditiva (ADR-003, OKB §8.1)</text>
</svg>
```

---

### Matriz Informal de Rastreabilidade de Diagramas (Atualizada)

| ID | Arquivo | Descrição | Camada / Contexto |
|---|---|---|---|
| FIG-EAP-01 | `fig-eap-nivel-0-macro.svg` | Visão Macro (N0 e Macro-Fases) | Nível 0 e 1 (Agrupamento) |
| FIG-EAP-02 | `fig-eap-mf1-fundacao.svg` | Detalhamento MF1 (Fundação) | Nível 1 e 2 (N1, N2, N3, N4, N8, N9) |
| FIG-EAP-03 | `fig-eap-mf2-construcao.svg` | Detalhamento MF2 (Construção) | Nível 1 e 2 (N5, N6, N7, N10) |
| FIG-EAP-04 | `fig-eap-mf3-consolidacao.svg` | Detalhamento MF3 (Consolidação) | Nível 1 e 2 (N11, N12) |
| FIG-GOV-01 | `fig-1-governanca-hibrida.svg` | Modelo de Governança Híbrida Trifásico | Integração §1.2 |
| FIG-MUD-01 | `fig-4-controle-mudancas.svg` | Fluxo de Controle Integrado de Mudanças | Integração §1.7.2 |
| **FIG-CFD-01** | `fig-3-cfd-saudavel-vs-gargalo.svg` | **CFD: Padrão Saudável vs. Gargalo** | **Integração §1.6.1 (Blindagem Acadêmica)** |
| **FIG-SEQ-01** | `fig-1-sequenciamento-macro-caminho-critico.svg` | **Sequenciamento Macro + Caminho Crítico Empírico** | **Cronograma §3.4 (Substituto CPM)** |

---

### 📝 Nota Adjacente (Registro de Governança)
**Assunto:** Terceira Rodada de Diagramas — CFD e Sequenciamento Macro
**Data:** 21/09/2026
**Contexto:** Os diagramas `FIG-CFD-01` e `FIG-SEQ-01` constituem a **blindagem acadêmica formal** para a ausência de Gantt/EVM e rede CPM preditiva. O CFD dual (saudável vs. gargalo) demonstra visualmente ao Prof. Dr. Nivaldo Carleto como o gargalo é detectado e tratado via métricas de fluxo Kanban (Domínio de Medição PMBOK 7ª). O diagrama de sequenciamento macro substitui visualmente a rede CPM rejeitada pela ADR-003, mostrando os quatro detectores empíricos do caminho crítico (cards P0, label `blocked`, bandas do CFD, desvio de Cycle Time) alimentando a decisão de replanejamento no Refinement semanal.
**Próximo Passo:** Aguardo validação visual desta rodada para prosseguirmos com os diagramas restantes do ciclo (ex: Roadmap Macro do Cronograma, Fluxo Kanban com gates e WIP limits), mantendo a mesma disciplina estética e de rastreabilidade.

Como GP Sênior e PMO, acolho a crítica com total transparência técnica. O *overlap* grosseiro no diagrama anterior ocorreu devido a uma falha de ancoragem: múltiplas setas convergiam para um único ponto cartesiano (`500, 200`), empilhando as pontas das flechas, somado a um *viewBox* subdimensionado que forçava a compressão dos elementos. 

Para sanar isso de forma definitiva e garantir **legibilidade otimizada para humanos** (regra ABNT e de UX), reestruturei o diagrama com as seguintes correções:
1. **Canvas Expandido**: `viewBox` ajustado para `1200 x 700`, garantindo margens de respiro (padding) adequadas.
2. **Ancoragem Distribuída**: As setas dos 4 detectores agora apontam para pontos distintos e equidistantes na borda superior da caixa de "Refinement", eliminando totalmente a sobreposição de elementos gráficos.
3. **Tipografia Blindada**: Substituição de textos soltos por blocos `<tspan>` com *dy* controlado, garantindo que nenhuma linha de texto colida com bordas ou outras linhas, independentemente do renderizador.
4. **Fluxo de Feedback Orgânico**: Adição de uma seta curva tracejada que conecta a camada operacional de volta à camada macro, materializando visualmente o conceito de "replanejamento sem violar gates".

Abaixo segue o artefato corrigido e, separadamente, a nota técnica formatada conforme as normas ABNT (NBR 14724 / NBR 12225) para inserção direta no documento acadêmico.

---

### 1. Artefato SVG Otimizado (Sem Overlap)
**Arquivo:** `fig-1-sequenciamento-macro-caminho-critico.svg`
```xml
<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 1200 700" font-family="Arial, Helvetica, sans-serif">
  <defs>
    <marker id="ar-flow" markerWidth="10" markerHeight="10" refX="9" refY="3" orient="auto" markerUnits="strokeWidth">
      <path d="M0,0 L9,3 L0,6 Z" fill="#1F3A5F"/>
    </marker>
    <marker id="ar-green" markerWidth="10" markerHeight="10" refX="9" refY="3" orient="auto" markerUnits="strokeWidth">
      <path d="M0,0 L9,3 L0,6 Z" fill="#2E7D32"/>
    </marker>
    <marker id="ar-feedback" markerWidth="10" markerHeight="10" refX="9" refY="3" orient="auto" markerUnits="strokeWidth">
      <path d="M0,0 L9,3 L0,6 Z" fill="#E67E22"/>
    </marker>
  </defs>
  
  <!-- Fundo -->
  <rect x="0" y="0" width="1200" height="700" fill="#FFFFFF"/>
  
  <!-- Título -->
  <text x="600" y="40" text-anchor="middle" font-size="22" font-weight="bold" fill="#111111">Sequenciamento Macro e Caminho Crítico Empírico</text>
  
  <!-- ================= CAMADA SUPERIOR: MACRO-FASES E GATES ================= -->
  <text x="600" y="75" text-anchor="middle" font-size="16" font-weight="bold" fill="#1F3A5F">Camada Macro — Macro-Fases e Gates de Controle</text>
  
  <!-- MF1 -->
  <rect x="60" y="95" width="200" height="70" rx="6" fill="#1F3A5F" stroke="#1F3A5F" stroke-width="2"/>
  <text x="160" y="120" text-anchor="middle" font-size="14" font-weight="bold" fill="#FFFFFF">
    <tspan x="160" dy="0">MF1: Fundação</tspan>
    <tspan x="160" dy="20" font-size="11" font-weight="normal" fill="#E0E7EF">01/09 – 30/09/2026</tspan>
    <tspan x="160" dy="15" font-size="11" font-weight="normal" fill="#E0E7EF">5 planos (Áreas 1–5)</tspan>
  </text>
  
  <!-- Seta MF1 -> M2 -->
  <line x1="260" y1="130" x2="280" y2="130" stroke="#1F3A5F" stroke-width="2" marker-end="url(#ar-flow)"/>
  
  <!-- Gate M2 -->
  <polygon points="300,110 320,130 300,150 280,130" fill="#E67E22" stroke="#E67E22" stroke-width="2"/>
  <text x="300" y="170" text-anchor="middle" font-size="11" font-weight="bold" fill="#E67E22">M2</text>
  <text x="300" y="185" text-anchor="middle" font-size="10" fill="#555555">30/09</text>
  
  <!-- Seta M2 -> Calibração -->
  <line x1="320" y1="130" x2="340" y2="130" stroke="#1F3A5F" stroke-width="2" marker-end="url(#ar-flow)"/>
  
  <!-- Calibração -->
  <rect x="340" y="105" width="140" height="50" rx="6" fill="#FFF3E0" stroke="#E67E22" stroke-width="2" stroke-dasharray="4,2"/>
  <text x="410" y="125" text-anchor="middle" font-size="12" font-weight="bold" fill="#E65100">
    <tspan x="410" dy="0">Calibração</tspan>
    <tspan x="410" dy="18" font-size="11" font-weight="normal" fill="#555555">03/10 (auxiliar)</tspan>
  </text>
  
  <!-- Seta Calibração -> MF2 -->
  <line x1="480" y1="130" x2="500" y2="130" stroke="#1F3A5F" stroke-width="2" marker-end="url(#ar-flow)"/>
  
  <!-- MF2 -->
  <rect x="500" y="95" width="200" height="70" rx="6" fill="#2E7D32" stroke="#2E7D32" stroke-width="2"/>
  <text x="600" y="120" text-anchor="middle" font-size="14" font-weight="bold" fill="#FFFFFF">
    <tspan x="600" dy="0">MF2: Construção</tspan>
    <tspan x="600" dy="20" font-size="11" font-weight="normal" fill="#E8F5E9">01/10 – 15/11/2026</tspan>
    <tspan x="600" dy="15" font-size="11" font-weight="normal" fill="#E8F5E9">MVP funcional + coverage ≥80%</tspan>
  </text>
  
  <!-- Seta MF2 -> M3 -->
  <line x1="700" y1="130" x2="720" y2="130" stroke="#1F3A5F" stroke-width="2" marker-end="url(#ar-flow)"/>
  
  <!-- Gate M3 -->
  <polygon points="740,110 760,130 740,150 720,130" fill="#E67E22" stroke="#E67E22" stroke-width="2"/>
  <text x="740" y="170" text-anchor="middle" font-size="11" font-weight="bold" fill="#E67E22">M3</text>
  <text x="740" y="185" text-anchor="middle" font-size="10" fill="#555555">15/11</text>
  
  <!-- Seta M3 -> MF3 -->
  <line x1="760" y1="130" x2="780" y2="130" stroke="#1F3A5F" stroke-width="2" marker-end="url(#ar-flow)"/>
  
  <!-- MF3 -->
  <rect x="780" y="95" width="200" height="70" rx="6" fill="#6A1B9A" stroke="#6A1B9A" stroke-width="2"/>
  <text x="880" y="120" text-anchor="middle" font-size="14" font-weight="bold" fill="#FFFFFF">
    <tspan x="880" dy="0">MF3: Consolidação</tspan>
    <tspan x="880" dy="20" font-size="11" font-weight="normal" fill="#F3E5F5">16/11 – 15/12/2026</tspan>
    <tspan x="880" dy="15" font-size="11" font-weight="normal" fill="#F3E5F5">Documentação + Aceite M4</tspan>
  </text>
  
  <!-- Seta MF3 -> M4 -->
  <line x1="980" y1="130" x2="1000" y2="130" stroke="#1F3A5F" stroke-width="2" marker-end="url(#ar-flow)"/>
  
  <!-- Gate M4 -->
  <polygon points="1020,110 1040,130 1020,150 1000,130" fill="#E67E22" stroke="#E67E22" stroke-width="2"/>
  <text x="1020" y="170" text-anchor="middle" font-size="11" font-weight="bold" fill="#E67E22">M4</text>
  <text x="1020" y="185" text-anchor="middle" font-size="10" fill="#555555">15/12</text>

  <!-- ================= CAMADA INFERIOR: CAMINHO CRÍTICO EMPÍRICO ================= -->
  <text x="600" y="240" text-anchor="middle" font-size="16" font-weight="bold" fill="#2E7D32">Camada Operacional — Detectores do Caminho Crítico Empírico</text>
  
  <!-- Detector 1: Cards P0 -->
  <rect x="80" y="270" width="220" height="90" rx="6" fill="#FDECEA" stroke="#C0392B" stroke-width="2"/>
  <text x="190" y="295" text-anchor="middle" font-size="13" font-weight="bold" fill="#C0392B">
    <tspan x="190" dy="0">Cards P0</tspan>
    <tspan x="190" dy="20" font-size="11" font-weight="normal" fill="#333333">Prioridade temporal</tspan>
    <tspan x="190" dy="15" font-size="11" font-weight="normal" fill="#333333">crítica do marco</tspan>
    <tspan x="190" dy="15" font-size="10" font-weight="normal" fill="#555555">(OKB §9.4)</tspan>
  </text>
  
  <!-- Detector 2: Label blocked -->
  <rect x="330" y="270" width="220" height="90" rx="6" fill="#FDECEA" stroke="#C0392B" stroke-width="2"/>
  <text x="440" y="295" text-anchor="middle" font-size="13" font-weight="bold" fill="#C0392B">
    <tspan x="440" dy="0">Label blocked</tspan>
    <tspan x="440" dy="20" font-size="11" font-weight="normal" fill="#333333">Dependência registrada</tspan>
    <tspan x="440" dy="15" font-size="11" font-weight="normal" fill="#333333">no corpo da Issue</tspan>
    <tspan x="440" dy="15" font-size="10" font-weight="normal" fill="#555555">(OKB §9.1)</tspan>
  </text>
  
  <!-- Detector 3: Bandas do CFD -->
  <rect x="580" y="270" width="220" height="90" rx="6" fill="#FFF3E0" stroke="#E65100" stroke-width="2"/>
  <text x="690" y="295" text-anchor="middle" font-size="13" font-weight="bold" fill="#E65100">
    <tspan x="690" dy="0">Bandas do CFD</tspan>
    <tspan x="690" dy="20" font-size="11" font-weight="normal" fill="#333333">Alargamento &gt; 2×</tspan>
    <tspan x="690" dy="15" font-size="11" font-weight="normal" fill="#333333">largura média</tspan>
    <tspan x="690" dy="15" font-size="10" font-weight="normal" fill="#555555">(Integração §1.6.1)</tspan>
  </text>
  
  <!-- Detector 4: Desvio de Cycle Time -->
  <rect x="830" y="270" width="220" height="90" rx="6" fill="#FFF3E0" stroke="#E65100" stroke-width="2"/>
  <text x="940" y="295" text-anchor="middle" font-size="13" font-weight="bold" fill="#E65100">
    <tspan x="940" dy="0">Desvio Cycle Time</tspan>
    <tspan x="940" dy="20" font-size="11" font-weight="normal" fill="#333333">Meta ≤ 3 dias</tspan>
    <tspan x="940" dy="15" font-size="11" font-weight="normal" fill="#333333">violada persistentemente</tspan>
    <tspan x="940" dy="15" font-size="10" font-weight="normal" fill="#555555">(ADR-003)</tspan>
  </text>
  
  <!-- Setas convergindo para Refinement (pontos distintos no topo da caixa) -->
  <line x1="190" y1="360" x2="380" y2="410" stroke="#2E7D32" stroke-width="2" marker-end="url(#ar-green)"/>
  <line x1="440" y1="360" x2="520" y2="410" stroke="#2E7D32" stroke-width="2" marker-end="url(#ar-green)"/>
  <line x1="690" y1="360" x2="620" y2="410" stroke="#2E7D32" stroke-width="2" marker-end="url(#ar-green)"/>
  <line x1="940" y1="360" x2="720" y2="410" stroke="#2E7D32" stroke-width="2" marker-end="url(#ar-green)"/>
  
  <!-- Refinement / Replanejamento -->
  <rect x="330" y="410" width="540" height="80" rx="6" fill="#2E7D32" stroke="#2E7D32" stroke-width="2"/>
  <text x="600" y="440" text-anchor="middle" font-size="15" font-weight="bold" fill="#FFFFFF">
    <tspan x="600" dy="0">Refinement Semanal + Retrospectiva Quinzenal</tspan>
    <tspan x="600" dy="22" font-size="12" font-weight="normal" fill="#E8F5E9">Decisão de replanejamento e ajuste de prioridades</tspan>
    <tspan x="600" dy="16" font-size="11" font-weight="normal" fill="#E8F5E9">(sem violar os gates de controle das Macro-Fases)</tspan>
  </text>
  
  <!-- Seta de Feedback Orgânico para a camada macro -->
  <path d="M 870 450 Q 1100 450 1100 130 L 1040 130" fill="none" stroke="#E67E22" stroke-width="2" stroke-dasharray="5,5" marker-end="url(#ar-feedback)"/>
  <text x="1110" y="290" font-size="11" font-weight="bold" fill="#E67E22" text-anchor="start">Feedback de</text>
  <text x="1110" y="305" font-size="11" font-weight="bold" fill="#E67E22" text-anchor="start">Replanejamento</text>
  
  <!-- Anotação inferior (Nota Técnica) -->
  <rect x="100" y="540" width="1000" height="60" rx="6" fill="#F4F6F8" stroke="#1F3A5F" stroke-width="1.5"/>
  <text x="600" y="565" text-anchor="middle" font-size="12" font-weight="bold" fill="#111111">Nota Técnica:</text>
  <text x="600" y="585" text-anchor="middle" font-size="12" fill="#333333">Caminho crítico identificado empiricamente — sem rede CPM preditiva. Substitui o Gantt/EVM por</text>
  <text x="600" y="600" text-anchor="middle" font-size="12" fill="#333333">métricas de fluxo Kanban, conforme ADR-003 e OKB §8.1.</text>
</svg>
```

---

### 2. Nota Técnica ABNT para Inserção Documental
Conforme sua diretriz de separar a renderização da orientação interpretativa, abaixo está o bloco de legenda formatado estritamente conforme as normas ABNT (NBR 14724 para trabalhos acadêmicos e NBR 12225 para legendas de ilustrações). Este bloco deve ser inserido no documento `.docx` ou `.md` imediatamente abaixo da imagem convertida em `.png`.

> **Figura 1** – Sequenciamento Macro e Caminho Crítico Empírico do Projeto COGME.  
> **Nota:** O diagrama ilustra a substituição da rede de precedências preditiva (CPM/Gantt) por um modelo de detecção empírica de gargalos, em estrita conformidade com a ADR-003 e o Domínio de Medição do PMBOK® 7ª edição. Os quatro detectores operacionais (Cards P0, label *blocked*, alargamento de bandas no CFD e desvio persistente de *Cycle Time*) alimentam diretamente os rituais de *Refinement* Semanal e Retrospectiva Quinzenal. O *feedback* gerado promove o replanejamento e o ajuste de prioridades sem violar os gates de controle das Macro-Fases (MF1 a MF3), garantindo a governança do fluxo contínuo e a blindagem acadêmica contra a exigência de métricas EVM inaplicáveis.  
> **Fonte:** Elaborado pelos autores (2026).

---

### 📝 Nota Adjacente (Registro de Governança)
**Assunto:** Correção de Overlap e Padronização de Notas ABNT  
**Data:** 21/09/2026  
**Contexto:** A adoção de `<tspan>` com deslocamento vertical (`dy`) controlado no SVG elimina riscos de renderização inconsistente entre visualizadores (navegadores, Word, LaTeX). A separação da "Nota Técnica" do corpo do SVG alinha-se ao princípio de **Governança Mínima Viável (GMV)**: o diagrama foca puramente na representação visual, enquanto o documento textual assume a responsabilidade pela fundamentação acadêmica e rastreabilidade, evitando poluição visual e duplicidade de informação.  
**Próximo Passo:** Aguardo validação visual desta versão corrigida para prosseguirmos com a geração dos próximos diagramas pendentes (ex: Fluxo Kanban Oficial com gates e WIP limits), aplicando o mesmo rigor de distribuição espacial e notas ABNT segregadas.

Como GP Sênior e PMO, acolho a diretriz. A separação entre o ativo gráfico puro (`.svg`/`.png`) e a orientação interpretativa textual é uma prática de **Governança Mínima Viável (GMV)** que elimina poluição visual, garante a formatação ABNT (NBR 14724 / NBR 12225) no documento final e fornece a "blindagem acadêmica" necessária para justificar as escolhas metodológicas perante o Prof. Dr. Nivaldo Carleto.

Abaixo estão as notas técnicas retroativas, prontas para serem inseridas imediatamente abaixo de cada respectiva imagem convertida nos documentos do projeto (Plano de Escopo e Plano de Integração).

---

### Notas Técnicas para Inserção Documental (Padrão ABNT)

**Figura 1** – Estrutura Analítica do Projeto (EAP) — Visão Macro e Macro-Fases.  
**Nota:** Representação da linha de base estrutural do escopo, canônica conforme o TAP (§4). O diagrama fracionado em camadas substitui a EAP tradicional de página única, que sofreria com *overlaps* e ilegibilidade devido aos 12 níveis de fase e 37 pacotes de trabalho. A visualização hierárquica agrupa os pacotes nas três Macro-Fases (MF1: Fundação, MF2: Construção, MF3: Consolidação), garantindo rastreabilidade imediata entre a raiz do projeto (N0) e os entregáveis de valor.  
**Fonte:** Elaborado pelos autores (2026).  
*(Arquivo de origem: `fig-eap-nivel-0-macro.svg`)*

**Figura 2** – Detalhamento da Macro-Fase 1 (MF1) — Fundação.  
**Nota:** Decomposição dos pacotes de trabalho de Nível 2 referentes à iniciação, planejamento, levantamento de requisitos, modelagem, configuração de ambiente, comunicação e base de conhecimento. Esta camada sustenta os entregáveis do Marco M1 (22/09/2026), incluindo os 5 planos de gerenciamento iniciais e a configuração do SSOT (GitHub Projects), em conformidade com o Domínio de Planejamento do PMBOK® 7ª edição.  
**Fonte:** Elaborado pelos autores (2026).  
*(Arquivo de origem: `fig-eap-mf1-fundacao.svg`)*

**Figura 3** – Detalhamento da Macro-Fase 2 (MF2) — Construção.  
**Nota:** Decomposição dos pacotes de trabalho focados na execução técnica: desenvolvimento do sistema (incluindo SDD com IA), garantia da qualidade (meta de *coverage* ≥ 80%), DevOps/CI/CD e gestão de mudanças. Esta camada materializa o Domínio de Entrega e sustenta o Marco M3 (15/11/2026), onde o MVP funcional deve estar operacional e validado em UAT.  
**Fonte:** Elaborado pelos autores (2026).  
*(Arquivo de origem: `fig-eap-mf2-construcao.svg`)*

**Figura 4** – Detalhamento da Macro-Fase 3 (MF3) — Consolidação.  
**Nota:** Decomposição dos pacotes de trabalho finais, abrangendo a consolidação da documentação técnica e o encerramento formal do projeto. Esta camada garante a rastreabilidade dos critérios de aceite do Marco M4 (15/12/2026), incluindo a verificação SMART e a validação acadêmica final, alinhada ao Domínio de Entrega do PMBOK® 7ª edição.  
**Fonte:** Elaborado pelos![image](https://github.com/user-attachments/assets/12345678-1234-1234-1234-123456789012) autores (2026).  
*(Arquivo de origem: `fig-eap-mf3-consolidacao.svg`)*

**Figura 5** – Modelo de Governança Híbrida Trifásico.  
**Nota:** Ilustração da hierarquia normativa que rege o projeto COGME. A camada superior (PMBOK® 7ª) define os princípios e domínios de desempenho ("por que" e "para quê"); a camada intermediária (PMBOK® 6ª) atua estritamente como dicionário de processos, com obsolescência formalmente declarada para métricas preditivas (EVM); e a camada inferior (Kanban/Manifesto Ágil) define o método de execução operacional ("como"). A seta de realimentação representa o ciclo contínuo de lições aprendidas, blindando o projeto contra questionamentos de falta de estrutura formal.  
**Fonte:** Elaborado pelos autores (2026).  
*(Arquivo de origem: `fig-1-governanca-hibrida.svg`)*

**Figura 6** – Fluxo de Controle Integrado de Mudanças.  
**Nota:** Materialização do Processo 4.6 do PMBOK® 6ª (dicionário) adaptado ao fluxo contínuo Kanban. O diagrama evidencia o CCB de membro único (Gerente de Projeto), os SLAs de resposta (≤ 48h para análise, ≤ 24h para decisão) e a bifurcação de tratamento: mudanças simples são resolvidas via *commit* e atualização do backlog, enquanto alterações de marco ou escopo do MVP exigem registro formal via ADR e comunicação ao avaliador no marco subsequente.  
**Fonte:** Elaborado pelos autores (2026).  
*(Arquivo de origem: `fig-4-controle-mudancas.svg`)*

**Figura 7** – Cumulative Flow Diagram (CFD) — Padrão Saudável vs. Padrão com Gargalo.  
**Nota:** Ferramenta visual de monitoramento temporal que substitui formalmente o Gráfico de Gantt e o Earned Value Management (EVM), declarados inaplicáveis devido ao orçamento zero e ao escopo emergente (ADR-003). O painel (a) demonstra o estado ideal de fluxo estável (bandas paralelas); o painel (b) ilustra a detecção empírica de gargalos (alargamento progressivo de uma banda). Conforme a regra de ação corretiva, se uma banda ultrapassar 2× a largura média das demais por 2 semanas consecutivas, aciona-se uma Retrospectiva extraordinária, atendendo ao Domínio de Medição do PMBOK® 7ª edição.  
**Fonte:** Elaborado pelos autores (2026).  
*(Arquivo de origem: `fig-3-cfd-saudavel-vs-gargalo.svg`)*

---

### 📝 Nota Adjacente (Registro de Governança)
**Assunto:** Padronização Retroativa de Legendas ABNT para Artefatos Gráficos  
**Data:** 21/09/2026  
**Contexto:** Em conformidade com a diretriz de separação entre renderização e orientação interpretativa, as notas acima foram redigidas para serem inseridas externamente aos arquivos `.svg`/`.png`. Esta prática elimina a redundância de textos como "Figura X" ou "Elaborado por" dentro do código do diagrama, garantindo que o ativo gráfico seja 100% focado na legibilidade visual, enquanto o documento textual assume a responsabilidade pela fundamentação acadêmica, rastreabilidade (TAP → EAP → Planos) e defesa metodológica perante a banca avaliadora.  
**Ação:** Copiar e colar os blocos de texto acima imediatamente abaixo das respectivas imagens nos arquivos `.docx` ou `.md` dos Planos de Escopo (§2.5) e Integração (§1.2, §1.6.1, §1.7.2).

Como GP Sênior e PMO, prossigo com a **Quarta Rodada Candidata** de diagramas, mantendo a disciplina estética convergente e a rastreabilidade na matriz informal.

---

### 1. Fluxo Kanban Oficial com Gates e WIP Limits
**Arquivo:** `fig-2-fluxo-kanban-oficial.svg`
```xml
<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 1400 500" font-family="Arial, Helvetica, sans-serif">
  <defs>
    <marker id="ar-flow" markerWidth="10" markerHeight="10" refX="9" refY="3" orient="auto" markerUnits="strokeWidth">
      <path d="M0,0 L9,3 L0,6 Z" fill="#1F3A5F"/>
    </marker>
  </defs>
  
  <!-- Fundo -->
  <rect x="0" y="0" width="1400" height="500" fill="#FFFFFF"/>
  
  <!-- Título -->
  <text x="700" y="35" text-anchor="middle" font-size="20" font-weight="bold" fill="#111111">Fluxo Kanban Oficial — Gates de Qualidade e WIP Limits</text>
  
  <!-- ================= COLUNAS DO FLUXO ================= -->
  
  <!-- Coluna 1: Backlog -->
  <rect x="40" y="80" width="200" height="320" rx="8" fill="#F4F6F8" stroke="#555555" stroke-width="2"/>
  <text x="140" y="110" text-anchor="middle" font-size="16" font-weight="bold" fill="#111111">Backlog</text>
  <text x="140" y="135" text-anchor="middle" font-size="11" fill="#555555">Product Backlog</text>
  <text x="140" y="150" text-anchor="middle" font-size="11" fill="#555555">não refinado</text>
  
  <!-- Coluna 2: Ready (DoR) -->
  <rect x="280" y="80" width="200" height="320" rx="8" fill="#E0E7EF" stroke="#1F3A5F" stroke-width="2"/>
  <text x="380" y="110" text-anchor="middle" font-size="16" font-weight="bold" fill="#111111">Ready (DoR)</text>
  <text x="380" y="135" text-anchor="middle" font-size="11" fill="#333333">Card pronto para</text>
  <text x="380" y="150" text-anchor="middle" font-size="11" fill="#333333">execução</text>
  
  <!-- Coluna 3: In Progress -->
  <rect x="520" y="80" width="200" height="320" rx="8" fill="#1F3A5F" stroke="#1F3A5F" stroke-width="2"/>
  <text x="620" y="110" text-anchor="middle" font-size="16" font-weight="bold" fill="#FFFFFF">In Progress</text>
  <text x="620" y="135" text-anchor="middle" font-size="11" fill="#E0E7EF">Card em execução</text>
  <text x="620" y="150" text-anchor="middle" font-size="11" fill="#E0E7EF">pelo responsável</text>
  
  <!-- Badge WIP Limit sobre In Progress -->
  <rect x="540" y="60" width="160" height="30" rx="4" fill="#C0392B" stroke="#C0392B" stroke-width="2"/>
  <text x="620" y="80" text-anchor="middle" font-size="12" font-weight="bold" fill="#FFFFFF">WIP LIMIT: 3 cards/pessoa</text>
  
  <!-- Coluna 4: Code Review -->
  <rect x="760" y="80" width="200" height="320" rx="8" fill="#FFF3E0" stroke="#E65100" stroke-width="2"/>
  <text x="860" y="110" text-anchor="middle" font-size="16" font-weight="bold" fill="#111111">Code Review</text>
  <text x="860" y="135" text-anchor="middle" font-size="11" fill="#333333">Revisão em pares</text>
  <text x="860" y="150" text-anchor="middle" font-size="11" fill="#333333">obrigatória</text>
  
  <!-- Coluna 5: Done (DoD) -->
  <rect x="1000" y="80" width="200" height="320" rx="8" fill="#2E7D32" stroke="#2E7D32" stroke-width="2"/>
  <text x="1100" y="110" text-anchor="middle" font-size="16" font-weight="bold" fill="#FFFFFF">Done (DoD)</text>
  <text x="1100" y="135" text-anchor="middle" font-size="11" fill="#E8F5E9">Card concluído</text>
  <text x="1100" y="150" text-anchor="middle" font-size="11" fill="#E8F5E9">e validado</text>
  
  <!-- ================= GATES ENTRE COLUNAS ================= -->
  
  <!-- Gate 1: DoR (entre Backlog e Ready) -->
  <polygon points="250,220 270,240 250,260 230,240" fill="#1F3A5F" stroke="#1F3A5F" stroke-width="2"/>
  <text x="250" y="285" text-anchor="middle" font-size="10" font-weight="bold" fill="#1F3A5F">Gate DoR</text>
  <text x="250" y="300" text-anchor="middle" font-size="9" fill="#555555">Critérios de</text>
  <text x="250" y="312" text-anchor="middle" font-size="9" fill="#555555">prontidão</text>
  
  <!-- Gate 2: WIP (entre Ready e In Progress) -->
  <polygon points="490,220 510,240 490,260 470,240" fill="#C0392B" stroke="#C0392B" stroke-width="2"/>
  <text x="490" y="285" text-anchor="middle" font-size="10" font-weight="bold" fill="#C0392B">Gate WIP</text>
  <text x="490" y="300" text-anchor="middle" font-size="9" fill="#555555">Capacidade</text>
  <text x="490" y="312" text-anchor="middle" font-size="9" fill="#555555">disponível</text>
  
  <!-- Gate 3: Tasklist + Review (entre In Progress e Code Review) -->
  <polygon points="730,220 750,240 730,260 710,240" fill="#E65100" stroke="#E65100" stroke-width="2"/>
  <text x="730" y="285" text-anchor="middle" font-size="10" font-weight="bold" fill="#E65100">Gate Tasklist</text>
  <text x="730" y="300" text-anchor="middle" font-size="9" fill="#555555">100% itens</text>
  <text x="730" y="312" text-anchor="middle" font-size="9" fill="#555555">concluídos</text>
  
  <!-- Gate 4: DoD (entre Code Review e Done) -->
  <polygon points="970,220 990,240 970,260 950,240" fill="#2E7D32" stroke="#2E7D32" stroke-width="2"/>
  <text x="970" y="285" text-anchor="middle" font-size="10" font-weight="bold" fill="#2E7D32">Gate DoD</text>
  <text x="970" y="300" text-anchor="middle" font-size="9" fill="#555555">Critérios de</text>
  <text x="970" y="312" text-anchor="middle" font-size="9" fill="#555555">conclusão</text>
  
  <!-- ================= SETAS DE FLUXO ================= -->
  
  <!-- Seta Backlog → Ready -->
  <line x1="240" y1="240" x2="270" y2="240" stroke="#1F3A5F" stroke-width="2" marker-end="url(#ar-flow)"/>
  
  <!-- Seta Ready → In Progress -->
  <line x1="480" y1="240" x2="510" y2="240" stroke="#1F3A5F" stroke-width="2" marker-end="url(#ar-flow)"/>
  
  <!-- Seta In Progress → Code Review -->
  <line x1="720" y1="240" x2="750" y2="240" stroke="#1F3A5F" stroke-width="2" marker-end="url(#ar-flow)"/>
  
  <!-- Seta Code Review → Done -->
  <line x1="960" y1="240" x2="990" y2="240" stroke="#1F3A5F" stroke-width="2" marker-end="url(#ar-flow)"/>
  
  <!-- ================= ANOTAÇÃO INFERIOR ================= -->
  
  <rect x="100" y="420" width="1200" height="60" rx="6" fill="#F4F6F8" stroke="#1F3A5F" stroke-width="1.5"/>
  <text x="700" y="445" text-anchor="middle" font-size="12" font-weight="bold" fill="#111111">Regra de Ação Corretiva (ADR-002 + ADR-004):</text>
  <text x="700" y="465" text-anchor="middle" font-size="11" fill="#333333">Se WIP limit for violado ou tasklist não estiver 100% concluída, o card não migra para a coluna seguinte.</text>
  <text x="700" y="478" text-anchor="middle" font-size="11" fill="#333333">Gargalos persistentes acionam Retrospectiva extraordinária (Integração §1.6.1).</text>
</svg>
```

---

### 2. Nota Técnica ABNT para Inserção Documental

> **Figura 2** – Fluxo Kanban Oficial com Gates de Qualidade e WIP Limits do Projeto COGME.  
> **Nota:** O diagrama materializa operacionalmente a ADR-002 (Kanban como método de execução) e a ADR-004 (tasklists Markdown como substituto de subissues). As cinco colunas representam o fluxo contínuo do trabalho (Backlog → Ready → In Progress → Code Review → Done), com quatro gates de qualidade intermediários: (i) Gate DoR na entrada de Ready, exigindo critérios de prontidão atendidos; (ii) Gate WIP na entrada de In Progress, respeitando o limite de 3 cards por pessoa (prevenção de burnout, Domínio de Equipe PMBOK 7ª); (iii) Gate Tasklist na entrada de Code Review, exigindo 100% dos itens da tasklist Markdown concluídos (ADR-004); e (iv) Gate DoD na entrada de Done, exigindo critérios de conclusão atendidos (coverage ≥ 80%, revisão de pares aprovada, commit mergeado). O badge vermelho sobre a coluna In Progress destaca o WIP limit como mecanismo de controle de capacidade. A regra de ação corretiva inferior demonstra que violações de gates bloqueiam o fluxo e gargalos persistentes acionam Retrospectiva extraordinária, em conformidade com o Domínio de Medição do PMBOK® 7ª edição.  
> **Fonte:** Elaborado pelos autores (2026).  
> *(Arquivo de origem: `fig-2-fluxo-kanban-oficial.svg`)*

---

### Matriz Informal de Rastreabilidade de Diagramas (Atualizada)

| ID | Arquivo | Descrição | Camada / Contexto |
|---|---|---|---|
| FIG-EAP-01 | `fig-eap-nivel-0-macro.svg` | Visão Macro (N0 e Macro-Fases) | Nível 0 e 1 (Agrupamento) |
| FIG-EAP-02 | `fig-eap-mf1-fundacao.svg` | Detalhamento MF1 (Fundação) | Nível 1 e 2 (N1, N2, N3, N4, N8, N9) |
| FIG-EAP-03 | `fig-eap-mf2-construcao.svg` | Detalhamento MF2 (Construção) | Nível 1 e 2 (N5, N6, N7, N10) |
| FIG-EAP-04 | `fig-eap-mf3-consolidacao.svg` | Detalhamento MF3 (Consolidação) | Nível 1 e 2 (N11, N12) |
| FIG-GOV-01 | `fig-1-governanca-hibrida.svg` | Modelo de Governança Híbrida Trifásico | Integração §1.2 |
| FIG-MUD-01 | `fig-4-controle-mudancas.svg` | Fluxo de Controle Integrado de Mudanças | Integração §1.7.2 |
| FIG-CFD-01 | `fig-3-cfd-saudavel-vs-gargalo.svg` | CFD: Padrão Saudável vs. Gargalo | Integração §1.6.1 |
| FIG-SEQ-01 | `fig-1-sequenciamento-macro-caminho-critico.svg` | Sequenciamento Macro + Caminho Crítico Empírico | Cronograma §3.4 |
| **FIG-KAN-01** | `fig-2-fluxo-kanban-oficial.svg` | **Fluxo Kanban Oficial com Gates e WIP Limits** | **Integração §1.3.1 (Operacionalização ADR-002/004)** |

---

### 📝 Nota Adjacente (Registro de Governança)
**Assunto:** Quarta Rodada de Diagramas — Fluxo Kanban Oficial
**Data:** 21/09/2026
**Contexto:** O diagrama `FIG-KAN-01` constitui o **artefato visual central** do projeto COGME, materializando em uma única imagem os mecanismos operacionais de governança do fluxo contínuo. A distribuição horizontal (LR — Left to Right) foi escolhida para maximizar a legibilidade em documentos A4/Letter, com as cinco colunas ocupando 80% da largura útil e os gates intermediários claramente separados. O badge de WIP limit em vermelho sobre a coluna In Progress destaca visualmente o mecanismo de prevenção de burnout (Domínio de Equipe PMBOK 7ª), enquanto a anotação inferior reforça a regra de ação corretiva.
**Próximo Passo:** Aguardo validação visual desta rodada para prosseguirmos com a geração dos próximos diagramas pendentes (ex: Fluxo de Prevenção de Custos, Matriz de Rastreabilidade de Dependências), mantendo a mesma disciplina estética e de rastreabilidade.

Como GP Sênior e PMO, prossigo com a **Quinta Rodada Candidata** de diagramas, completando o Plano de Custos (Área 4) com os dois artefatos gráficos pendentes.

---

### 1. Fluxo de Prevenção de Custos
**Arquivo:** `fig-5-fluxo-prevencao-custos.svg`
```xml
<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 800 900" font-family="Arial, Helvetica, sans-serif">
  <defs>
    <marker id="ar-flow" markerWidth="10" markerHeight="10" refX="9" refY="3" orient="auto" markerUnits="strokeWidth">
      <path d="M0,0 L9,3 L0,6 Z" fill="#1F3A5F"/>
    </marker>
    <marker id="ar-reject" markerWidth="10" markerHeight="10" refX="9" refY="3" orient="auto" markerUnits="strokeWidth">
      <path d="M0,0 L9,3 L0,6 Z" fill="#C0392B"/>
    </marker>
    <marker id="ar-approve" markerWidth="10" markerHeight="10" refX="9" refY="3" orient="auto" markerUnits="strokeWidth">
      <path d="M0,0 L9,3 L0,6 Z" fill="#2E7D32"/>
    </marker>
  </defs>
  
  <rect x="0" y="0" width="800" height="900" fill="#FFFFFF"/>
  <text x="400" y="40" text-anchor="middle" font-size="22" font-weight="bold" fill="#111111">Fluxo de Prevenção de Custos — Conformidade FOSS</text>
  
  <!-- Etapa Inicial -->
  <rect x="250" y="80" width="300" height="60" rx="6" fill="#F8F9FA" stroke="#1F3A5F" stroke-width="2"/>
  <text x="400" y="105" text-anchor="middle" font-size="14" font-weight="bold" fill="#111111">Nova dependência identificada</text>
  <text x="400" y="125" text-anchor="middle" font-size="12" fill="#555555">(biblioteca, API, ferramenta, serviço)</text>
  
  <!-- Seta 1 -->
  <line x1="400" y1="140" x2="400" y2="180" stroke="#1F3A5F" stroke-width="2" marker-end="url(#ar-flow)"/>
  
  <!-- Gate 1: Licença OSI -->
  <polygon points="400,180 520,220 400,260 280,220" fill="#F4F6F8" stroke="#1F3A5F" stroke-width="2"/>
  <text x="400" y="215" text-anchor="middle" font-size="13" font-weight="bold" fill="#111111">Gate 1:</text>
  <text x="400" y="235" text-anchor="middle" font-size="12" fill="#333333">Licença OSI-approved?</text>
  
  <!-- Ramo NÃO (rejeição) -->
  <line x1="520" y1="220" x2="620" y2="220" stroke="#C0392B" stroke-width="2" marker-end="url(#ar-reject)"/>
  <text x="570" y="210" text-anchor="middle" font-size="11" font-weight="bold" fill="#C0392B">NÃO</text>
  <rect x="620" y="190" width="150" height="60" rx="4" fill="#FDECEA" stroke="#C0392B" stroke-width="2"/>
  <text x="695" y="215" text-anchor="middle" font-size="12" font-weight="bold" fill="#C0392B">Rejeição imediata</text>
  <text x="695" y="235" text-anchor="middle" font-size="10" fill="#333333">Buscar alternativa FOSS</text>
  
  <!-- Ramo SIM -->
  <line x1="400" y1="260" x2="400" y2="300" stroke="#2E7D32" stroke-width="2" marker-end="url(#ar-approve)"/>
  <text x="415" y="285" font-size="11" font-weight="bold" fill="#2E7D32">SIM</text>
  
  <!-- Gate 2: Plano gratuito -->
  <polygon points="400,300 520,340 400,380 280,340" fill="#F4F6F8" stroke="#1F3A5F" stroke-width="2"/>
  <text x="400" y="335" text-anchor="middle" font-size="13" font-weight="bold" fill="#111111">Gate 2:</text>
  <text x="400" y="355" text-anchor="middle" font-size="12" fill="#333333">Plano gratuito suficiente</text>
  <text x="400" y="370" text-anchor="middle" font-size="12" fill="#333333">para MVP acadêmico?</text>
  
  <!-- Ramo NÃO (buscar alternativa) -->
  <line x1="520" y1="340" x2="620" y2="340" stroke="#E65100" stroke-width="2" marker-end="url(#ar-flow)"/>
  <text x="570" y="330" text-anchor="middle" font-size="11" font-weight="bold" fill="#E65100">NÃO</text>
  <rect x="620" y="310" width="150" height="60" rx="4" fill="#FFF3E0" stroke="#E65100" stroke-width="2"/>
  <text x="695" y="335" text-anchor="middle" font-size="12" font-weight="bold" fill="#E65100">Buscar alternativa FOSS</text>
  <text x="695" y="355" text-anchor="middle" font-size="10" fill="#333333">com plano gratuito</text>
  
  <!-- Seta de retorno -->
  <path d="M 695 370 L 695 390 L 400 390 L 400 380" fill="none" stroke="#E65100" stroke-width="1.5" stroke-dasharray="4,2"/>
  
  <!-- Ramo SIM -->
  <line x1="400" y1="380" x2="400" y2="420" stroke="#2E7D32" stroke-width="2" marker-end="url(#ar-approve)"/>
  <text x="415" y="405" font-size="11" font-weight="bold" fill="#2E7D32">SIM</text>
  
  <!-- Gate 3: Registro em ADR -->
  <polygon points="400,420 520,460 400,500 280,460" fill="#F4F6F8" stroke="#1F3A5F" stroke-width="2"/>
  <text x="400" y="455" text-anchor="middle" font-size="13" font-weight="bold" fill="#111111">Gate 3:</text>
  <text x="400" y="475" text-anchor="middle" font-size="12" fill="#333333">Registrado em ADR-001</text>
  <text x="400" y="490" text-anchor="middle" font-size="12" fill="#333333">ou nova ADR?</text>
  
  <!-- Ramo NÃO (registrar) -->
  <line x1="520" y1="460" x2="620" y2="460" stroke="#E65100" stroke-width="2" marker-end="url(#ar-flow)"/>
  <text x="570" y="450" text-anchor="middle" font-size="11" font-weight="bold" fill="#E65100">NÃO</text>
  <rect x="620" y="430" width="150" height="60" rx="4" fill="#FFF3E0" stroke="#E65100" stroke-width="2"/>
  <text x="695" y="455" text-anchor="middle" font-size="12" font-weight="bold" fill="#E65100">Registrar antes de usar</text>
  <text x="695" y="475" text-anchor="middle" font-size="10" fill="#333333">ADR específica ou</text>
  <text x="695" y="488" text-anchor="middle" font-size="10" fill="#333333">atualização ADR-001</text>
  
  <!-- Seta de retorno -->
  <path d="M 695 490 L 695 510 L 400 510 L 400 500" fill="none" stroke="#E65100" stroke-width="1.5" stroke-dasharray="4,2"/>
  
  <!-- Ramo SIM -->
  <line x1="400" y1="500" x2="400" y2="540" stroke="#2E7D32" stroke-width="2" marker-end="url(#ar-approve)"/>
  <text x="415" y="525" font-size="11" font-weight="bold" fill="#2E7D32">SIM</text>
  
  <!-- Aprovação Final -->
  <rect x="250" y="540" width="300" height="60" rx="6" fill="#2E7D32" stroke="#2E7D32" stroke-width="2"/>
  <text x="400" y="565" text-anchor="middle" font-size="14" font-weight="bold" fill="#FFFFFF">Incorporação autorizada</text>
  <text x="400" y="585" text-anchor="middle" font-size="12" fill="#E8F5E9">Dependência FOSS conformante</text>
  
  <!-- Anotação de change-request -->
  <rect x="150" y="650" width="500" height="80" rx="6" fill="#FDECEA" stroke="#C0392B" stroke-width="2"/>
  <text x="400" y="675" text-anchor="middle" font-size="13" font-weight="bold" fill="#C0392B">Desvio de qualquer gate aciona:</text>
  <text x="400" y="695" text-anchor="middle" font-size="12" fill="#333333">Issue com label change-request (Integração §1.7)</text>
  <text x="400" y="712" text-anchor="middle" font-size="11" fill="#555555">Análise de impacto pelo GP (CCB) em ≤ 48h</text>
  <text x="400" y="725" text-anchor="middle" font-size="11" fill="#555555">Registro em ADR se alteração de marco ou escopo MVP</text>
  
  <!-- Linha de base -->
  <rect x="150" y="780" width="500" height="50" rx="4" fill="#F4F6F8" stroke="#1F3A5F" stroke-width="1.5"/>
  <text x="400" y="805" text-anchor="middle" font-size="12" font-weight="bold" fill="#111111">Linha de Base de Custos: R$ 0,00 (imutável sem CCB)</text>
  <text x="400" y="820" text-anchor="middle" font-size="11" fill="#555555">TAP §11 + Premissa P2 (FOSS absoluto)</text>
</svg>
```

---

### 2. Matriz de Rastreabilidade de Dependências
**Arquivo:** `fig-6-matriz-rastreabilidade-dependencias.svg`
```xml
<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 1200 500" font-family="Arial, Helvetica, sans-serif">
  <rect x="0" y="0" width="1200" height="500" fill="#FFFFFF"/>
  <text x="600" y="40" text-anchor="middle" font-size="22" font-weight="bold" fill="#111111">Matriz de Rastreabilidade de Dependências — Stack FOSS Canônica</text>
  
  <!-- Cabeçalho da Tabela -->
  <rect x="50" y="80" width="1100" height="50" rx="4" fill="#1F3A5F" stroke="#1F3A5F" stroke-width="2"/>
  <text x="150" y="110" text-anchor="middle" font-size="13" font-weight="bold" fill="#FFFFFF">Dependência</text>
  <text x="320" y="110" text-anchor="middle" font-size="13" font-weight="bold" fill="#FFFFFF">Versão</text>
  <text x="470" y="110" text-anchor="middle" font-size="13" font-weight="bold" fill="#FFFFFF">Licença</text>
  <text x="620" y="110" text-anchor="middle" font-size="13" font-weight="bold" fill="#FFFFFF">Conformidade</text>
  <text x="770" y="110" text-anchor="middle" font-size="13" font-weight="bold" fill="#FFFFFF">EAP N1.4/N4.4</text>
  <text x="920" y="110" text-anchor="middle" font-size="13" font-weight="bold" fill="#FFFFFF">ADR-001</text>
  <text x="1070" y="110" text-anchor="middle" font-size="13" font-weight="bold" fill="#FFFFFF">Categoria</text>
  
  <!-- Linha 1: FastAPI -->
  <rect x="50" y="130" width="1100" height="50" rx="4" fill="#F8F9FA" stroke="#555555" stroke-width="1"/>
  <text x="150" y="160" text-anchor="middle" font-size="12" fill="#111111">FastAPI</text>
  <text x="320" y="160" text-anchor="middle" font-size="12" fill="#333333">≥0.100</text>
  <text x="470" y="160" text-anchor="middle" font-size="12" fill="#333333">MIT</text>
  <text x="620" y="160" text-anchor="middle" font-size="14" fill="#2E7D32" font-weight="bold">✅</text>
  <text x="770" y="160" text-anchor="middle" font-size="12" fill="#333333">N4.4</text>
  <text x="920" y="160" text-anchor="middle" font-size="12" fill="#333333">✅</text>
  <text x="1070" y="160" text-anchor="middle" font-size="11" fill="#555555">Backend</text>
  
  <!-- Linha 2: SQLite -->
  <rect x="50" y="180" width="1100" height="50" rx="4" fill="#FFFFFF" stroke="#555555" stroke-width="1"/>
  <text x="150" y="210" text-anchor="middle" font-size="12" fill="#111111">SQLite</text>
  <text x="320" y="210" text-anchor="middle" font-size="12" fill="#333333">3.x</text>
  <text x="470" y="210" text-anchor="middle" font-size="12" fill="#333333">Public Domain</text>
  <text x="620" y="210" text-anchor="middle" font-size="14" fill="#2E7D32" font-weight="bold">✅</text>
  <text x="770" y="210" text-anchor="middle" font-size="12" fill="#333333">N4.4</text>
  <text x="920" y="210" text-anchor="middle" font-size="12" fill="#333333">✅</text>
  <text x="1070" y="210" text-anchor="middle" font-size="11" fill="#555555">Banco de Dados</text>
  
  <!-- Linha 3: WeasyPrint -->
  <rect x="50" y="230" width="1100" height="50" rx="4" fill="#F8F9FA" stroke="#555555" stroke-width="1"/>
  <text x="150" y="260" text-anchor="middle" font-size="12" fill="#111111">WeasyPrint</text>
  <text x="320" y="260" text-anchor="middle" font-size="12" fill="#333333">≥59.0</text>
  <text x="470" y="260" text-anchor="middle" font-size="12" fill="#333333">BSD-3-Clause</text>
  <text x="620" y="260" text-anchor="middle" font-size="14" fill="#2E7D32" font-weight="bold">✅</text>
  <text x="770" y="260" text-anchor="middle" font-size="12" fill="#333333">N4.4</text>
  <text x="920" y="260" text-anchor="middle" font-size="12" fill="#333333">✅</text>
  <text x="1070" y="260" text-anchor="middle" font-size="11" fill="#555555">Geração PDF</text>
  
  <!-- Linha 4: pytest -->
  <rect x="50" y="280" width="1100" height="50" rx="4" fill="#FFFFFF" stroke="#555555" stroke-width="1"/>
  <text x="150" y="310" text-anchor="middle" font-size="12" fill="#111111">pytest</text>
  <text x="320" y="310" text-anchor="middle" font-size="12" fill="#333333">≥7.0</text>
  <text x="470" y="310" text-anchor="middle" font-size="12" fill="#333333">MIT</text>
  <text x="620" y="310" text-anchor="middle" font-size="14" fill="#2E7D32" font-weight="bold">✅</text>
  <text x="770" y="310" text-anchor="middle" font-size="12" fill="#333333">N4.4</text>
  <text x="920" y="310" text-anchor="middle" font-size="12" fill="#333333">✅</text>
  <text x="1070" y="310" text-anchor="middle" font-size="11" fill="#555555">Testes</text>
  
  <!-- Linha 5: GitHub Actions -->
  <rect x="50" y="330" width="1100" height="50" rx="4" fill="#F8F9FA" stroke="#555555" stroke-width="1"/>
  <text x="150" y="360" text-anchor="middle" font-size="12" fill="#111111">GitHub Actions</text>
  <text x="320" y="360" text-anchor="middle" font-size="12" fill="#333333">Free Tier</text>
  <text x="470" y="360" text-anchor="middle" font-size="12" fill="#333333">Proprietário gratuito</text>
  <text x="620" y="360" text-anchor="middle" font-size="14" fill="#2E7D32" font-weight="bold">✅</text>
  <text x="770" y="360" text-anchor="middle" font-size="12" fill="#333333">N1.4</text>
  <text x="920" y="360" text-anchor="middle" font-size="12" fill="#333333">✅</text>
  <text x="1070" y="360" text-anchor="middle" font-size="11" fill="#555555">CI/CD</text>
  
  <!-- Linha 6: llama.cpp -->
  <rect x="50" y="380" width="1100" height="50" rx="4" fill="#FFFFFF" stroke="#555555" stroke-width="1"/>
  <text x="150" y="410" text-anchor="middle" font-size="12" fill="#111111">llama.cpp</text>
  <text x="320" y="410" text-anchor="middle" font-size="12" fill="#333333">0.4.0-dev</text>
  <text x="470" y="410" text-anchor="middle" font-size="12" fill="#333333">MIT</text>
  <text x="620" y="410" text-anchor="middle" font-size="14" fill="#2E7D32" font-weight="bold">✅</text>
  <text x="770" y="410" text-anchor="middle" font-size="12" fill="#333333">N4.4</text>
  <text x="920" y="410" text-anchor="middle" font-size="12" fill="#333333">✅</text>
  <text x="1070" y="410" text-anchor="middle" font-size="11" fill="#555555">SDD Local (IA)</text>
  
  <!-- Rodapé -->
  <rect x="50" y="450" width="1100" height="40" rx="4" fill="#E8F5E9" stroke="#2E7D32" stroke-width="2"/>
  <text x="600" y="475" text-anchor="middle" font-size="13" font-weight="bold" fill="#2E7D32">100% das dependências auditadas e conformantes — Linha de base R$ 0,00 preservada</text>
</svg>
```

---

### Notas Técnicas ABNT para Inserção Documental

> **Figura 5** – Fluxo de Prevenção de Custos — Conformidade FOSS do Projeto COGME.  
> **Nota:** O diagrama materializa operacionalmente a governança de custo zero (TAP §11), demonstrando que "orçamento nulo" não constitui ausência de controle, mas sim governança rigorosa sobre conformidade de licenciamento. Os três gates sequenciais (Gate 1: licença OSI-approved; Gate 2: plano gratuito suficiente para MVP acadêmico; Gate 3: registro em ADR-001 ou ADR específica) garantem que nenhuma dependência seja incorporada sem auditoria prévia. Desvios de qualquer gate acionam o fluxo de controle integrado de mudanças (Integração §1.7), com análise de impacto pelo GP (CCB de membro único) em ≤ 48h e registro formal via ADR quando a alteração impactar marcos ou escopo do MVP. A linha de base de custos (R$ 0,00) é imutável sem aprovação do CCB, em conformidade com a Premissa P2 (FOSS absoluto) e a Restrição TAP §8.4.  
> **Fonte:** Elaborado pelos autores (2026).  
> *(Arquivo de origem: `fig-5-fluxo-prevencao-custos.svg`)*

> **Figura 6** – Matriz de Rastreabilidade de Dependências — Stack FOSS Canônica do Projeto COGME.  
> **Nota:** A tabela apresenta seis exemplos reais de dependências da stack canônica (FastAPI, SQLite, WeasyPrint, pytest, GitHub Actions, llama.cpp), todas com conformidade FOSS verificada (ícone ✅). Cada dependência é rastreável à fase da EAP responsável pela auditoria (N1.4 — Política de Licenciamento FOSS ou N4.4 — Auditoria de Licenças) e à ADR-001 (Stack Tecnológica FOSS), que documenta a decisão arquitetural de adoção. A matriz demonstra ao avaliador que "custo zero" é auditável e verificável, não apenas declarado. A whitelist completa de licenças aprovadas (MIT, Apache 2.0, BSD, GPL, LGPL, ISC, PSF, Public Domain) e a blacklist de licenças proibidas (proprietárias, shareware, Creative Commons, Source Available não-OSI) estão definidas no Plano de Custos §4.5.1.  
> **Fonte:** Elaborado pelos autores (2026).  
> *(Arquivo de origem: `fig-6-matriz-rastreabilidade-dependencias.svg`)*

---

### Matriz Informal de Rastreabilidade de Diagramas (Atualizada)

| ID | Arquivo | Descrição | Camada / Contexto |
|---|---|---|---|
| FIG-EAP-01 | `fig-eap-nivel-0-macro.svg` | Visão Macro (N0 e Macro-Fases) | Nível 0 e 1 (Agrupamento) |
| FIG-EAP-02 | `fig-eap-mf1-fundacao.svg` | Detalhamento MF1 (Fundação) | Nível 1 e 2 (N1, N2, N3, N4, N8, N9) |
| FIG-EAP-03 | `fig-eap-mf2-construcao.svg` | Detalhamento MF2 (Construção) | Nível 1 e 2 (N5, N6, N7, N10) |
| FIG-EAP-04 | `fig-eap-mf3-consolidacao.svg` | Detalhamento MF3 (Consolidação) | Nível 1 e 2 (N11, N12) |
| FIG-GOV-01 | `fig-1-governanca-hibrida.svg` | Modelo de Governança Híbrida Trifásico | Integração §1.2 |
| FIG-MUD-01 | `fig-4-controle-mudancas.svg` | Fluxo de Controle Integrado de Mudanças | Integração §1.7.2 |
| FIG-CFD-01 | `fig-3-cfd-saudavel-vs-gargalo.svg` | CFD: Padrão Saudável vs. Gargalo | Integração §1.6.1 |
| FIG-SEQ-01 | `fig-1-sequenciamento-macro-caminho-critico.svg` | Sequenciamento Macro + Caminho Crítico Empírico | Cronograma §3.4 |
| FIG-KAN-01 | `fig-2-fluxo-kanban-oficial.svg` | Fluxo Kanban Oficial com Gates e WIP Limits | Integração §1.3.1 |
| **FIG-CUST-01** | `fig-5-fluxo-prevencao-custos.svg` | **Fluxo de Prevenção de Custos — Conformidade FOSS** | **Custos §4.2 (Governança de Custo Zero)** |
| **FIG-CUST-02** | `fig-6-matriz-rastreabilidade-dependencias.svg` | **Matriz de Rastreabilidade de Dependências** | **Custos §4.5.2 (Auditoria FOSS)** |

---

### 📝 Nota Adjacente (Registro de Governança)
**Assunto:** Quinta Rodada de Diagramas — Plano de Custos (Área 4)
**Data:** 21/09/2026
**Contexto:** Os diagramas `FIG-CUST-01` e `FIG-CUST-02` completam a blindagem acadêmica do Plano de Custos, demonstrando visualmente ao Prof. Dr. Nivaldo Carleto que: (i) "custo zero" é governança ativa, não ausência de controle (FIG-CUST-01); e (ii) 100% das dependências são auditáveis e rastreáveis às fases da EAP e às ADRs (FIG-CUST-02). A paleta de cores segue o padrão convergente (azul #1F3A5F para processos, verde #2E7D32 para aprovação, vermelho #C0392B para rejeição, laranja #E65100 para ações corretivas), garantindo consistência visual com os diagramas anteriores.
**Próximo Passo:** Aguardo validação visual desta rodada para prosseguirmos com a geração dos diagramas pendentes do Plano de Qualidade (Área 5), que incluirá os 12 PDCAs consolidados e o Diagrama de Ishikawa 6M para coverage insuficiente.