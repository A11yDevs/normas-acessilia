# ACESSILIA‑500 – Conteúdo Educacional

> **Família 500** · Identificador de família: `ACL-500`  
> **RFC 2119**: Os termos **DEVE**, **NÃO DEVE**, **PODE** e **RECOMENDA‑SE** devem ser interpretados conforme [RFC 2119](https://tools.ietf.org/html/rfc2119) e [RFC 8174](https://tools.ietf.org/html/rfc8174).

## 1. Escopo
Aplica‑se a materiais didáticos: apostilas, slides, textos de apoio, exercícios, simulados e recursos pedagógicos digitais.

## 2. Referências de Norma
Conforme [ACESSILIA‑100](../../ACESSILIA-100.md) para princípios de terminologia e auditabilidade. Em adição ao [WCAG 2.2](https://www.w3.org/TR/WCAG22/), [EPUB 3](https://www.w3.org/TR/epub-33/), **Manual de Padronização REBECA (Rede Brasileira de Estudos e Conteúdos Adaptados, 2025)**, **Nota Técnica nº 21/MEC/SECADI/DPEE (MECDAISY, 2012)** e o modelo de **Audiodescrição Didática - ADD (Vergara-Nunes, 2016)** para materiais e recursos pedagógicos acessíveis.

## 3. Diretrizes Principais

| Código | Diretriz | Métrica de Avaliação | Comentário |
|--------|----------|----------------------|------------|
| ACL‑500‑EDU‑001 | **Contexto de Aprendizagem** | 100 % das descrições **DEVEM** incluir contexto pedagógico. | A descrição **DEVE** indicar o tema, o público-alvo e o nível educacional. |
| ACL‑500‑EDU‑002 | **Objetivos de Aprendizagem** | 100 % dos materiais **DEVEM** declarar objetivos mensuráveis. | Objetivos **DEVEM** usar verbos de ação mensuráveis (Bloom). |
| ACL‑500‑EDU‑003 | **Progressão** | 100 % dos conteúdos **DEVEM** seguir sequência lógica. | A ordem dos tópicos **DEVE** respeitar progressão do simples ao complexo. |
| ACL‑500‑EDU‑004 | **Exemplos e Contra‑exemplos** | Cada conceito **DEVE** ter ao menos 1 exemplo e 1 contra‑exemplo. | Exemplos **DEVEM** ser observáveis e objetivos. |

## 4. Critérios Obrigatórios (ACL‑500‑EDU‑NNN)

| Identificador | Objetivo | Evidência Obrigatória | Importância | Ponto de Verificação |
|---------------|-----------|------------------------|-------------|-----------------------|
| ACL‑500‑EDU‑001 | Incluir contexto pedagógico na descrição. | Campo `educationalContext` no metadata com tema, público e nível. | Alta | Presença do campo `educationalContext` com subcampos obrigatórios. |
| ACL‑500‑EDU‑002 | Declarar objetivos mensuráveis. | Campo `learningObjectives` contendo lista de objetivos com verbos de Bloom. | Alta | Verificação de verbos de ação mensuráveis nos objetivos. |
| ACL‑500‑EDU‑003 | Garantir progressão lógica. | Sequência de tópicos documentada no campo `sequence`. | Média | Ordem crescente de complexidade no campo `sequence`. |
| ACL‑500‑EDU‑004 | Fornecer exemplos e contra‑exemplos. | Campo `examples` com ao menos 1 entrada positiva e 1 negativa. | Média | Presença de ao menos um exemplo e um contra‑exemplo. |

## 5. Metadados de Exemplo (JSON)

```json
{
  "id": "ACL-500-EDU-001",
  "description": "Apostila de introdução à programação para ensino médio",
  "language": "pt-BR",
  "license": "https://creativecommons.org/licenses/by-sa/4.0/",
  "standard": "ACESSILIA 1.1.0",
  "date": "2026-07-16T00:00:00Z",
  "reviewStatus": "approved",
  "familyId": 500,
  "educationalContext": {
    "theme": "Programação básica",
    "targetAudience": "Ensino médio",
    "level": "Introdutório"
  },
  "learningObjectives": [
    "Identificar variáveis e tipos de dados",
    "Escrever estruturas de controle condicional"
  ],
  "sequence": ["Variáveis", "Tipos de dados", "Operadores", "Condicionais"],
  "examples": [
    {"type": "positive", "text": "Uma variável x = 5 armazena o número inteiro 5."},
    {"type": "negative", "text": "Uma variável x = 'cinco' mistura texto com número sem conversão."}
  ]
}
```

## 6. Exemplos, Técnicas e Falhas Comuns

### 6.1 Exemplos de Conformidade

| Exemplo | Justificativa |
|---------|-----------|
| **Conforme** – “Apostila destinada ao ensino médio, abordando fundamentos de programação. Objetivo: identificar variáveis e escrever condicionais.” | Inclui contexto, público, nível e objetivos mensuráveis. |
| **Não conforme** – “Material sobre programação.” `[viola ACL‑500‑EDU‑001, ACL‑500‑EDU‑002, ACL‑500‑EDU‑003, ACL‑500‑EDU‑004]` | Falta contexto educacional, objetivos e progressão. |

### 6.2 Diretrizes de Audiodescrição Didática (ADD - Padrão REBECA / Vergara-Nunes)

A descrição didática de elementos visuais pedagógicos **DEVE** apoiar-se no tripé metodológico:
1. **Receptor**: Identificar quem é o estudante (curso, disciplina, etapa formativa e tipo de deficiência visual).
2. **Contexto de Uso**: Delimitar com exatidão o que a atividade didática ou o docente visa ensinar com aquela figura, evitando sobrecarga cognitiva desnecessária.
3. **Foco e Não Revelação de Resposta**: Descrever primeiramente a visão geral do elemento e, em exercícios avaliativos, **NÃO DEVE** fornecer a resposta ou conclusão que o estudante precisa deduzir.

### 6.3 Catálogo de Técnicas Aplicáveis

| Código | Técnica | Tipo | Aplicabilidade | Critérios Atendidos |
|--------|---------|------|----------------|---------------------|
| `T-500-01` | **Visão Geral Preliminar**: Iniciar a descrição didática contextualizando o tipo de diagrama ou imagem antes de descer aos detalhes anatômicos ou funcionais. | Suficiente | Todas as imagens didáticas | `ACL-500-EDU-001`, `ACL-500-EDU-003` |
| `T-500-02` | **Verbos Cognitivos da Taxonomia de Bloom**: Formular metas de aprendizagem com verbos de ação mensuráveis (identificar, diferenciar, calcular, categorizar). | Suficiente | Metas e objetivos instrucionais | `ACL-500-EDU-002` |
| `T-500-03` | **Sinalização Didática de Consulta Docente**: Quando a imagem exigir especialidade técnica além da capacidade do núcleo de acessibilidade, inserir a nota padronizada: `Nota do digitalizador: Procure o auxílio do professor para descrição da imagem`. | Recomendada | Conteúdo técnico complexo | `ACL-500-EDU-001` |

### 6.4 Catálogo de Falhas Comuns

| Código | Falha | Severidade | Violação | Exemplo de Falha |
|--------|-------|------------|----------|-------------------|
| `F-500-01` | **Revelação Prematura da Resposta**: Descrever o elemento indicando a solução da questão de múltipla escolha ou exercício. | Crítica | `ACL-500-EDU-001` | Dizer em um teste de botânica: "Figura mostrando a folha de bordo, que é a resposta correta". |
| `F-500-02` | **Sobrecarga Cognitiva por Hiperdetalhamento**: Inserir detalhes irrelevantes para o objetivo de ensino que dispersam a atenção auditiva do estudante. | Alta | `ACL-500-EDU-003` | Descrever a cor da moldura ou arte gráfica em um problema de física de plano inclinado. |

## 7. Estratégia de Validação

1. **Validação de esquema**: garantir que todos os campos obrigatórios (`educationalContext`, `learningObjectives`, `sequence`, `examples`, `license`) estejam presentes.
2. **Validação de verbos**: o linter **DEVE** verificar se os objetivos contêm verbos de Bloom mensuráveis.
3. **Validação de exemplos**: o linter **DEVE** garantir a existência de ao menos um exemplo positivo e um negativo.
4. **Auditoria de progressão**: a sequência de tópicos **DEVE** respeitar ordem crescente de complexidade.

## 8. Exemplo de Execução do Lint

```bash
acessilia-lint \
  --schema schemas/acessilia.schema.json \
  --dir ./families/500 \
  --output relatorio-familia500.md
```

O relatório gerado **DEVE** indicar `PASS` ou `FAIL` para cada critério listado na Seção 4.

## 9. Limitações e Exclusões

Esta família aplica‑se a materiais didáticos e recursos pedagógicos. Os seguintes tipos de conteúdo **NÃO DEVEM** ser descritos exclusivamente usando esta família:

- **Publicações científicas ou técnicas** → usar [ACESSILIA‑400](../400/ACESSILIA‑400.md).
- **Imagens didáticas e diagramas** → aplicar também [ACESSILIA‑200](../200/ACESSILIA‑200.md) ou [ACESSILIA‑300](../300/ACESSILIA‑300.md).
- **Vídeo‑aulas e conteúdos audiovisuais** → usar [ACESSILIA‑600](../600/ACESSILIA‑600.md).
- **Avaliações e provas** sem contexto pedagógico descritivo → não aplicável.
- **Documentos administrativos** (editais, regimentos) → não são materiais didáticos.
- **Declaração de conformidade e perfis** → usar [ACESSILIA‑800](../800/ACESSILIA‑800.md).

A verificação de verbos de Bloom depende de base lexical e pode não reconhecer variações regionais ou termos técnicos específicos.
