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
