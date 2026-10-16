# ACESSILIA – Sistema Brasileiro de Normas de Acessibilidade Digital e Descrição Semântica
## Índice de Navegação

> **Versão**: 1.1.0 · **Data**: 2026-07-16  
> **RFC 2119/8174**: Todos os termos **DEVE**, **NÃO DEVE**, **PODE** e **RECOMENDA‑SE** seguem [RFC 2119](https://tools.ietf.org/html/rfc2119) e [RFC 8174](https://tools.ietf.org/html/rfc8174).

## Documentos Centrais

| Documento | Descrição | Caminho |
|-----------|-----------|---------|
| **ACESSILIA‑Base** | Arquitetura central, versionamento e fluxo de revisões | [ACESSILIA‑Base.md](ACESSILIA-Base.md) |
| **ACESSILIA‑100** | Terminologia, princípios fundamentais e glossário | [ACESSILIA-100.md](ACESSILIA-100.md) |
| **ACESSILIA‑Index** | Este índice de navegação | [ACESSILIA‑Index.md](ACESSILIA-Index.md) |

## Famílias de Conteúdo

| Família | Título | Identificador | Caminho | Requer |
|---------|--------|---------------|---------|--------|
| **200** | Descrição de Imagens Estáticas | `ACL-200` | [families/200/ACESSILIA‑200.md](families/200/ACESSILIA‑200.md) | 100 |
| **300** | Gráficos, Tabelas e Diagramas | `ACL-300` | [families/300/ACESSILIA‑300.md](families/300/ACESSILIA‑300.md) | 100 |
| **400** | Conteúdo Científico | `ACL-400` | [families/400/ACESSILIA‑400.md](families/400/ACESSILIA‑400.md) | 100 |
| **500** | Conteúdo Educacional | `ACL-500` | [families/500/ACESSILIA‑500.md](families/500/ACESSILIA‑500.md) | 100 |
| **600** | Conteúdo Multimídia | `ACL-600` | [families/600/ACESSILIA‑600.md](families/600/ACESSILIA‑600.md) | 100 |
| **700** | Validação e Conformidade | `ACL-700` | [families/700/ACESSILIA‑700.md](families/700/ACESSILIA‑700.md) | 100, 200–600 |
| **800** | Perfis de Acessibilidade e Conformidade | `ACL-800` | [families/800/ACESSILIA‑800.md](families/800/ACESSILIA‑800.md) | 100, 200–700 |

## Padrões de Identificadores por Família

| Família | Padrão | Exemplo |
|---------|--------|---------|
| 200 | `ACL‑200‑IMG‑NNN` | `ACL‑200‑IMG‑001` |
| 300 | `ACL‑300‑GRF‑NNN` | `ACL‑300‑GRF‑001` |
| 400 | `ACL‑400‑SCI‑NNN` | `ACL‑400‑SCI‑001` |
| 500 | `ACL‑500‑EDU‑NNN` | `ACL‑500‑EDU‑001` |
| 600 | `ACL‑600‑MDM‑NNN` | `ACL‑600‑MDM‑001` |
| 700 | `ACL‑700‑VAL‑NNN` | `ACL‑700‑VAL‑001` |
| 800 (Critérios) | `ACL‑800‑CRT‑NNN` | `ACL‑800‑CRT‑001` |
| 800 (Perfis) | `ACL‑800‑PRF‑NNN` | `ACL‑800‑PRF‑001` |

## Infraestrutura

| Recurso | Descrição | Caminho |
|---------|-----------|---------|
| **Schema JSON** | Validação de metadata (draft‑07) | [schemas/acessilia.schema.json](schemas/acessilia.schema.json) |
| **Manifesto** | Catálogo de famílias e ordem de importação | [manifest.yml](manifest.yml) |
| **Lint Script (PS)** | Script de validação PowerShell | [scripts/lint_demo.ps1](scripts/lint_demo.ps1) |
| **Lint Script (Bash)** | Script de validação Bash | [scripts/lint_demo.sh](scripts/lint_demo.sh) |

## Conformidade Externa e Padrões Integrados

| Padrão / Norma | Escopo | Família(s) Aplicável(is) |
|----------------|--------|--------------------------|
| [WCAG 2.2](https://www.w3.org/TR/WCAG22/) / [ISO/IEC 40500](https://www.iso.org/standard/57363.html) | Acessibilidade de conteúdo Web (W3C / ISO) | 200, 300, 400, 500, 600, 700 |
| [WAI-ARIA 1.2](https://www.w3.org/TR/wai-aria-1.2/) | Semântica de acessibilidade de aplicações ricas | 200, 300, 600 |
| [HTML-AAM / Core-AAM](https://www.w3.org/TR/html-aam-1.0/) | Acessibilidade e mapeamento estrutural de navegadores | 200, 300 |
| [PDF/UA-1 / PDF/UA-2 (ISO 14289)](https://www.iso.org/standard/64599.html) | Universal Accessibility em formato PDF (tags e semântica) | 200, 300, 400, 500, 800 |
| [EPUB 3.3](https://www.w3.org/TR/epub-33/) / [EPUB Accessibility 1.1 (ISO/IEC 23761)](https://www.iso.org/standard/84542.html) | Publicações e livros digitais estruturados e acessíveis | 200, 300, 400, 500, 800 |
| [DAISY 3 (ANSI/NISO Z39.86)](https://daisy.org/) / [MECDAISY (MEC)](http://portal.mec.gov.br/) | Áudio digital sincronizado e materiais adaptados | 600, 800 |
| [ISO 9241-171](https://www.iso.org/standard/39080.html) | Ergonomia da interação humano-sistema e acessibilidade | 200, 300, 700 |
| [ISO/IEC Guide 71](https://www.iso.org/standard/57385.html) / [ABNT ISO/IEC Guia 71](https://www.abntcatalogo.com.br/) | Integração de requisitos de acessibilidade em padrões | 100, 700, 800 |
| [ABNT NBR 17060 / 14724 / 10520](https://www.abntcatalogo.com.br/) | Acessibilidade em apps móveis, trabalhos e citações | 200, 300, 400, 500, 800 |
| [Manual REBECA 2025](https://repositorio.unb.br/bitstream/10482/52961/1/REBECA_ManualPadronizacao.pdf) | Padronização documental universitária e ADD | 100, 400, 500, 600, 800 |
| [EN 301 549 v3.2.1](https://www.etsi.org/deliver/etsi_en/301500_301599/301549/03.02.01_60/en_301549v030201p.pdf) | Requisitos europeus de TIC | Todas |
| [Section 508](https://www.section508.gov/) | Acessibilidade governamental (EUA) | Todas |
| [ADLAB PRO](https://www.adlabproject.eu/) | Diretrizes de audiodescrição | 600 |

## Fluxo de Revisão

```
Draft → Working Draft → Candidate Recommendation → Recommendation
```

| Fase | Descrição |
|------|-----------|
| **Draft** | Proposta não oficial. |
| **Working Draft** | Revisão interna pelo comitê técnico. |
| **Candidate Recommendation** | Comentários de stakeholders externos. |
| **Recommendation** | Objeto de publicação oficial. |

## Guia de Leitura

Para novos usuários, recomendamos a seguinte ordem de leitura:

1. **ACESSILIA‑Base** – Arquitetura e conceitos gerais
2. **ACESSILIA‑100** – Terminologia e princípios fundamentais
3. **Família(s) de interesse** – Regras específicas para o tipo de conteúdo
4. **Família 700** – Validação e conformidade
5. **Família 800** – Perfis de acessibilidade

## Contato

Para sugestões, abra uma issue no repositório ou contate o comitê técnico ACESSILIA.
