# ACESSILIA‑200 – Descrição de Imagens Estáticas

> **Família 200** · Identificador de família: `ACL-200`  
> **RFC 2119**: Os termos **DEVE**, **NÃO DEVE**, **PODE** e **RECOMENDA‑SE** devem ser interpretados conforme [RFC 2119](https://tools.ietf.org/html/rfc2119) e [RFC 8174](https://tools.ietf.org/html/rfc8174).

## 1. Escopo
Aplica‑se a todas as imagens estáticas que compõem conteúdo acessível em qualquer mídia: JPEG, PNG, SVG, GIF, TIFF, WebP.  
Exclui: vídeos em movimento, animações interativas, imagens 3D renderizadas em tempo real e conteúdos gerados por algoritmos de machine‑learning.

## 2. Referências de Norma
O conteúdo **DEVE** seguir os princípios e terminologia definidos em [ACESSILIA‑100](../../ACESSILIA-100.md). O identificador principal é `ACL‑200‑IMG‑001`.

## 3. Diretrizes Principais

| Código | Diretriz | Métrica de Avaliação | Comentário |
|--------|----------|----------------------|------------|
| ACL‑200‑IMG‑001 | **Observabilidade** | 100 % de elementos visíveis **DEVEM** estar mapeados. | Usar verbos observáveis. |
| ACL‑200‑IMG‑002 | **Emoções** | 0 % de inferências de emoção sem evidência. | Evitar “pessoa feliz” sem sorriso visível. |
| ACL‑200‑IMG‑003 | **Voz ativa** | 100 % de frases em voz ativa. | Preferir “cortou a lâmpada” a “a lâmpada foi cortada”. |
| ACL‑200‑IMG‑004 | **Ordem espacial** | 100 % de referências de localização orientadas a esq→dir, cima→baixo. | Não misturar direções. |
| ACL‑200‑IMG‑005 | **Privacidade** | 0 % de supressão de dados PII sem aviso. | Nunca omitir dados pessoais sem consentimento explícito. |
| ACL‑200‑IMG‑006 | **Licenciamento** | 100 % de imagens com licença claramente identificada. | Incluir campo `license` no metadata. |
| ACL‑200‑IMG‑007 | **Contraste de Luminância** | Razão de luminância mínima de 4,5 :1 para elementos informativos. | Ver [WCAG 2.2](https://www.w3.org/TR/WCAG22/). |

## 4. Critérios Obrigatórios (ACL‑200‑IMG‑NNN)

| Identificador | Objetivo | Evidência Obrigatória | Importância | Ponto de Verificação |
|---------------|-----------|------------------------|-------------|-----------------------|
| ACL‑200‑IMG‑001 | Garantir que a descrição reflita apenas o que é observável. | Texto descrevendo local e “o que há” diante do olhar do leitor. | Alta | Presença de verbos de ação observáveis em todas as frases. |
| ACL‑200‑IMG‑002 | Evitar inferências de emoções. | Ausência de palavras que indiquem estado emocional sem evidência facial ou gestual. | Alta | Busca por termos de emoção (ex.: “feliz”, “triste”, “irritado”). |
| ACL‑200‑IMG‑003 | Exigir voz ativa. | Sentença começando com verbo de ação em primeira pessoa ou ativa; evitar construções passivas. | Média | Análise sintática da voz verbal. |
| ACL‑200‑IMG‑004 | Manter ordem espacial consistente. | Quando a descrição inclui múltiplos objetos, a sequência segue a ordem esq→dir, cima→baixo. | Média | Verificação da sequência de referências espaciais. |
| ACL‑200‑IMG‑005 | Proteger privacidade. | Se presença de dados pessoais, a descrição **DEVE** indicar “dados protegidos” e evitar supressão automática. | Alta | Presença do campo `privacyNotice` no metadata. |
| ACL‑200‑IMG‑006 | Exigir licenciamento. | Campo JSON `license` no metadata com SPDX ou URL de licença válida. | Alta | Validação de formato SPDX no campo `license`. |
| ACL‑200‑IMG‑007 | Garantir contraste adequado. | Quando a imagem contém texto, a descrição **DEVE** avisar sobre possibilidade de contraste insuficiente. | Média | Presença do campo `contrastWarning` no metadata. |

## 5. Metadados de Exemplo (JSON)

```json
{
  "id": "ACL-200-IMG-001",
  "description": "Mesa de madeira com quatro cadeiras na sala de jantar, iluminada por lâmpada de teto, com foto de cromo e chapéu no gabinete.",
  "language": "pt-BR",
  "license": "https://creativecommons.org/licenses/by/4.0/",
  "standard": "ACESSILIA 1.1.0",
  "date": "2026-07-16T00:00:00Z",
  "reviewStatus": "approved",
  "familyId": 200,
  "imageType": "image/jpeg",
  "resolution": "300dpi",
  "privacyNotice": false,
  "contrastWarning": false,
  "conformsTo": "EPUB Accessibility 1.1 - WCAG 2.2 Level AA",
  "accessMode": ["textual", "visual"],
  "accessibilityFeature": ["alternativeText", "readingOrder"],
  "accessibilityHazard": ["none"],
  "accessibilitySummary": "Esta imagem inclui uma descrição textual detalhada que transmite o conteúdo visual."
}
```

## 6. Exemplos, Técnicas e Falhas Comuns

### 6.1 Exemplos de Conformidade

| Exemplo | Justificativa |
|---------|-----------|
| **Conforme** – "Mesa de madeira com quatro cadeiras na sala de jantar, iluminada por lâmpada de teto, com foto de cromo e chapéu no gabinete." | Cumpre todas as diretrizes: observável, voz ativa, ordem espacial, privacidade. |
| **Não conforme** – "Mesa elegante com cadeiras confortáveis, onde a família parece feliz esperando o jantar." `[viola ACL‑200‑IMG‑001, ACL‑200‑IMG‑002, ACL‑200‑IMG‑003]` | Juízo de valor ("elegante", "confortáveis"), inferência emocional ("parece feliz") e suposição não observável ("esperando o jantar"). |

### 6.2 Catálogo de Técnicas Aplicáveis

| Código | Técnica | Tipo | Aplicabilidade | Critérios Atendidos |
|--------|---------|------|----------------|---------------------|
| `T-200-01` | **Descrição Espacial Metódica**: Sequenciar objetos orientando-se estritamente da esquerda para a direita e de cima para baixo. | Suficiente | Fotografias e ilustrações | `ACL-200-IMG-001`, `ACL-200-IMG-004` |
| `T-200-02` | **Verbos de Ação Observáveis**: Construir cada frase com verbo que denota ação ou estado visualmente identificável na voz ativa. | Suficiente | Todas as imagens estáticas | `ACL-200-IMG-001`, `ACL-200-IMG-003` |
| `T-200-03` | **Registro Factual de Expressão Facial**: Descrever elementos anatômicos observáveis (ex.: "cantos da boca elevados", "olhos semicerrados") sem rotular emoções subjetivas. | Suficiente | Pessoas em foco | `ACL-200-IMG-002` |
| `T-200-04` | **Sinalização Explícita de Incerteza**: Declarar limites visuais objetivos no campo `uncertainty` quando houver oclusão parcial. | Recomendada | Imagens ambíguas | `ACL-200-IMG-001`, `ACL-200-IMG-005` |

### 6.3 Catálogo de Falhas Comuns

| Código | Falha | Severidade | Violação | Exemplo de Falha |
|--------|-------|------------|----------|-------------------|
| `F-200-01` | **Inferência de Profissão ou Status**: Atribuir profissão ou condição social sem comprovação observável. | Crítica | `ACL-200-IMG-001` | Dizer "Médico examinando paciente" em vez de "Pessoa de jaleco branco com estetoscópio perante outra sentada". |
| `F-200-02` | **Atribuição de Emoção sem Evidência**: Projetar sentimentos no sujeito retratado. | Crítica | `ACL-200-IMG-002` | Descrever "Pessoa triste olhando pela janela" quando apenas a cabeça inclinada para baixo é visível. |
| `F-200-03` | **Uso de Adjetivos Avaliativos / Juízo de Valor**: Inserir opinião estética ou qualitativa pessoal. | Grave | `ACL-200-IMG-001` | Descrever objeto como "lindo", "luxuoso", "estranho" ou "agradável". |
| `F-200-04` | **Supressão Oculta de Dados Pessoais**: Omitir dados PII sem documentar no metadata. | Crítica | `ACL-200-IMG-005` | Cortar rosto ou identificador de documento sem sinalizar `privacyNotice: true`. |

## 7. Estratégia de Validação

1. **Validação de esquema**: garantir que todos os campos obrigatórios (`description`, `imageType`, `license`) estejam presentes.
2. **Validação de conteúdo** (via linter): checar presença de verbos ativos, ausência de termos de emoção e conformidade de ordem espacial.
3. **Auditoria de privacidade**: o campo `privacyNotice` **DEVE** ser `true` quando houver dados pessoais na imagem.
4. **Teste de contraste**: se a imagem contiver texto, a linter **DEVE** calcular a razão de contraste e sinalizar se estiver abaixo de 4,5 :1.

## 8. Exemplo de Execução do Lint

```bash
acessilia-lint \
  --schema schemas/acessilia.schema.json \
  --dir ./families/200 \
  --output relatorio-familia200.md
```

O relatório gerado **DEVE** indicar `PASS` ou `FAIL` para cada critério listado na Seção 4.

## 9. Limitações e Exclusões

Esta família aplica‑se exclusivamente a imagens estáticas. Os seguintes tipos de conteúdo **NÃO DEVEM** ser descritos usando esta família:

- **Vídeos e animações em movimento** → usar [ACESSILIA‑600](../600/ACESSILIA‑600.md).
- **Gráficos, tabelas e diagramas** → usar [ACESSILIA‑300](../300/ACESSILIA‑300.md).
- **Imagens 3D renderizadas em tempo real** → exigem família específica futura.
- **Conteúdos gerados por machine‑learning** sem objeto visual observável → não aplicável.
- **Conteúdo científico ou educacional** → usar [ACESSILIA‑400](../400/ACESSILIA‑400.md) ou [ACESSILIA‑500](../500/ACESSILIA‑500.md).
- **Declaração de conformidade e perfis** → usar [ACESSILIA‑800](../800/ACESSILIA‑800.md).

Formatos suportados: JPEG, PNG, SVG, GIF, TIFF, WebP. Formatos não listados **DEVEM** ser validados quanto à conformidade antes da aplicação.
