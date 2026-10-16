# ACESSILIA‑800 – Perfis de Acessibilidade e Conformidade

> **Família 800** · Identificador de família: `ACL-800`  
> **RFC 2119**: Os termos **DEVE**, **NÃO DEVE**, **PODE** e **RECOMENDA‑SE** devem ser interpretados conforme [RFC 2119](https://tools.ietf.org/html/rfc2119) e [RFC 8174](https://tools.ietf.org/html/rfc8174).

## 1. Escopo
Define níveis de conformidade, perfis de acessibilidade e mecanismos de extensão do padrão ACESSILIA. Estabelece como implementações devem declarar conformidade e como novos perfis podem ser criados.

## 2. Referências de Norma
Conforme [ACESSILIA‑100](../../ACESSILIA-100.md) para princípios de terminologia e auditabilidade. Em adição ao [WCAG 2.2](https://www.w3.org/TR/WCAG22/), [ABNT NBR 17225:2025](https://www.abntcatalogo.com.br/) (Acessibilidade Web), [EPUB Accessibility 1.1 (ISO/IEC 23761)](https://www.iso.org/standard/84542.html), [DPUB-ARIA 1.1](https://www.w3.org/TR/dpub-aria-1.1/), [PDF/UA‑1/2 (ISO 14289-1 e ISO 14289-2)](https://www.iso.org/standard/64599.html), [Matterhorn Protocol 1.1](https://www.pdfa.org/resource/matterhorn-protocol-1-1/), [DAISY 3 (ANSI/NISO Z39.86)](https://daisy.org/), [EN 301 549 v3.2.1](https://www.etsi.org/deliver/etsi_en/301500_301599/301549/03.02.01_60/en_301549v030201p.pdf) e [Section 508](https://www.section508.gov/) para requisitos de acessibilidade. Referencia [ACESSILIA‑700](../700/ACESSILIA‑700.md) para critérios de validação.

## 3. Diretrizes Principais

| Código | Diretriz | Métrica de Avaliação | Comentário |
|--------|----------|----------------------|------------|
| ACL‑800‑CRT‑001 | **Conformidade** | Nível de conformidade declarado (A, AA ou AAA). | Campo `conformanceLevel` no metadata. |
| ACL‑800‑CRT‑002 | **Famílias** | Lista de famílias aplicáveis. | Campo `families` no metadata. |
| ACL‑800‑CRT‑003 | **Tipos MIME** | Pelo menos 1 tipo MIME válido. | Campo `mediaTypes` no metadata. |
| ACL‑800‑CRT‑004 | **Metadata** | Lista de campos obrigatórios. | Campo `requiredMetadata` no metadata. |
| ACL‑800‑CRT‑005 | **Extensões** | Documentação de critérios adicionais. | Quando o perfil adicionar critérios além das famílias. |

## 4. Níveis de Conformidade

### 4.1 Definição dos Níveis

| Nível | Escopo | Descrição |
|-------|--------|-----------|
| **ACESSILIA‑A** | Básico | Todos os critérios obrigatórios das famílias 200–700. |
| **ACESSILIA‑AA** | Intermediário | Critérios obrigatórios + critérios de importância alta de todas as famílias. |
| **ACESSILIA‑AAA** | Avançado | Todos os critérios (obrigatórios e recomendados) de todas as famílias. |

### 4.2 Requisitos por Nível

| Nível | Família 200 | Família 300 | Família 400 | Família 500 | Família 600 | Família 700 |
|-------|-------------|-------------|-------------|-------------|-------------|-------------|
| **A** | Obrigatórios | Obrigatórios | Obrigatórios | Obrigatórios | Obrigatórios | Obrigatórios |
| **AA** | Obrigatórios + Alta | Obrigatórios + Alta | Obrigatórios + Alta | Obrigatórios + Alta | Obrigatórios + Alta | Obrigatórios + Alta |
| **AAA** | Todos | Todos | Todos | Todos | Todos | Todos |

### 4.3 Mapeamento com Padrões Externos

| Nível ACESSILIA | WCAG 2.2 / ABNT NBR 17225 | EPUB Accessibility (ISO/IEC 23761) | PDF/UA (ISO 14289) | Manual REBECA 2025 | EN 301 549 | Section 508 |
|---|---|---|---|---|---|---|
| **ACESSILIA‑A** | Nível A | WCAG Level A conformance | §7.1–7.5 básicos | Requisitos essenciais de transcrição | Cláusulas 5–6 | E205.3–E205.4 |
| **ACESSILIA‑AA** | Nível AA | WCAG Level AA conformance | Conformidade completa | Padrão REBECA completo (Perfil ACL-800-PRF-007) | Cláusulas 5–9 | E205.3–E205.4, E205.7 |
| **ACESSILIA‑AAA** | Nível AAA | WCAG Level AAA conformance | Excedente | Padrão REBECA avançado com recursos ampliados | Cláusulas 5–12 | Excedente |


### 4.4 Mapeamento Detalhado ACESSILIA → WCAG 2.2

A tabela a seguir mapeia critérios específicos do ACESSILIA com as Success Criteria (SC) do WCAG 2.2 correspondentes, facilitando a rastreabilidade e auditoria de conformidade.

| Critério ACESSILIA | Família | WCAG 2.2 SC | Nível WCAG | Descrição |
|---------------------|---------|-------------|------------|-----------|
| ACL‑200‑IMG‑001 | 200 | 1.1.1 Non-text Content | A | Descrição de imagens estáticas |
| ACL‑200‑IMG‑002 | 200 | 1.1.1 Non-text Content | A | Inferência de emoções sem evidência |
| ACL‑200‑IMG‑003 | 200 | 3.1.5 Reading Level | AAA | Voz ativa em descrições |
| ACL‑200‑IMG‑004 | 200 | 1.3.2 Meaningful Sequence | A | Ordem espacial consistente |
| ACL‑200‑IMG‑005 | 200 | N/A | N/A | Privacidade de dados pessoais (requisito ACESSILIA específico, sem equivalente WCAG direto) |
| ACL‑200‑IMG‑006 | 200 | N/A | N/A | Licenciamento de imagens (requisito ACESSILIA específico, sem equivalente WCAG direto) |
| ACL‑200‑IMG‑007 | 200 | 1.4.3 Contrast (Minimum) | AA | Contraste de luminância |
| ACL‑300‑GRF‑001 | 300 | 1.1.1 Non-text Content | A | Fonte de dados em gráficos |
| ACL‑300‑GRF‑002 | 300 | 1.1.1 Non-text Content | A | Legendas de eixos e rótulos |
| ACL‑300‑GRF‑003 | 300 | 1.3.1 Info and Relationships | A | Tendências sem dados explícitos |
| ACL‑300‑GRF‑004 | 300 | 1.3.2 Meaningful Sequence | A | Ordem lógica de leitura |
| ACL‑300‑GRF‑005 | 300 | 1.4.1 Use of Color | A | Contraste de cores com significado |
| ACL‑400‑SCI‑001 | 400 | 1.3.1 Info and Relationships | A | Resultados objetivos |
| ACL‑400‑SCI‑002 | 400 | 2.4.4 Link Purpose (In Context) | A | Referências com DOI/URL |
| ACL‑400‑SCI‑003 | 400 | 2.4.4 Link Purpose (In Context) | A | Acesso direto a dados |
| ACL‑400‑SCI‑004 | 400 | 2.4.2 Page Titled | A | Rastreabilidade de publicação |
| ACL‑500‑EDU‑001 | 500 | N/A | N/A | Contexto pedagógico (requisito ACESSILIA específico, sem equivalente WCAG direto) |
| ACL‑500‑EDU‑002 | 500 | 3.1.5 Reading Level | AAA | Objetivos mensuráveis (alinhado com nível de leitura) |
| ACL‑500‑EDU‑003 | 500 | 1.3.2 Meaningful Sequence | A | Progressão lógica |
| ACL‑500‑EDU‑004 | 500 | 1.1.1 Non-text Content | A | Exemplos e contra-exemplos |
| ACL‑600‑MDM‑001 | 600 | 1.2.1 Audio-only and Video-only | A | Descrição de narrativa |
| ACL‑600‑MDM‑002 | 600 | 1.2.2 Captions (Prerecorded) | A | Legendas sincronizadas |
| ACL‑600‑MDM‑003 | 600 | 1.2.5 Audio Description | AA | Áudio descritivo |
| ACL‑600‑MDM‑004 | 600 | 1.2.1 Audio-only and Video-only | A | Marcadores temporais ISO 8601 |
| ACL‑600‑MDM‑005 | 600 | 1.2.1 Audio-only and Video-only | A | Transcrição completa |
| ACL‑700‑VAL‑001 | 700 | 4.1.2 Name, Role, Value | A | Validação de esquema |
| ACL‑700‑VAL‑002 | 700 | 4.1.2 Name, Role, Value | A | Validação de conteúdo |
| ACL‑700‑VAL‑003 | 700 | 4.1.2 Name, Role, Value | A | Auditoria de privacidade |
| ACL‑700‑VAL‑004 | 700 | 1.4.3 Contrast (Minimum) | AA | Teste de contraste |
| ACL‑700‑VAL‑005 | 700 | 1.4.3 Contrast (Minimum) | AA | Conformidade de contraste |
| ACL‑800‑CRT‑001 | 800 | N/A | N/A | Declaração de conformidade |
| ACL‑800‑CRT‑002 | 800 | N/A | N/A | Lista de famílias |
| ACL‑800‑CRT‑003 | 800 | N/A | N/A | Tipos MIME |
| ACL‑800‑CRT‑004 | 800 | N/A | N/A | Metadata obrigatórios |
| ACL‑800‑CRT‑005 | 800 | N/A | N/A | Documentação de extensões |

### 4.5 Declaração de Conformidade

Uma implementação **DEVE** atender integralmente aos critérios do nível declarado para usar a designação ACESSILIA‑A, ACESSILIA‑AA ou ACESSILIA‑AAA.

> Implementações que não atendam integralmente ao nível declarado **NÃO DEVEM** declarar conformidade. Podem informar os critérios implementados individualmente para fins de avaliação técnica.

## 5. Perfis de Acessibilidade

### 5.1 Conceito de Perfil

Um perfil de acessibilidade é um conjunto de critérios e requisitos específicos para um tipo de conteúdo ou cenário de uso. Perfis podem restringir ou expandir os requisitos das famílias base.

### 5.2 Perfis Definidos

| Perfil | Identificador | Família(s) Aplicável(is) | Descrição |
|--------|---------------|--------------------------|-----------|
| **Livro Digital** | `ACL-800-PRF-001` | 200, 300, 400, 500 | Requisitos para EPUB e PDF acessíveis. |
| **Fotografia** | `ACL-800-PRF-002` | 200 | Requisitos específicos para descrição de fotografias. |
| **Conteúdo Matemático** | `ACL-800-PRF-003` | 400 | Requisitos para equações e notação matemática. |
| **Gráfico Científico** | `ACL-800-PRF-004` | 300, 400 | Requisitos para gráficos de dados e diagramas científicos. |
| **Captura de Tela** | `ACL-800-PRF-005` | 200 | Requisitos para descrição de interfaces e capturas de tela. |
| **Conteúdo STEM** | `ACL-800-PRF-006` | 300, 400, 500 | Requisitos para ciência, tecnologia, engenharia e matemática. |
| **Documento Acadêmico (REBECA)** | `ACL-800-PRF-007` | 200, 300, 400, 500 | Requisitos do Manual REBECA para adaptação de livros e artigos acadêmicos digitais acessíveis (ABNT, amparo na Lei de Direitos Autorais nº 9.610/1998, ADD e delimitação de descrição). |
| **Documento PDF/UA (ISO 14289)** | `ACL-800-PRF-008` | 200, 300, 400, 500, 700 | Requisitos estritos de acessibilidade universal para PDFs com tags semânticas, linearização e metadados XMP. |
| **Publicação EPUB Acessível (ISO/IEC 23761)** | `ACL-800-PRF-009` | 200, 300, 400, 500, 700 | Requisitos para EPUB 3 conforme W3C EPUB Accessibility 1.1 e metadados schema.org/accessibility. |
| **Áudio Digital e Texto Sincronizado (DAISY / MECDAISY)** | `ACL-800-PRF-010` | 500, 600, 700 | Requisitos para livros falados e multimídia com sincronização temporal SMIL (ANSI/NISO Z39.86 e MECDAISY). |

### 5.3 Estrutura de um Perfil

Cada perfil **DEVE** conter:

| Campo | Tipo | Obrigatório | Descrição |
|-------|------|-------------|-----------|
| `id` | string | Sim | Identificador único do perfil (ex.: `ACL-800-PRF-001`). |
| `name` | string | Sim | Nome do perfil em inglês. |
| `namePt` | string | Sim | Nome do perfil em português. |
| `description` | string | Sim | Descrição do escopo do perfil. |
| `mediaTypes` | array | Sim | Tipos MIME aplicáveis. |
| `requiredMetadata` | array | Sim | Campos de metadata obrigatórios. |
| `families` | array | Sim | Famílias ACESSILIA aplicáveis. |
| `conformanceLevel` | string | Sim | Nível mínimo de conformidade (A, AA, AAA). |
| `license` | string | Sim | Identificador SPDX ou URL da licença. |
| `criteria` | array | Não | Critérios específicos do perfil (além dos da família). |

## 6. Critérios Obrigatórios (ACL‑800‑CRT‑NNN)

> **Nota**: Perfis usam o prefixo `ACL-800-PRF-`, enquanto critérios de validação usam `ACL-800-CRT-` para evitar colisão de identificadores.

| Identificador | Objetivo | Evidência Obrigatória | Importância | Ponto de Verificação |
|---------------|-----------|------------------------|-------------|-----------------------|
| ACL‑800‑CRT‑001 | Declarar nível de conformidade. | Campo `conformanceLevel` no metadata com valor válido (A, AA ou AAA). | Alta | Presença do campo `conformanceLevel` com valor válido. |
| ACL‑800‑CRT‑002 | Listar famílias aplicáveis. | Campo `families` contendo lista de famílias incluídas no perfil. | Alta | Todas as famílias referenciadas existem no manifesto. |
| ACL‑800‑CRT‑003 | Definir tipos MIME. | Campo `mediaTypes` com pelo menos 1 tipo MIME válido. | Média | Formato MIME válido em todas as entradas. |
| ACL‑800‑CRT‑004 | Especificar metadata obrigatórios. | Campo `requiredMetadata` com lista de campos exigidos. | Média | Campos listados são válidos conforme schema. |
| ACL‑800‑CRT‑005 | Documentar extensões. | Quando o perfil adicionar critérios além das famílias, estes **DEVEM** ser documentados com identificador `ACL-800-PRF-XXX-NNN`. | Alta | Todos os critérios de extensão possuem identificador, evidência e ponto de verificação. |

## 7. Metadados de Exemplo (JSON)

### 7.1 Exemplo de Perfil — Livro Digital

```json
{
  "id": "ACL-800-PRF-001",
  "name": "Accessibility Profile - Livro Digital",
  "namePt": "Perfil de Acessibilidade - Livro Digital",
  "description": "Requisitos para livros digitais acessíveis em EPUB e PDF.",
  "mediaTypes": [
    "application/epub+zip",
    "application/pdf"
  ],
  "requiredMetadata": [
    "title",
    "language",
    "description",
    "conformsTo",
    "accessMode",
    "accessibilityFeature",
    "accessibilitySummary"
  ],
  "families": [200, 300, 400, 500],
  "conformanceLevel": "AA",
  "license": "https://creativecommons.org/licenses/by/4.0/"
}
```

### 7.2 Exemplo de Perfil — Fotografia

```json
{
  "id": "ACL-800-PRF-002",
  "name": "Accessibility Profile - Fotografia",
  "namePt": "Perfil de Acessibilidade - Fotografia",
  "description": "Requisitos específicos para descrição de fotografias e imagens estáticas.",
  "mediaTypes": [
    "image/jpeg",
    "image/png",
    "image/webp"
  ],
  "requiredMetadata": [
    "title",
    "description",
    "imageType",
    "resolution"
  ],
  "families": [200],
  "conformanceLevel": "A",
  "license": "https://creativecommons.org/licenses/by/4.0/"
}
```

### 7.3 Exemplo de Perfil — Conteúdo Matemático

```json
{
  "id": "ACL-800-PRF-003",
  "name": "Accessibility Profile - Conteúdo Matemático",
  "namePt": "Perfil de Acessibilidade - Conteúdo Matemático",
  "description": "Requisitos para equações e notação matemática acessível.",
  "mediaTypes": [
    "application/xhtml+xml",
    "application/pdf"
  ],
  "requiredMetadata": [
    "title",
    "description",
    "language"
  ],
  "families": [400],
  "conformanceLevel": "AA",
  "license": "https://creativecommons.org/licenses/by/4.0/"
}
```

### 7.4 Exemplo de Perfil — Gráfico Científico

```json
{
  "id": "ACL-800-PRF-004",
  "name": "Accessibility Profile - Gráfico Científico",
  "namePt": "Perfil de Acessibilidade - Gráfico Científico",
  "description": "Requisitos para gráficos de dados e diagramas científicos.",
  "mediaTypes": [
    "image/png",
    "image/svg+xml",
    "application/pdf"
  ],
  "requiredMetadata": [
    "title",
    "description",
    "chartType",
    "source",
    "xAxis",
    "yAxis"
  ],
  "families": [300, 400],
  "conformanceLevel": "AA",
  "license": "https://creativecommons.org/licenses/by/4.0/"
}
```

### 7.5 Exemplo de Perfil — Captura de Tela

```json
{
  "id": "ACL-800-PRF-005",
  "name": "Accessibility Profile - Captura de Tela",
  "namePt": "Perfil de Acessibilidade - Captura de Tela",
  "description": "Requisitos para descrição de interfaces e capturas de tela.",
  "mediaTypes": [
    "image/png",
    "image/jpeg"
  ],
  "requiredMetadata": [
    "title",
    "description",
    "imageType",
    "resolution"
  ],
  "families": [200],
  "conformanceLevel": "A",
  "license": "https://creativecommons.org/licenses/by/4.0/"
}
```

### 7.6 Exemplo de Perfil — Conteúdo STEM

```json
{
  "id": "ACL-800-PRF-006",
  "name": "Accessibility Profile - Conteúdo STEM",
  "namePt": "Perfil de Acessibilidade - Conteúdo STEM",
  "description": "Requisitos para ciência, tecnologia, engenharia e matemática.",
  "mediaTypes": [
    "application/xhtml+xml",
    "application/pdf",
    "image/png",
    "image/svg+xml"
  ],
  "requiredMetadata": [
    "title",
    "description",
    "language",
    "chartType",
    "source",
    "educationalContext"
  ],
  "families": [300, 400, 500],
  "conformanceLevel": "AA",
  "license": "https://creativecommons.org/licenses/by/4.0/"
}
```

### 7.7 Exemplo de Perfil — Documento Acadêmico Acessível (Padrão REBECA)

```json
{
  "id": "ACL-800-PRF-007",
  "name": "Accessibility Profile - Academic Accessible Document (REBECA)",
  "namePt": "Perfil de Acessibilidade - Documento Acadêmico Acessível (REBECA)",
  "description": "Requisitos baseados no Manual de Padronização REBECA para adaptação documental de livros, artigos, capítulos e teses acadêmicas.",
  "mediaTypes": [
    "application/vnd.openxmlformats-officedocument.wordprocessingml.document",
    "application/pdf",
    "text/html"
  ],
  "requiredMetadata": [
    "title",
    "description",
    "language",
    "standard",
    "legalNotice",
    "adaptingInstitution",
    "namingConvention",
    "descriptionDelimiters"
  ],
  "families": [200, 300, 400, 500],
  "conformanceLevel": "AA",
  "license": "https://creativecommons.org/licenses/by-nc-nd/4.0/",
  "criteria": [
    {
      "id": "ACL-800-PRF-REB-001",
      "name": "Cabeçalho de Amparo Legal",
      "requirement": "Documento DEVE explicitar citação bibliográfica, setor/instituição adaptadora e menção ao Art. 46 da Lei 9.610/1998."
    },
    {
      "id": "ACL-800-PRF-REB-002",
      "name": "Delimitação de Audiodescrição",
      "requirement": "Toda audiodescrição DEVE ser precedida por '[Início da descrição]' e sucedida por '[Fim da descrição]'."
    },
    {
      "id": "ACL-800-PRF-REB-003",
      "name": "Nomenclatura Padronizada de Arquivo",
      "requirement": "O arquivo DEVE seguir o padrão: [SOBRENOME]_[PrimeiraPalavraTitulo]_[RADICAL] (ex.: SILVA_Historia_LIVR)."
    }
  ]
}
```

### 7.8 Exemplo de Perfil — Documento PDF/UA (ISO 14289)

```json
{
  "id": "ACL-800-PRF-008",
  "name": "Accessibility Profile - PDF/UA Universal Accessibility (ISO 14289)",
  "namePt": "Perfil de Acessibilidade - Documento PDF/UA (ISO 14289)",
  "description": "Requisitos de acessibilidade universal para documentos PDF taggeados, linearizados e conformes com ISO 14289-1 e ISO 14289-2.",
  "mediaTypes": [
    "application/pdf"
  ],
  "requiredMetadata": [
    "title",
    "description",
    "language",
    "conformsTo",
    "accessMode",
    "accessibilityFeature",
    "accessibilitySummary"
  ],
  "families": [200, 300, 400, 500, 700],
  "conformanceLevel": "AA",
  "license": "https://creativecommons.org/licenses/by/4.0/"
}
```

### 7.9 Exemplo de Perfil — Publicação EPUB Acessível (ISO/IEC 23761)

```json
{
  "id": "ACL-800-PRF-009",
  "name": "Accessibility Profile - Accessible EPUB Publication (ISO/IEC 23761)",
  "namePt": "Perfil de Acessibilidade - Publicação EPUB Acessível (ISO/IEC 23761)",
  "description": "Requisitos para publicações digitais EPUB 3 em conformidade com a especificação W3C EPUB Accessibility 1.1 e ISO/IEC 23761.",
  "mediaTypes": [
    "application/epub+zip"
  ],
  "requiredMetadata": [
    "title",
    "description",
    "language",
    "conformsTo",
    "accessMode",
    "accessModeSufficient",
    "accessibilityFeature",
    "accessibilityHazard",
    "accessibilitySummary"
  ],
  "families": [200, 300, 400, 500, 700],
  "conformanceLevel": "AA",
  "license": "https://creativecommons.org/licenses/by/4.0/"
}
```

### 7.10 Exemplo de Perfil — Áudio Digital e Texto Sincronizado (DAISY / MECDAISY)

```json
{
  "id": "ACL-800-PRF-010",
  "name": "Accessibility Profile - Synchronized Digital Audio and Text (DAISY / MECDAISY)",
  "namePt": "Perfil de Acessibilidade - Áudio Digital e Texto Sincronizado (DAISY / MECDAISY)",
  "description": "Requisitos para livros falados e materiais educacionais com sincronização temporal multimodal SMIL (ANSI/NISO Z39.86 e MECDAISY).",
  "mediaTypes": [
    "application/x-dtbook+xml",
    "audio/mpeg",
    "application/smil+xml"
  ],
  "requiredMetadata": [
    "title",
    "description",
    "language",
    "duration",
    "mediaType",
    "transcript",
    "audioDescription"
  ],
  "families": [500, 600, 700],
  "conformanceLevel": "AA",
  "license": "https://creativecommons.org/licenses/by/4.0/"
}
```

## 8. Exemplos de Conformidade

| Exemplo | Justificativa |
|---------|-----------|
| **Conforme** – Implementação declarando `conformanceLevel: "AA"` e atendendo a todos os critérios obrigatórios e de alta importância das famílias 200–600. | Declaração válida com conformidade verificável. |
| **Não conforme** – Implementação declarando `conformanceLevel: "AAA"` mas sem documentar critérios de extensão. `[viola ACL‑800‑CRT‑005]` | Nível declarado sem suporte documentado. |
| **Não conforme** – Implementação declarando `conformanceLevel: "AA"` mas sem campo `conformanceLevel` no metadata. `[viola ACL‑800‑CRT‑001]` | Falta declaração obrigatória. |

## 9. Estratégia de Validação

1. **Validação de esquema**: garantir que todos os campos obrigatórios do perfil estejam presentes.
2. **Validação de nível**: o linter **DEVE** verificar se o nível declarado corresponde aos critérios atendidos.
3. **Validação de famílias**: o linter **DEVE** verificar se todas as famílias referenciadas existem no manifesto.
4. **Validação de extensões**: quando o perfil adicionar critérios, o linter **DEVE** verificar se possuem identificador válido e evidência documentada.

## 10. Exemplo de Execução do Lint

```bash
acessilia-lint \
  --schema schemas/acessilia.schema.json \
  --dir ./families/800 \
  --output relatorio-familia800.md
```

O relatório gerado **DEVE** indicar `PASS` ou `FAIL` para cada critério listado na Seção 6 (prefixo `ACL‑800‑CRT‑`).

## 11. Limitações e Exclusões

Esta família define perfis de conformidade e mecanismos de extensão. Os seguintes tipos de conteúdo **NÃO DEVEM** ser descritos usando apenas esta família:

- **Conteúdo específico** → usar a família correspondente (200–600) para descrição do conteúdo.
- **Validação de conteúdo** → usar [ACESSILIA‑700](../700/ACESSILIA‑700.md) para critérios de validação.

A criação de novos perfis **DEVE** ser documentada e revisada pelo comitê técnico antes da publicação.

## 12. Modelo de Extensão

O padrão ACESSILIA pode ser estendido por perfis específicos. O processo de extensão **DEVE** seguir:

1. **Proposta**: Documento descrevendo o novo perfil, seu escopo e critérios.
2. **Revisão**: Análise pelo comitê técnico e stakeholders.
3. **Publicação**: Inclusão no catálogo de perfis com identificador `ACL-800-PRF-XXX`.

Perfis existentes podem ser referenciados por implementações que desejem atender a requisitos específicos além das famílias base.
