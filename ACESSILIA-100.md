# ACESSILIA‑100 – Terminologia e Princípios Fundamentais

> **RFC 2119**: Os termos **DEVE**, **NÃO DEVE**, **PODE** e **RECOMENDA‑SE** devem ser interpretados conforme [RFC 2119](https://tools.ietf.org/html/rfc2119) e [RFC 8174](https://tools.ietf.org/html/rfc8174).

## Sumário

- [1. Terminologia](#1-terminologia)
- [2. Princípios Fundamentais](#2-princípios-fundamentais)
- [3. Taxonomia de Elementos de Descrição](#3-taxonomia-de-elementos-de-descrição)
- [4. Requisitos de Auditoria](#4-requisitos-de-auditoria)
- [5. Identificadores Permanentes](#5-identificadores-permanentes)
- [6. Glossário](#6-glossário)
- [7. Requisitos Normativos para Sistemas de Inteligência Artificial](#7-requisitos-normativos-para-sistemas-de-inteligência-artificial)
- [8. Não Objetivos](#8-não-objetivos)
- [9. Requisitos de Interoperabilidade Técnica](#9-requisitos-de-interoperabilidade-técnica)

## 1. Terminologia

| Termo | Definição |
|-------|-----------|
| **Objetividade** | A descrição **DEVE** relatar apenas o que pode ser observado diretamente. |
| **Fidelidade** | A descrição **NÃO DEVE** conter informações sem evidência observável. |
| **Clareza** | A linguagem **DEVE** ser objetiva, livre de ambiguidade e sem juízo de valor. |
| **Consistência** | O uso de termos e estrutura **DEVE** ser uniforme em todo o documento. |
| **Reprodutibilidade** | Diferentes descritores independentes **DEVEM** chegar a resultados equivalentes (≥ 85%). |
| **Contextualização** | A descrição **DEVE** adequar-se ao propósito e escopo comunicativo sem distorcer o conteúdo observado. |
| **Ética e Privacidade** | A descrição **NÃO DEVE** expor dados pessoais sem aviso ou perpetuar estereótipos e discriminação. |

## 2. Princípios Fundamentais

Os princípios do ACESSILIA estruturam-se em quatro eixos fundamentais:

| Eixo | Princípio | RFC 2119 Designação | Descrição |
|------|-----------|----------------------|-----------|
| **A) Objetividade** | Neutralidade | DEVE | A descrição **NÃO DEVE** expressar opinião ou preferência pessoal. |
| | Fidelidade | DEVE | A descrição **DEVE** corresponder fielmente ao conteúdo observado e **NÃO DEVE** conter inferências sem evidência. |
| | Verificabilidade | DEVE | Todas as afirmações **DEVEM** ser sustentadas por evidências diretamente observáveis. |
| **B) Clareza** | Clareza | DEVE | A linguagem **DEVE** ser compreensível pelo público-alvo, preferindo frases curtas e voz ativa. |
| | Consistência | DEVE | Termos e estrutura **DEVEM** ser uniformes em todas as famílias. |
| | Reprodutibilidade | DEVE | Resultados equivalentes (≥ 85%) **DEVEM** ser obtidos por descritores independentes. |
| **C) Contexto** | Proporcionalidade | DEVE | A extensão e o nível de detalhe **DEVEM** ser proporcionais à relevância do elemento. |
| | Contextualização | RECOMENDA-SE | O contexto de inserção do conteúdo **DEVE** orientar o foco descritivo sem violar a fidelidade. |
| **D) Ética** | Privacidade | DEVE | Dados pessoais (PII) **DEVEM** ser sinalizados via `privacyNotice` e protegidos. |
| | Não discriminação | DEVE | A descrição **NÃO DEVE** inferir atributos de identidade (raça, gênero, classe, profissão) sem evidência direta. |

### 2.1 Resolução de Conflitos entre Princípios

Em caso de divergência ou tensão entre princípios durante a elaboração ou auditoria da descrição, a seguinte ordem de precedência **DEVE** ser respeitada:

1. **Fidelidade** (relatar estritamente o observado, sem alucinação ou inferência)
2. **Neutralidade** (ausência de juízo de valor, emoções não comprovadas ou viés)
3. **Clareza** (compreensibilidade, concisão e voz ativa)
4. **Contextualização** (adequação pedagógica, científica ou comunicativa)
5. **Estilo** (preferências estéticas de redação)

### 2.2 Hierarquia Normativa de Critérios

A estrutura de especificação e rastreabilidade do padrão segue a hierarquia formal:

```
Princípio > Diretriz > Critério > Método > Técnica > Falha > Exemplo
```

## 3. Taxonomia de Elementos de Descrição

O arquivo **`manifest.yml`** atua como catálogo de famílias e controla a ordem de importação.

| Elemento | Família | Descrição |
|----------|---------|-----------|
| `ImageDescription` | 200 | Descrição de imagens estáticas. |
| `ChartDescription` | 300 | Descrição de gráficos, tabelas e diagramas. |
| `ScientificContent` | 400 | Descrição de conteúdo científico. |
| `EducationalContent` | 500 | Descrição de conteúdo educacional. |
| `MultimediaDescriptor` | 600 | Descrição de conteúdo multimídia. |
| `ValidationConformity` | 700 | Validação e conformidade. |
| `AccessibilityProfile` | 800 | Perfis de acessibilidade e conformidade. |
| `Terminology` | 100 | Identificadores de terminologia e princípios fundamentais. |

## 4. Requisitos de Auditoria

Para garantir a rastreabilidade e a auditabilidade dos requisitos, cada critério recebe um identificador permanente, um índice de importância e um ponto de verificação de validação.

| Identificador | Importância | Ponto de Verificação |
|---------------|-------------|-----------------------|
| ACL‑100‑T001 | Alta | Evidência observável em 100 % das descrições. |
| ACL‑100‑T002 | Alta | Uso de **NÃO DEVE** em todos os documentos para restrições. |
| ACL‑100‑T003 | Média | Ausência de ambiguidades na redação (validação por linter). |
| ACL‑100‑T004 | Alta | Termo consistente em todas as diretrizes (verificação cruzada). |
| ACL‑100‑T005 | Média | Conformidade de métricas de reprodutibilidade (≥ 85%). |
| ACL‑100‑T006 | Alta | Identificador permanente `ACL-<FAMÍLIA>-<TIPO>-<NÚMERO>` em todos os critérios. |
| ACL‑100‑T007 | Média | Referência a RFC 2119 em todos os documentos normativos. |

## 5. Identificadores Permanentes

Os identificadores seguem o padrão `ACL‑<FAMÍLIA>-<TIPO>-<NÚMERO>`. Exemplos:

| Família | Padrão de Identificador | Exemplo |
|---------|-------------------------|---------|
| 200 | `ACL‑200‑IMG‑NNN` | `ACL‑200‑IMG‑001` |
| 300 | `ACL‑300‑GRF‑NNN` | `ACL‑300‑GRF‑001` |
| 400 | `ACL‑400‑SCI‑NNN` | `ACL‑400‑SCI‑001` |
| 500 | `ACL‑500‑EDU‑NNN` | `ACL‑500‑EDU‑001` |
| 600 | `ACL‑600‑MDM‑NNN` | `ACL‑600‑MDM‑001` |
| 700 | `ACL‑700‑VAL‑NNN` | `ACL‑700‑VAL‑001` |
| 800 | `ACL‑800‑PRF‑NNN` (perfis) / `ACL‑800‑CRT‑NNN` (critérios) | `ACL‑800‑PRF‑001`, `ACL‑800‑CRT‑001` |
| 100 | `ACL‑100‑T‑NNN` | `ACL‑100‑T001` |

Estes IDs são **fixos** e não mudam entre versões.

## 6. Glossário

### 6.1 Termos Fundamentais

| Termo | Definição |
|-------|-----------|
| **Objetividade** | Princípio de relatar apenas o que pode ser observado diretamente. |
| **Fidelidade (Princípio)** | Princípio qualitativo: descrição sem informações sem evidência observável. |
| **Fidelidade Semântica (Métrica)** | Métrica quantitativa: percentual de correspondência com o conteúdo original (≥ 90%). |
| **Clareza** | Princípio de linguagem objetiva, livre de ambiguidade e sem juízo de valor. |
| **Consistência** | Princípio de uso uniforme de termos e estrutura em todo o documento. |
| **Reprodutibilidade** | Capacidade de diferentes descritores independentes chegarem a resultados equivalentes (≥ 85%). |
| **Neutralidade** | Princípio de não expressar opinião ou preferência pessoal na descrição. |

### 6.2 Termos Operacionais

| Termo | Definição |
|-------|-----------|
| **Escopo** | Delimitação do tipo de conteúdo ao qual se aplicam as regras de uma família. |
| **Diretriz** | Regra qualitativa que orienta a elaboração de descrições dentro de uma família. |
| **Evidência** | Dado observável que sustenta uma afirmação na descrição. |
| **Evidência Obrigatória** | Dado que **DEVE** estar presente para que o critério seja atendido. |
| **Ponto de Verificação** | Local ou método pelo qual se verifica a conformidade de um critério. |
| **Importância** | Nível de prioridade de um critério (Alta ou Média). |
| **Esquema** | Arquivo JSON ou XSD que define a estrutura obrigatória dos metadata. |
| **Manifesto** | Arquivo `manifest.yml` que lista famílias, ordem de importação e versão. |
| **Módulo** | Arquivo individual de uma família que pode ser incluído em contexto de uso. |
| **Rastreabilidade** | Capacidade de rastrear cada critério por seu identificador permanente. |
| **Conformidade** | Estado de atendimento a todos os critérios obrigatórios aplicáveis. |
| **Relatório de Conformidade** | Documento gerado pelo linter com resultado PASS/FAIL por critério. |
| **Validação** | Processo de verificar se conteúdo e metadata atendem aos requisitos. |
| **Auditoria** | Revisão humana independente para validar conformidade além da validação automática. |
| **Auditabilidade** | Qualidade do processo ou especificação que permite inspeção, verificação independente e validação dos critérios aplicados. |
| **Perfil** | Conjunto de critérios e requisitos específicos para um tipo de conteúdo ou cenário de uso, podendo restringir ou expandir os requisitos das famílias base. |
| **Extensão** | Mecanismo pelo qual novos perfis adicionam critérios além das famílias base, mediante documentação e revisão pelo comitê técnico. |
| **Completude** | Percentual de campos obrigatórios preenchidos no metadata em relação ao total de campos exigidos pelo esquema. |

### 6.3 Termos Técnicos

| Termo | Definição |
|-------|-----------|
| **PII** | *Personally Identifiable Information* — dados pessoais identificáveis. |
| **SPDX** | *Software Package Data Exchange* — padrão para identificação de licenças ([spdx.org](https://spdx.org/specifications)). |
| **Contraste de Luminância** | Razão mínima de luminância entre texto e fundo (≥ 4,5:1 conforme WCAG). |
| **Contraste de Cores** | Uso de cores diferenciadoras com significado textual associado. |
| **Verbo de Bloom** | Verbo de ação mensurável usado na taxonomia de Bloom para objetivos educacionais (Bloom et al., 1956; Anderson & Krathwohl, 2001). |
| **Flesch-Kincaid** | Fórmula de legibilidade que mede a compreensibilidade de textos (Flesch, 1949). Para português: índice equivalente adaptado por Costa (1998). |
| **Legenda (Gráfico)** | Texto que descreve eixos, unidades e elementos de um gráfico ou diagrama. |
| **Legenda (Vídeo)** | Texto sincronizado com o áudio que transcreve falas e sons relevantes em conteúdo multimídia (captions). |
| **Índice de Gunning** | Fórmula alternativa de legibilidade que mede a compreensibilidade de textos; alternativa ao Flesch-Kincaid para validação de Clareza. |
| **AD (Audiodescrição)** | Tradução intersemiótica que transforma o visual em verbal para garantir acesso autônomo ao conteúdo por pessoas cegas ou com baixa visão. |
| **ADD (Audiodescrição Didática)** | Modalidade de audiodescrição voltada a fins pedagógicos e acadêmicos que considera o receptor, a disciplina e o objetivo de ensino sem induzir respostas ou sobrecarregar cognitivamente (Vergara-Nunes, 2016; REBECA, 2025). |
| **Nota do Digitalizador / Adaptador** | Indicação textual padronizada que insere metadados, alertas de consulta docente ou a própria audiodescrição no corpo de obras digitalizadas acessíveis (padrão REBECA/MEC). |
| **Marcadores de Delimitação Descritiva** | Tags textuais explícitas (`[Início da descrição]` e `[Fim da descrição]`, bem como `[Início da citação]` e `[Final da citação]`) para orientar com precisão softwares leitores de tela na transição entre texto original e conteúdo adaptado. |
| **Two-Part Strategy (Estratégia em Duas Partes)** | Prática recomendada pelo W3C e DIAGRAM Center que combina um texto alternativo conciso (`alt`) com uma descrição longa e estruturada (tabela de dados ou bloco textual adjacente/recolhível). |
| **MathML (Mathematical Markup Language)** | Vocabulário XML padrão da W3C para representar a estrutura sintática e o significado matemático de fórmulas para navegação por leitores de tela e conversão em braille digital (Nemeth). |
| **DPUB-ARIA (Digital Publishing WAI-ARIA)** | Módulo semântico de papéis WAI-ARIA da W3C para componentes estruturais de livros e publicações digitais (ex.: `doc-chapter`, `doc-glossary`, `doc-footnote`, `doc-pagebreak`). |
| **Matterhorn Protocol** | Modelo de testes e catálogo de 31 pontos de verificação e 136 falhas da PDF Association para auditoria e validação de conformidade com a ISO 14289 (PDF/UA). |
| **PDF/UA (Universal Accessibility)** | Norma internacional (ISO 14289-1 e ISO 14289-2) que define requisitos para que documentos em formato PDF contenham árvore de tags semânticas, linearização e navegabilidade universal. |

### 6.4 Termos Gerais

| Termo | Definição |
|-------|-----------|
| **Descrição** | Texto que representa o conteúdo de forma objetiva e observável. |
| **Metadata** | Dados estruturados (JSON/XML) que acompanham a descrição textual. |
| **Linter** | Ferramenta de validação automática que verifica conformidade com o esquema e regras. |
| **Família** | Conjunto de regras aplicáveis a um tipo específico de conteúdo (ex.: 200 para imagens). |
| **Critério** | Regra específica com identificador permanente, evidência obrigatória e ponto de verificação. |

### 6.5 Convenção de Nomenclatura

> **Convenção de Nomenclatura**: Campos de metadata JSON utilizam nomenclatura em inglês (`description`, `license`, `imageType`, etc.) independentemente do idioma da documentação do padrão.

## 7. Requisitos Normativos para Sistemas de Inteligência Artificial

Quando descrições semânticas forem geradas ou assistidas por agentes ou modelos de Inteligência Artificial, o sistema gerador **DEVE**:

1. **Separação Factual**: Distinguir expressamente fatos diretamente observados de hipóteses, deduções ou informações ausentes.
2. **Registro de Incerteza**: Indicar no campo `uncertainty` qualquer elemento visual de baixa confiabilidade ou ambiguidades (ex.: texto parcialmente ilegível, oclusão parcial).
3. **Não Alucinação**: **NÃO DEVE** inventar ou preencher textos ilegíveis, logotipos cortados ou identidades de pessoas não observáveis.
4. **Metadados de Rastreabilidade do Modelo**: Preencher obrigatoriamente os campos de metadata `model`, `modelVersion`, `confidence` (valor numérico de 0 a 1) e `date` em formato ISO 8601 UTC.
5. **Versão do Padrão**: Indicar o padrão e versão adotados (ex.: `"standard": "ACESSILIA 1.1.0"`).
6. **Submissão à Auditoria**: Garantir que as descrições geradas possam ser submetidas ao processo de auditoria humana independente.
7. **Declaração Explícita de Auxílio de IA**: Conforme preconizado no Manual REBECA (2025, §2.12), documentos ou descrições gerados total ou parcialmente com auxílio de modelos de IA **DEVEM** explicitar essa condição junto aos metadados e à fonte da descrição (ex.: `"Descrição realizada na íntegra com recursos de IA: [Modelo]"` ou `"Descrição realizada com auxílio parcial de IA: [Modelo], revisada por [Auditor]"`).
8. **Salvaguarda de Direitos Autorais e Segurança**: Sistemas de IA utilizados na transcrição e descrição de obras intelectuais sob a Lei 9.610/1998 **DEVEM** respeitar as diretrizes de privacidade e confidencialidade institucional, assegurando que conteúdos não públicos não sejam expostos ou retidos por fornecedores sem consentimento.

## 8. Não Objetivos

O padrão ACESSILIA delimita expressamente que **NÃO** pretende:

- Substituir a revisão ou auditoria de especialistas humanos;
- Avaliar a qualidade artística, estética ou poética de obras visuais;
- Determinar ou especular sobre a intenção psicológica do autor da obra visual;
- Interpretar significados culturais profundos ou simbolismos desprovidos de evidência visual factual;
- Substituir as diretrizes WCAG, normas de audiodescrição fílmica (ADLAB) ou normas de legendagem cinematográfica.

## 9. Requisitos de Interoperabilidade Técnica

Sistemas e ferramentas em conformidade com o ACESSILIA **DEVEM**:

- Exportar dados e documentos em codificação **UTF-8** estrita;
- Adotar identificadores permanentes e universais (`UUID` ou padrão `ACL-<FAMÍLIA>-<TIPO>-<NÚMERO>`);
- Identificar idiomas por tags **BCP 47** (ex.: `pt-BR`, `en-US`);
- Representar marcas temporais e durações conforme **ISO 8601** (com timezone);
- Preservar integridade de campos de metadata mesmo em processos de transformação ou exportação.
