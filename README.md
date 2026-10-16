# ACESSILIA — Sistema Brasileiro de Normas de Acessibilidade Digital e Descrição Semântica

> **Versão**: 1.1.0 · **Data**: 2026-07-16  
> **RFC 2119/8174**: Os termos **DEVE**, **NÃO DEVE**, **PODE** e **RECOMENDA-SE** seguem [RFC 2119](https://tools.ietf.org/html/rfc2119) e [RFC 8174](https://tools.ietf.org/html/rfc8174).

---

## Sumário

- [1. O Que é ACESSILIA](#1-o-que-é-acessilia)
- [2. Por Que ACESSILIA](#2-por-que-acessilia)
- [3. Arquitetura do Padrão](#3-arquitetura-do-padrão)
- [4. Terminologia Resumida](#4-terminologia-resumida)
- [5. Famílias de Conteúdo](#5-famílias-de-conteúdo)
- [6. Níveis de Conformidade](#6-níveis-de-conformidade)
- [7. Identificadores Permanentes](#7-identificadores-permanentes)
- [8. Como Começar](#8-como-começar)
- [9. Validação e Ferramentas](#9-validação-e-ferramentas)
- [10. Conformidade com Padrões Externos](#10-conformidade-com-padrões-externos)
- [11. Estrutura do Repositório](#11-estrutura-do-repositório)
- [12. Fluxo de Revisão](#12-fluxo-de-revisão)
- [13. Contribuindo](#13-contribuindo)
- [14. Licença](#14-licença)
- [15. Contato](#15-contato)

---

## 1. O Que é ACESSILIA

**ACESSILIA** (*Sistema Brasileiro de Normas de Acessibilidade Digital e Descrição Semântica*) é um padrão técnico brasileiro que estabelece especificações técnicas, perfis de conformidade e boas práticas para conteúdos, documentos e formatos digitais acessíveis (incluindo **PDF/UA**, **EPUB 3**, **DAISY/MECDAISY**, normas **ISO** e **ABNT**).

O padrão integra duas dimensões fundamentais da acessibilidade digital:
1. **Semântica do Conteúdo**: regras rigorosas para elaboração de descrições semânticas objetivas de imagens, gráficos, dados estatísticos, fórmulas científicas, materiais didáticos e mídias audiovisuais.
2. **Estrutura e Formato de Documentos**: diretrizes arquiteturais para que arquivos e publicações digitais preservem marcação de acessibilidade, hierarquia de títulos, ordem lógica de leitura, tabelas semânticas e metadados de conformidade.

O padrão fornece:

- **Descrições objetivas**: texto semântico que relata o conteúdo de forma verificável e contextualizada.
- **Perfis para formatos digitais**: especificações para conformidade com **PDF/UA-1/2 (ISO 14289)**, **EPUB Accessibility (ISO/IEC 23761)**, **DAISY 3** e documentos acadêmicos (**Manual REBECA / ABNT**).
- **Metadata estruturados**: dados em JSON/XML que acompanham descrições e declarações de conformidade de documentos.
- **Validação automatizada**: linter que verifica conformidade com schemas, regras e perfis.
- **Auditoria**: procedimentos de revisão humana e critérios de amparo legal (ex.: Lei nº 9.610/1998, Art. 46).

> O objetivo do ACESSILIA é assegurar que conteúdos e documentos digitais sejam universalmente acessíveis, objetivos, reproduzíveis, verificáveis e tecnologicamente interoperáveis com sintetizadores e tecnologias assistivas.

---

## 2. Por Que ACESSILIA

| Problema | Solução ACESSILIA |
|----------|-------------------|
| Descrições subjetivas e com inferências | Regras de **Objetividade** e **Fidelidade** (ACESSILIA-100) |
| Inconsistência entre descritores | Padronização de **terminologia** e **estrutura** |
| Ausência de metadata | **Esquemas JSON/XSD** com campos obrigatórios |
| Dificuldade de verificação automatizada | **acessilia-lint** com regras por família |
| Falta de rastreabilidade | **Identificadores permanentes** (`ACL-<FAMÍLIA>-<TIPO>-<NÚMERO>`) |
| Incompatibilidade com normas externas | Mapeamento para **WCAG 2.2**, **EPUB 3**, **PDF/UA-1** |

---

## 3. Arquitetura do Padrão

O ACESSILIA é modular. Cada **Família** (Family) é um módulo independente com regras específicas para um tipo de conteúdo:

```
ACESSILIA-Base (arquitetura central)
    │
    ├── ACESSILIA-100 (terminologia e princípios)
    ├── ACESSILIA-200 (imagens estáticas)
    ├── ACESSILIA-300 (gráficos, tabelas e diagramas)
    ├── ACESSILIA-400 (conteúdo científico)
    ├── ACESSILIA-500 (conteúdo educacional)
    ├── ACESSILIA-600 (conteúdo multimídia)
    ├── ACESSILIA-700 (validação e conformidade)
    └── ACESSILIA-800 (perfis de acessibilidade)
```

O arquivo **`manifest.yml`** atua como catálogo de famílias e controla a ordem de importação.

---

## 4. Terminologia Resumida

> Para o glossário completo, consulte [ACESSILIA-100 Seção 6](ACESSILIA-100.md#6-glossário).  
> Para o guia completo de terminologia, consulte [TERMINOLOGY_GUIDE.md](TERMINOLOGY_GUIDE.md).

### 4.1 Termos Fundamentais

| Termo | Definição Resumida |
|-------|-------------------|
| **Família** (Family) | Conjunto de regras aplicáveis a um tipo específico de conteúdo (ex.: 200 para imagens). |
| **Critério** (Criterion) | Regra específica com identificador permanente, evidência obrigatória e ponto de verificação. |
| **Metadata** | Dados estruturados (JSON/XML) que acompanham a descrição textual. |
| **Conformidade** (Conformity) | Estado de atendimento a todos os critérios obrigatórios aplicáveis. |
| **Validação** (Validation) | Processo de verificar se conteúdo e metadata atendem aos requisitos. |
| **Auditoria** (Audit) | Revisão humana independente para validar conformidade além da validação automática. |

### 4.2 Princípios

| Princípio | Descrição |
|-----------|-----------|
| **Objetividade** | Relatar apenas o que é observável diretamente. |
| **Fidelidade** | Descrição sem informações sem evidência observável. |
| **Clareza** | Linguagem objetiva, livre de ambiguidade e sem juízo de valor. |
| **Consistência** | Uso uniforme de termos e estrutura em todo o documento. |
| **Reprodutibilidade** | Descritores independentes chegam a resultados equivalentes (≥ 85%). |
| **Neutralidade** | Não expressar opinião ou preferência pessoal na descrição. |

### 4.3 Termos Operacionais

| Termo | Definição Resumida |
|-------|-------------------|
| **Escopo** (Scope) | Delimitação do tipo de conteúdo ao qual se aplicam as regras. |
| **Diretriz** (Guideline) | Regra qualitativa que orienta a elaboração de descrições. |
| **Evidência** (Evidence) | Dado observável que sustenta uma afirmação na descrição. |
| **Perfil** (Profile) | Conjunto de critérios específicos para um tipo de conteúdo ou cenário. |
| **Extensão** (Extension) | Mecanismo pelo qual novos perfis adicionam critérios. |
| **Rastreabilidade** (Traceability) | Capacidade de rastrear cada critério por seu identificador permanente. |

> **Convenção de Nomenclatura**: Campos de metadata JSON utilizam nomenclatura em inglês (`description`, `license`, `imageType`, etc.) independentemente do idioma da documentação.

---

## 5. Famílias de Conteúdo

| Família | Título | Descrição | Caminho |
|---------|--------|-----------|---------|
| **100** | Terminologia e Princípios Fundamentais | Glossário, princípios e taxonomia | [ACESSILIA-100.md](ACESSILIA-100.md) |
| **200** | Descrição de Imagens Estáticas | JPEG, PNG, SVG, GIF, TIFF, WebP | [families/200/](families/200/ACESSILIA%E2%80%91200.md) |
| **300** | Gráficos, Tabelas e Diagramas | Representações visuais de dados | [families/300/](families/300/ACESSILIA%E2%80%91300.md) |
| **400** | Conteúdo Científico | Artigos, teses, relatórios técnicos | [families/400/](families/400/ACESSILIA%E2%80%91400.md) |
| **500** | Conteúdo Educacional | Materiais didáticos e recursos pedagógicos | [families/500/](families/500/ACESSILIA%E2%80%91500.md) |
| **600** | Conteúdo Multimídia | Vídeos, animações, podcasts | [families/600/](families/600/ACESSILIA%E2%80%91600.md) |
| **700** | Validação e Conformidade | Métricas e procedimentos de validação | [families/700/](families/700/ACESSILIA%E2%80%91700.md) |
| **800** | Perfis de Acessibilidade e Conformidade | Níveis de conformidade e extensões | [families/800/](families/800/ACESSILIA%E2%80%91800.md) |

### 5.1 Dependências entre Famílias

```
100 (base obrigatória)
 ├── 200 (imagens)
 ├── 300 (gráficos)
 ├── 400 (científico)
 ├── 500 (educacional)
 ├── 600 (multimídia)
 ├── 700 (validação) ──── requer 100, 200-600
 └── 800 (perfis) ─────── requer 100, 200-700
```

---

## 6. Níveis de Conformidade

| Nível | Escopo | Descrição |
|-------|--------|-----------|
| **ACESSILIA-A** | Básico | Todos os critérios obrigatórios das famílias 200-700. |
| **ACESSILIA-AA** | Intermediário | Critérios obrigatórios + critérios de importância alta de todas as famílias. |
| **ACESSILIA-AAA** | Avançado | Todos os critérios (obrigatórios e recomendados) de todas as famílias. |

### 6.1 Requisitos por Nível

| Nível | Fam. 200 | Fam. 300 | Fam. 400 | Fam. 500 | Fam. 600 | Fam. 700 |
|-------|----------|----------|----------|----------|----------|----------|
| **A** | Obrigatórios | Obrigatórios | Obrigatórios | Obrigatórios | Obrigatórios | Obrigatórios |
| **AA** | Obr. + Alta | Obr. + Alta | Obr. + Alta | Obr. + Alta | Obr. + Alta | Obr. + Alta |
| **AAA** | Todos | Todos | Todos | Todos | Todos | Todos |

### 6.2 Mapeamento com WCAG 2.2

| Nível ACESSILIA | WCAG 2.2 | EPUB Accessibility | PDF/UA-1 | EN 301 549 | Section 508 |
|-----------------|----------|-------------------|----------|------------|-------------|
| **A** | Level A | WCAG Level A conformance | Seções 7.1-7.5 básicos | Cláusulas 5-6 | E205.3–E205.4 |
| **AA** | Level AA | WCAG Level AA conformance | Conformidade completa | Cláusulas 5-9 | E205.3–E205.4, E205.7 |
| **AAA** | Level AAA | WCAG Level AAA conformance | Excedente | Cláusulas 5-12 | Excedente |

> Implementações que não atendam integralmente ao nível declarado **NÃO DEVEM** declarar conformidade.

### 6.3 Conformidade Parcial

Implementações que não alcancem a totalidade dos critérios para o nível pretendido **NÃO DEVEM** declarar conformidade global (ex.: "conforme ACESSILIA-AA"). Podem, contudo, informar os critérios implementados e aprovados individualmente (ex.: "atende a ACL-200-IMG-001 a ACL-200-IMG-006") para fins de avaliação e relatório técnico de auditoria.

## 7. Identificadores Permanentes

Os identificadores seguem o padrão `ACL-<FAMÍLIA>-<TIPO>-<NÚMERO>`:

| Família | Padrão | Exemplo |
|---------|--------|---------|
| 100 | `ACL-100-T-NNN` | `ACL-100-T001` |
| 200 | `ACL-200-IMG-NNN` | `ACL-200-IMG-001` |
| 300 | `ACL-300-GRF-NNN` | `ACL-300-GRF-001` |
| 400 | `ACL-400-SCI-NNN` | `ACL-400-SCI-001` |
| 500 | `ACL-500-EDU-NNN` | `ACL-500-EDU-001` |
| 600 | `ACL-600-MDM-NNN` | `ACL-600-MDM-001` |
| 700 | `ACL-700-VAL-NNN` | `ACL-700-VAL-001` |
| 800 (Critérios) | `ACL-800-CRT-NNN` | `ACL-800-CRT-001` |
| 800 (Perfis) | `ACL-800-PRF-NNN` | `ACL-800-PRF-001` |

> Estes IDs são **fixos** e não mudam entre versões. A Família 800 adota `CRT` para critérios de validação e `PRF` para perfis de acessibilidade, evitando colisão de identificadores.

---

## 8. Como Começar

### 8.1 Para Descritores

1. Leia [ACESSILIA-Base](ACESSILIA-Base.md) para entender a arquitetura.
2. Estude [ACESSILIA-100](ACESSILIA-100.md) para dominar terminologia e princípios.
3. Consulte a família correspondente ao tipo de conteúdo que você irá descrever.
4. Siga os critérios obrigatórios e gere metadata em JSON.
5. Valide com `acessilia-lint` antes de submeter.

### 8.2 Para Implementadores

1. Implemente validação de esquema com `schemas/acessilia.schema.json`.
2. Integre `acessilia-lint` no seu fluxo de CI/CD.
3. Gere relatórios de conformidade para cada família.
4. Declare o nível de conformidade (A, AA ou AAA) nos metadata.

### 8.3 Para Revisores

1. Use a [Família 700](families/700/ACESSILIA%E2%80%91700.md) como referência para métricas de qualidade.
2. Aplique revisão humana para critérios de importância alta.
3. Documente discordâncias e resoluções no relatório.

---

## 9. Validação e Ferramentas

### 9.1 acessilia-lint

O `acessilia-lint` é a ferramenta oficial de validação automatizada:

```bash
# Validar todas as famílias
acessilia-lint \
  --schema schemas/acessilia.schema.json \
  --dir ./families \
  --output relatorio-conformidade.md

# Validar uma família específica
acessilia-lint \
  --schema schemas/acessilia.schema.json \
  --dir ./families/200 \
  --output relatorio-familia200.md

# Validação com modo verboso
acessilia-lint \
  --schema schemas/acessilia.schema.json \
  --dir ./families \
  --verbose \
  --output relatorio-detalhado.md
```

### 9.2 Integração em CI (GitHub Actions)

```yaml
# .github/workflows/acessilia-lint.yml
name: ACESSILIA Lint
on: [push, pull_request]
jobs:
  lint:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v4
      - name: Setup Node.js
        uses: actions/setup-node@v4
        with:
          node-version: '20'
      - name: Run ACESSILIA Lint
        run: |
          chmod +x scripts/lint_demo.sh
          ./scripts/lint_demo.sh ./families ./schemas/acessilia.schema.json ./relatorio-conformidade.md
      - name: Upload Report
        uses: actions/upload-artifact@v4
        with:
          name: acessilia-report
          path: relatorio-conformidade.md
```

### 9.3 Formato do Relatório

O relatório gerado **DEVE** seguir o formato:

```markdown
# Relatório de Conformidade ACESSILIA

**Data**: YYYY-MM-DD
**Versão do padrão**: X.Y.Z
**Famílias analisadas**: 200, 300, 400, 500, 600, 700

## Resumo

| Família | Total de Critérios | PASS | FAIL | WARN |
|---------|-------------------|------|------|------|
| 200 | 7 | 7 | 0 | 0 |
| ... | ... | ... | ... | ... |

## Detalhes por Família

### Família 200 - Imagens Estáticas

| Critério | Resultado | Observação |
|----------|-----------|------------|
| ACL-200-IMG-001 | PASS | Verbos observáveis detectados. |
| ... | ... | ... |
```

### 9.4 Scripts de Demo

- **PowerShell**: [scripts/lint_demo.ps1](scripts/lint_demo.ps1)
- **Bash**: [scripts/lint_demo.sh](scripts/lint_demo.sh)

---

## 10. Conformidade com Padrões Externos

| Padrão / Norma | Escopo Técnico | Família(s) Aplicável(is) |
|-----------------|----------------|--------------------------|
| [ABNT NBR 17225:2025](https://www.abntcatalogo.com.br/) | Norma Brasileira de Acessibilidade em Conteúdo e Aplicações Web (LBI Art. 63 / ABNT CB-040) | 100, 200, 300, 400, 500, 600, 700 |
| [ABNT NBR 17060:2022](https://www.abntcatalogo.com.br/) | Acessibilidade em aplicações móveis e interfaces digitais | 200, 300, 600 |
| [ABNT NBR 14724 / 10520 / 6027](https://www.abntcatalogo.com.br/) | Trabalhos acadêmicos, citações em bloco e estruturação de sumários | 400, 500, 800 |
| [Manual REBECA 2025](https://repositorio.unb.br/bitstream/10482/52961/1/REBECA_ManualPadronizacao.pdf) | Padronização documental universitária e audiodescrição didática (ADD) | 100, 400, 500, 600, 800 |
| [WCAG 2.2](https://www.w3.org/TR/WCAG22/) / [ISO/IEC 40500](https://www.iso.org/standard/57363.html) | Diretrizes de Acessibilidade para Conteúdo Web (W3C / ISO) | 200, 300, 400, 500, 600, 700 |
| [WAI-ARIA 1.2](https://www.w3.org/TR/wai-aria-1.2/) / [DPUB-ARIA 1.1](https://www.w3.org/TR/dpub-aria-1.1/) | Semântica estrutural, aplicações interativas e papéis editoriais | 200, 300, 600, 800 |
| [DIAGRAM Center Guidelines](http://diagramcenter.org/) | Diretrizes especializadas para descrição de imagens e gráficos complexos (STEM) | 200, 300, 400, 500 |
| [BANA Tactile Graphics / Nemeth](http://www.brailleauthority.org/) | Diretrizes para gráficos táteis, notação matemática e científica acessível | 300, 400, 500 |
| [HTML-AAM / Core-AAM](https://www.w3.org/TR/html-aam-1.0/) | Mapeamento de elementos e acessibilidade de navegadores | 200, 300 |
| [PDF/UA-1 (ISO 14289-1)](https://www.iso.org/standard/64599.html) / [PDF/UA-2 (ISO 14289-2)](https://www.iso.org/standard/82216.html) | Universal Accessibility em formato PDF (estrutura, tags e leitura linear) | 200, 300, 400, 500, 800 |
| [Matterhorn Protocol 1.1](https://www.pdfa.org/resource/matterhorn-protocol-1-1/) | Modelo de testes e catálogo de falhas para validação de PDF/UA | 700, 800 |
| [EPUB 3.3](https://www.w3.org/TR/epub-33/) / [EPUB Accessibility 1.1 (ISO/IEC 23761)](https://www.iso.org/standard/84542.html) | Publicações e livros digitais estruturados e acessíveis | 200, 300, 400, 500, 800 |
| [DAISY 3 (ANSI/NISO Z39.86)](https://daisy.org/activities/standards/daisy/daisy-3/) / [MECDAISY (Nota Técnica nº 21/MEC)](http://portal.mec.gov.br/) | Áudio digital sincronizado e publicações multimídia estruturadas | 600, 800 |
| [ISO 9241-171](https://www.iso.org/standard/39080.html) | Ergonomia da interação humano-sistema — Acessibilidade de software e documentos | 200, 300, 700 |
| [ISO/IEC Guide 71](https://www.iso.org/standard/57385.html) / [ABNT ISO/IEC Guia 71](https://www.abntcatalogo.com.br/) | Guia para integração de acessibilidade em normas e projetos | 100, 700, 800 |
| [EN 301 549 v3.2.1](https://www.etsi.org/deliver/etsi_en/301500_301599/301549/03.02.01_60/en_301549v030201p.pdf) | Requisitos europeus de TIC acessível | Todas |
| [Section 508](https://www.section508.gov/) | Requisitos de acessibilidade governamental (EUA) | Todas |
| [ADLAB PRO](https://www.adlabproject.eu/) | Diretrizes de formação e prática de audiodescrição | 600 |

---

## 11. Estrutura do Repositório

```
ACESSILIA/
├── ACESSILIA-Base.md          # Arquitetura central e versionamento
├── ACESSILIA-100.md           # Terminologia e princípios fundamentais
├── ACESSILIA-Index.md         # Índice de navegação
├── ACESSILIA_SPEC_CH01.txt    # Especificação técnica original (draft)
├── TERMINOLOGY_GUIDE.md       # Guia de terminologia
├── manifest.yml               # Catálogo de famílias
├── schemas/
│   ├── acessilia.schema.json  # Esquema JSON para validação
│   ├── acessilia.xsd          # Esquema XSD
│   └── elementTypes.schema.json
├── scripts/
│   ├── lint_demo.ps1          # Script PowerShell de demo
│   └── lint_demo.sh           # Script Bash de demo
└── families/
    ├── 200/
    │   └── ACESSILIA-200.md   # Imagens estáticas
    ├── 300/
    │   └── ACESSILIA-300.md   # Gráficos, tabelas e diagramas
    ├── 400/
    │   └── ACESSILIA-400.md   # Conteúdo científico
    ├── 500/
    │   └── ACESSILIA-500.md   # Conteúdo educacional
    ├── 600/
    │   └── ACESSILIA-600.md   # Conteúdo multimídia
    ├── 700/
    │   └── ACESSILIA-700.md   # Validação e conformidade
    └── 800/
        ├── ACESSILIA-800.md   # Perfis de acessibilidade
        └── ACESSILIA-800.yml  # Perfis definidos em formato YAML
```

---

## 12. Fluxo de Revisão

```
Draft -> Working Draft -> Candidate Recommendation -> Recommendation
```

| Fase | Descrição |
|------|-----------|
| **Draft** | Proposta não oficial. |
| **Working Draft** | Revisão interna pelo comitê técnico. |
| **Candidate Recommendation** | Comentários de stakeholders externos. |
| **Recommendation** | Apto para publicação oficial. |

### 12.1 Versionamento

| Categoria | Descrição | Exemplo |
|-----------|-----------|---------|
| **MAJOR** | Mudança de estrutura ou introdução de nova família. | Adição de nova família (ex.: família 900 quando disponível). |
| **MINOR** | Adição ou alteração de critério dentro de uma família. | Novo critério `ACL-200-IMG-008`. |
| **PATCH** | Correção editorial ou pequenas melhorias de redação. | Correção de tipografia. |

---

## 13. Contribuindo

1. Abra uma issue no repositório para discutir a proposta.
2. Fork o repositório e crie uma branch para sua alteração.
3. Siga as convenções de terminologia do [TERMINOLOGY_GUIDE.md](TERMINOLOGY_GUIDE.md).
4. Execute `acessilia-lint` para verificar conformidade.
5. Envie um Pull Request com descrição clara da alteração.

> Para sugestões de terminologia, consulte a seção [1.2 Termos Preferidos vs. Depreciados](TERMINOLOGY_GUIDE.md#12-preferred-vs-deprecated-terms) do Guia de Terminologia.

---

## 14. Licença

Este documento pode ser utilizado gratuitamente para implementação, pesquisa e ensino, mantendo referência ao projeto ACESSILIA.

---

## 15. Contato

Para sugestões, abra uma issue no repositório ou contate o comitê técnico ACESSILIA.
