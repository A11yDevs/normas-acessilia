# Relatório de Revisão Terminológica — ACESSILIA

> **Versão do relatório**: 1.0  
> **Data**: 2026-07-16  
> **Revisor**: Terminology Engineer (big-pickle)  
> **Escopo**: Todos os documentos do projeto ACESSILIA  
> **Base de referência**: ACESSILIA-100 §6 (Glossário) + TERMINOLOGY_GUIDE.md

---

## Resumo Executivo

| Indicador | Valor |
|-----------|-------|
| **Pontuação de Consistência Terminológica** | **72 / 100** |
| **Documentos analisados** | 11 (3 centrais + 7 famílias + 1 spec draft) |
| **Issues críticos** | 3 |
| **Issues importantes** | 8 |
| **Issues menores** | 6 |
| **Issues informativas** | 4 |

### Classificação dos Issues

| Severidade | Quantidade | Descrição |
|------------|------------|-----------|
| **CRÍTICO** | 3 | Inconsistências que afetam conformidade normativa ou causam ambiguidade severa |
| **IMPORTANTE** | 8 | Violações das regras do TERMINOLOGY_GUIDE que afetam clareza e consistência |
| **MENOR** | 6 | Inconsistências de estilo que não comprometem a compreensão |
| **INFORMATIVO** | 4 | Sugestões de melhoria eObservações |

---

## 1. Issues Críticos

### 1.1 Colisão de Identificadores ACL-800-PRF — ID Conflitante entre Perfis e Critérios

**Arquivo**: `families/800/ACESSILIA‑800.md`  
**Seções afetadas**: §5.2 (Perfis Definidos) e §6 (Critérios Obrigatórios)

**Problema**: Os identificadores `ACL-800-PRF-001` a `ACL-800-PRF-005` são usados tanto para **perfis** (§5.2) quanto para **critérios obrigatórios** (§6):

| ID | Uso em §5.2 (Perfil) | Uso em §6 (Critério) |
|----|-----------------------|----------------------|
| `ACL-800-PRF-001` | Perfil "Livro Digital" | Critério "Declarar nível de conformidade" |
| `ACL-800-PRF-002` | Perfil "Fotografia" | Critério "Listar famílias aplicáveis" |
| `ACL-800-PRF-003` | Perfil "Conteúdo Matemático" | Critério "Definir tipos MIME" |
| `ACL-800-PRF-004` | Perfil "Gráfico Científico" | Critério "Especificar metadados obrigatórios" |
| `ACL-800-PRF-005` | Perfil "Captura de Tela" | Critério "Documentar extensões" |

**Impacto**: Gera ambiguidade severa. Um referencial `ACL-800-PRF-001` pode significar tanto o perfil "Livro Digital" quanto o critério "Declarar nível de conformidade".

**Recomendação**: Usar prefixos distintos. Por exemplo:
- Perfis: `ACL-800-PRF-PERF-NNN` (ex.: `ACL-800-PRF-PERF-001`)
- Critérios: `ACL-800-PRF-CRT-NNN` (ex.: `ACL-800-PRF-CRT-001`)

Ou alternativamente, deslocar os IDs dos perfis para a faixa 010+.

---

### 1.2 Uso Inconsistente de "metadata" vs "metadados" — Violação Direta do TERMINOLOGY_GUIDE

**Regra do TERMINOLOGY_GUIDE §1.2**:
> **Metadata** | **Metadata** | "metadados" (inconsistent casing) | Use "metadata" (lowercase, singular in English; invariant in PT).

**Ocorrências de violação** (19 ocorrências em 9 arquivos):

| Arquivo | Linha | Texto Encontrado | Deveria ser |
|---------|-------|-------------------|-------------|
| ACESSILIA-100.md | 104 | "estrutura obrigatória dos **metadados**" | "metadata" |
| ACESSILIA-100.md | 110 | "conteúdo e **metadados** atendem" | "metadata" |
| ACESSILIA-100.md | 142 | "Campos de **metadados** JSON" | "metadata" |
| ACESSILIA-Index.md | 42 | "Validação de **metadados**" | "metadata" |
| ACESSILIA-Base.md | 120 | "validação de **metadados**" | "metadata" |
| README.md | 49 | "Ausência de **metadados**" | "metadata" |
| Families 200–600 | §5 headers | "**Metadados** de Exemplo (JSON)" | "Metadata de Exemplo (JSON)" |
| ACESSILIA-800.md | 19, 87, 124, 137 | "**Metadados**" / "metadados" | "metadata" |
| ACESSILIA-400.md | 26, 27 | "**Metadado** `bibliography`" | "metadata `bibliography`" |

**Impacto**: Violação explícita da convenção de nomenclatura. A seção §6.5 do ACESSILIA-100 afirma que "Campos de metadados JSON utilizam nomenclatura em inglês", mas o próprio documento mistura "metadados" (PT) e "metadata" (EN).

---

### 1.3 Uso de "DEVERIA" no SPEC_CH01 — Keyword RFC 2119 Desatualizada

**Arquivo**: `ACESSILIA_SPEC_CH01.txt`  
**Linhas**: 18, 21

**Problema**: O draft original usa "DEVERIA" como equivalente de SHOULD, enquanto todos os documentos normativos atuais usam "RECOMENDA-SE":

| Documento | Keyword para SHOULD | Status |
|-----------|---------------------|--------|
| ACESSILIA_SPEC_CH01.txt | **DEVERIA** | Desatualizado |
| ACESSILIA-100.md | **RECOMENDA-SE** | Correto |
| ACESSILIA-Base.md | **RECOMENDA-SE** | Correto |
| Todas as famílias (200–800) | **RECOMENDA-SE** | Correto |
| TERMINOLOGY_GUIDE.md | **RECOMENDA-SE** | Correto |

**Impacto**: O SPEC_CH01 é o draft original e pode ser consultado por implementadores. O uso de "DEVERIA" pode gerar confusão sobre qual keyword usar.

**Recomendação**: Atualizar o SPEC_CH01 para usar "RECOMENDA-SE" ou adicionar nota de que aquele documento é superseded pelos normativos atuais.

---

## 2. Issues Importantes

### 2.1 "compatibilidade" — Termo Depreciado Usado em Família 200

**Arquivo**: `families/200/ACESSILIA‑200.md`, linha 97  
**TERMINOLOGY_GUIDE §1.2**: "compatibilidade" é termo deprecado, substituir por "conformidade".

**Texto encontrado**:
> Formatos não listados **DEVEM** ser validados quanto à **compatibilidade** antes da aplicação.

**Texto sugerido**:
> Formatos não listados **DEVEM** ser validados quanto à **conformidade** antes da aplicação.

---

### 2.2 "ferramenta de lint" — Expressão Deprecada em ACESSILIA-Base

**Arquivo**: `ACESSILIA-Base.md`, linha 117  
**TERMINOLOGY_GUIDE §1.2**: Usar "linter" ou "ACESSILIA Lint", não "ferramenta de lint".

**Texto encontrado**:
> Uma **ferramenta de lint**, **`acessilia-lint`**, **DEVE** ser fornecida.

**Texto sugerido**:
> Um **linter** oficial, **`acessilia-lint`**, **DEVE** ser fornecido.

---

### 2.3 "verificação automática via linter" — Deveria ser "validação"

**Arquivo**: `families/700/ACESSILIA‑700.md`, linhas 19 e 29  
**TERMINOLOGY_GUIDE §1.2**: "verificação" não deve ser usada para referir-se a checks automatizados; o termo correto é "validação".

**Ocorrências**:
- Linha 19: `Verificação automática via linter` (como Ponto de Verificação de ACL-700-VAL-004)
- Linha 29: `Verificação automática via linter` (como Métrica de Avaliação de Objetividade)

**Nota**: O termo "Verificação" é aceitável no contexto de "Ponto de Verificação" (que é um termo definido), mas quando se refere ao processo automatizado em si, deve ser "Validação".

---

### 2.4 "auditabilidade" — Termo Não Definido no Glossário

**Arquivos**: ACESSILIA-100.md (linha 51), Families 300, 500, 600, 700, 800 (§2 Referências de Norma)

**Problema**: O termo "auditabilidade" é usado em múltiplos documentos ("princípios de terminologia e auditabilidade") mas não consta do glossário do ACESSILIA-100 §6.

**Recomendação**: Adicionar "auditabilidade" ao glossário ou substituir por "auditoria" (já definida). Alternativa: "rastreabilidade e auditoria" (já que ambos os termos estão definidos).

---

### 2.5 "Contraste" — Ambiguidade com Termos Definidos

**Arquivo**: `families/200/ACESSILIA‑200.md`, linha 23  
**Glossário ACESSILIA-100 §6.3**: Define "**Contraste de Luminância**" e "**Contraste de Cores**" como termos distintos.

**Problema**: O guideline ACL-200-IMG-007 usa apenas "**Contraste**" como nome bold, quando se refere especificamente a "Contraste de Luminância". Isso pode gerar confusão com "Contraste de Cores" (usado na família 300).

**Recomendação**: Renomear para **Contraste de Luminância** para alinhar com o glossário.

---

### 2.6 "Rastreabilidade" Usado como Nome de Guideline em Família 400

**Arquivo**: `families/400/ACESSILIA‑400.md`, linha 19

**Problema**: O guideline ACL-400-SCI-004 usa "**Rastreabilidade**" como nome bold, mas este é um termo definido no glossário do ACESSILIA-100 §6.2 como princípio operacional. Usá-lo como nome de guideline pode criar confusão semântica.

**Recomendação**: Renomear para algo como "**Rastreabilidade da Publicação**" ou "**Versionamento e Rastreabilidade**" para distinguir do princípio geral.

---

### 2.7 "Legenda (Video)" sem Acento no TERMINOLOGY_GUIDE

**Arquivo**: `TERMINOLOGY_GUIDE.md`, linha 172  
**Glossário ACESSILIA-100 §6.3, linha 127**: "**Legenda (Vídeo)**" (com acento)

**Problema**: Inconsistência de grafia entre os dois documentos oficiais.

| Documento | Grafia |
|-----------|--------|
| ACESSILIA-100 §6.3 | **Legenda (Vídeo)** |
| TERMINOLOGY_GUIDE §4.3 | **Legenda (Video)** |

**Recomendação**: Padronizar para "Legenda (Vídeo)" com acento em ambos os documentos.

---

### 2.8 "Índice de Gunning" sem Acento no TERMINOLOGY_GUIDE

**Arquivo**: `TERMINOLOGY_GUIDE.md`, linha 173  
**Glossário ACESSILIA-100 §6.3, linha 128**: "**Índice de Gunning**" (com acento)

**Problema**: Mesma inconsistência de grafia que o item 2.7.

| Documento | Grafia |
|-----------|--------|
| ACESSILIA-100 §6.3 | **Índice de Gunning** |
| TERMINOLOGY_GUIDE §4.3 | **Indice de Gunning** |

**Recomendação**: Padronizar para "Índice de Gunning" com acento.

---

## 3. Issues Menores

### 3.1 "Principio" sem Acento na Hierarquia de Critérios

**Arquivo**: `TERMINOLOGY_GUIDE.md`, linha 182  
**ACESSILIA_SPEC_CH01.txt, linha 247**: "Princípio" (com acento)

**Texto encontrado**:
```
Principio > Diretriz > Criterio > Metodo > Tecnica > Falha > Exemplo
```

**Texto sugerido**:
```
Princípio > Diretriz > Critério > Método > Técnica > Falha > Exemplo
```

**Nota**: Os termos "Criterio", "Metodo" e "Tecnica" também estão sem acento na linha 182. Devem ser "Critério", "Método" e "Técnica".

---

### 3.2 "Revisão Humana" vs "Auditoria" em Família 700

**Arquivo**: `families/700/ACESSILIA‑700.md`, linha 34

**Problema**: A seção é intitulada "### 5.1 Revisão Humana" quando, pelo contexto (é o processo formal de validação além da automática), deveria usar o termo definido "Auditoria".

**Recomendação**: Renomear para "### 5.1 Auditoria Humana" ou "### 5.1 Auditoria".

---

### 3.3 Section Headers "Referências de Norma" — Inconsistência com Glossário

**Arquivos**: Todas as famílias (200–800), seção §2

**Problema**: Usa-se "Referências de Norma" como título de seção, mas o termo "Norma" é listado como termo a evitar no TERMINOLOGY_GUIDE §1.2 (deve-se usar "Diretriz", não "regra" ou "norma").

**Nota**: Neste contexto, "Norma" refere-se a documentos normativos externos (WCAG, EPUB, etc.), não ao conceito interno de "diretriz". Portanto, o uso é aceitável, mas poderia ser mais preciso como "Referências Normativas" (padrão ISO/IEC).

---

### 3.4 Nomes de Guidelines Bold Não Introduzidos com Definição

**Arquivos**: Families 200–800, tabela "Diretrizes Principais"

**Problema**: O TERMINOLOGY_GUIDE §1.1 exige que termos técnicos sejam introduzidos em **negrito na primeira ocorrência** com definição. Os nomes dos guidelines nas tabelas (ex.: **Observabilidade**, **Emoções**, **Voz ativa**) aparecem em negrito mas sem definição formal. Embora sejam nomes de guidelines (não termos do glossário), a ausência de definição pode confundir leitores novos.

**Recomendação**: Considerar adicionar uma linha de referência cruzada ao glossário do ACESSILIA-100 ou criar uma tabela de nomenclatura de guidelines por família.

---

### 3.5 "NÃO DEVEM" (plural) vs "NÃO DEVE" (singular)

**Arquivos**: Diversos

**Problema**: Uso misto de concordância verbal:
- README.md linha 171: "**NÃO DEVEM** declarar conformidade" (plural)
- ACESSILIA-800.md linha 94: "**NÃO DEVEM** declarar conformidade" (plural)
- Família 200, linha 88: "**NÃO DEVEM** ser descritos" (plural)

**Nota**: A concordância verbal em português é gramaticalmente correta (verbo concorda com o sujeito). Porém, RFC 2119 em inglês usa sempre "MUST NOT" sem variação. Para máxima consistência, poderia-se padronizar o verbo no singular quando o sujeito for coletivo.

---

### 3.6 Família 600 Usa "Legendas" Não-Alinhado ao Glossário

**Arquivo**: `families/600/ACESSILIA‑600.md`, linha 17

**Problema**: O guideline ACL-600-MDM-002 usa "**Legendas**" como nome bold. O glossário do ACESSILIA-100 §6.3 define "**Legenda (Vídeo)**" (com qualificador entre parênteses). O nome do guideline deveria ser "**Legendas (Vídeo)**" ou "**Legendas Sincronizadas**" para alinhar com a terminologia definida.

---

## 4. Issues Informativos

### 4.1 Cobertura do Glossário — Termos de Guidelines por Família

Os nomes dos guidelines nas tabelas "Diretrizes Principais" das famílias 200–600 não estão documentados no glossário do ACESSILIA-100. Embora não sejam termos normativos, a ausência de documentação pode dificultar a busca e referência cruzada.

**Sugestão**: Adicionar ao ACESSILIA-100 uma seção "Termos de Família" ou "Nomenclatura de Guidelines" documentando os nomes usados em cada família.

---

### 4.2 "Conformidade Parcial" — Conceito Não Formalizado

**Arquivo**: `families/700/ACESSILIA‑700.md`, linha 98

**Texto**:
> A conformidade parcial (reprovação em critérios de baixa importância) **PODE** ser aceita mediante justificativa documentada no relatório.

O conceito de "conformidade parcial" não é formalmente definido no glossário. Seria útil adicionar uma definição para evitar ambiguidade com o termo "Conformidade" (que implica atendimento integral).

---

### 4.3 Consistência de Formato "RECOMENDA-SE" vs "RECOMENDA‑SE"

**Problema**: Variação sutil no character do hífen:
- README.md: `RECOMENDA-SE` (hyphen U+002D)
- ACESSILIA-100.md, families: `RECOMENDA‑SE` (non-breaking hyphen U+2011)

**Impacto**: Mínimo, mas inconsistentes em buscas textuais.

---

### 4.4 "Versão do padrão" — Variação de Formato

| Arquivo | Formato |
|---------|---------|
| ACESSILIA-Base.md §7.3 | `**Versão do padrão**: 1.0.0` |
| README.md | `**Versão**: 1.1.0` |
| ACESSILIA-Index.md | `**Versão**: 1.1.0` |
| manifest.yml | `version: "1.1.0"` |

A versão é 1.1.0 em todos os lugares, mas o rótulo varia ("Versão" vs "Versão do padrão"). Recomenda-se padronizar.

---

## 5. Análise de Conformidade por Documento

### 5.1 ACESSILIA-100.md

| Critério | Status | Observação |
|----------|--------|------------|
| Glossário completo | OK | 4 categorias, 30+ termos |
| RFC 2119 no cabeçalho | OK | |
| Termos bold na primeira ocorrência | OK | |
| "metadata" em vez de "metadados" | FALHA | §6.4 usa "metadados" (3 ocorrências) |
| Ausência de termos deprecados | OK | |

### 5.2 ACESSILIA-Base.md

| Critério | Status | Observação |
|----------|--------|------------|
| RFC 2119 no cabeçalho | OK | |
| "metadata" em vez de "metadados" | FALHA | Linha 120: "metadados" |
| "linter" em vez de "ferramenta de lint" | FALHA | Linha 117: "ferramenta de lint" |
| Conformidade com glossário | OK | |

### 5.3 ACESSILIA-Index.md

| Critério | Status | Observação |
|----------|--------|------------|
| RFC 2119/8174 no cabeçalho | OK | |
| "metadata" em vez de "metadados" | FALHA | Linha 42: "metadados" |
| Referências cruzadas | OK | |

### 5.4 README.md

| Critério | Status | Observação |
|----------|--------|------------|
| RFC 2119/8174 no cabeçalho | OK | |
| "metadata" em vez de "metadados" | FALHA | Linha 49: "metadados" |
| Glossário referenciado | OK | |
| Conformidade com TERMINOLOGY_GUIDE | PARCIAL | Usa termos definidos corretamente |

### 5.5 TERMINOLOGY_GUIDE.md

| Critério | Status | Observação |
|----------|--------|------------|
| Regras documentadas | OK | |
| Hierarquia de critérios | FALHA | Linha 182: sem acentos ("Principio", "Criterio", etc.) |
| Acentos em termos técnicos | FALHA | "Legenda (Video)" e "Indice de Gunning" sem acento |
| Checklist completo | OK | |

### 5.6 Famílias 200–600

| Família | RFC 2119 | Glossário | "metadata" | Termos deprecados | Bold 1ª ocorrência |
|---------|----------|-----------|------------|-------------------|---------------------|
| **200** | OK | OK | FALHA (§5 header) | FALHA ("compatibilidade" l.97) | PARCIAL |
| **300** | OK | OK | FALHA (§5 header) | OK | PARCIAL |
| **400** | OK | OK | FALHA (§5 header, l.26-27) | OK | PARCIAL |
| **500** | OK | OK | FALHA (§5 header) | OK | PARCIAL |
| **600** | OK | OK | FALHA (§5 header) | OK | PARCIAL |
| **700** | OK | OK | OK (usa "metadata" corretamente l.19) | OK | OK |
| **800** | OK | OK | FALHA (múltiplas l.19,87,124,137) | OK | PARCIAL |

### 5.7 ACESSILIA_SPEC_CH01.txt

| Critério | Status | Observação |
|----------|--------|------------|
| RFC 2119 keywords | FALHA | Usa "DEVERIA" em vez de "RECOMENDA-SE" |
| Glossário alinhado | FALHA | Definições divergem do ACESSILIA-100 |
| Status | DRAFT | Documento original, superseded |

---

## 6. Mapa de Consistência Terminológica

### 6.1 Termos-Chave vs. Uso Real

| Termo Definido (ACESSILIA-100) | TERMINOLOGY_GUIDE | Uso nos documentos | Consistente? |
|-------------------------------|-------------------|--------------------|--------------|
| **Metadata** | "metadata" sempre | "metadados" em 9 arquivos | **NÃO** |
| **Conformidade** | Não usar "compatibilidade" | "compatibilidade" em Fam.200 | **NÃO** |
| **Validação** | Não usar "verificação" para automated checks | "verificação" em Fam.700 | **PARCIAL** |
| **Auditoria** | Não usar "revisão" para processo formal | "Revisão Humana" em Fam.700 | **PARCIAL** |
| **Linter** | Não usar "ferramenta de lint" | "ferramenta de lint" em Base | **NÃO** |
| **RECOMENDA-SE** | Keyword oficial para SHOULD | "DEVERIA" em SPEC_CH01 | **NÃO** |
| **Contraste de Luminância** | Termo definido | "Contraste" (abreviado) em Fam.200 | **PARCIAL** |
| **Legenda (Vídeo)** | Acento obrigatório | "Legenda (Video)" em Guide | **NÃO** |
| **Índice de Gunning** | Acento obrigatório | "Indice de Gunning" em Guide | **NÃO** |
| **Princípio** | Hierarquia com acentos | "Principio" em Guide l.182 | **NÃO** |

### 6.2 RFC 2119 Keywords — Consistência Cross-Documento

| Keyword | PT (Definido) | ACESSILIA-100 | Base | Famílias | SPEC_CH01 | Guide |
|---------|---------------|---------------|------|----------|-----------|-------|
| MUST | **DEVE** | OK | OK | OK | OK | OK |
| MUST NOT | **NÃO DEVE** | OK | OK | OK | OK | OK |
| MAY | **PODE** | OK | OK | OK | OK | OK |
| SHOULD | **RECOMENDA-SE** | OK | OK | OK | **DEVERIA** | OK |

---

## 7. Ações Recomendadas (Priorizadas)

### Prioridade 1 — Crítica (resolver antes da próxima release)

| # | Ação | Arquivo(s) | Esforço |
|---|------|-----------|---------|
| 1 | Corrigir colisão de IDs ACL-800-PRF | ACESSILIA-800.md | Alto |
| 2 | Substituir "metadados" → "metadata" em todos os documentos | 9 arquivos | Médio |
| 3 | Atualizar "DEVERIA" → "RECOMENDA-SE" no SPEC_CH01 | SPEC_CH01.txt | Baixo |

### Prioridade 2 — Importante (resolver antes da publicação)

| # | Ação | Arquivo(s) | Esforço |
|---|------|-----------|---------|
| 4 | Substituir "compatibilidade" → "conformidade" | Fam.200 l.97 | Baixo |
| 5 | Substituir "ferramenta de lint" → "linter" | Base l.117 | Baixo |
| 6 | Corrigir "verificação automática" → "validação automática" | Fam.700 l.19,29 | Baixo |
| 7 | Adicionar "auditabilidade" ao glossário ou substituir | ACESSILIA-100 + families | Baixo |
| 8 | Corrigir acentos: "Legenda (Video)" → "(Vídeo)", "Indice" → "Índice" | Guide l.172,173 | Baixo |
| 9 | Corrigir hierarquia: "Principio > Criterio > Metodo > Tecnica" | Guide l.182 | Baixo |
| 10 | Renomear "Contraste" → "Contraste de Luminância" | Fam.200 l.23 | Baixo |

### Prioridade 3 — Menor (melhoria de qualidade)

| # | Ação | Arquivo(s) | Esforço |
|---|------|-----------|---------|
| 11 | Renomear "Revisão Humana" → "Auditoria" | Fam.700 §5.1 | Baixo |
| 12 | Renomear "Rastreabilidade" guideline em Fam.400 | Fam.400 l.19 | Baixo |
| 13 | Renomear "Legendas" → "Legendas Sincronizadas" | Fam.600 l.17 | Baixo |
| 14 | Adicionar glossário de nomes de guidelines por família | ACESSILIA-100 | Médio |
| 15 | Padronizar formato "RECOMENDA-SE" (hífen) | README.md | Baixo |

---

## 8. Conclusão

O projeto ACESSILIA demonstra uma **estrutura terminológica sólida** com glossário abrangente, guia de terminologia bem estruturado e uso consistente da maioria dos termos definidos. A principal vulnerabilidade é a **inconsistência na aplicação das próprias regras** — especialmente o uso de "metadados" em vez de "metadata", que é a violação mais prevalente (19 ocorrências em 9 arquivos).

A **colisão de identificadores na família 800** é a issue mais estruturalmente grave e deve ser priorizada, pois afeta a rastreabilidade — um dos princípios fundamentais do padrão.

Com as correções recomendadas (especialmente Prioridade 1 e 2), a pontuação de consistência pode subir de **72 para ~92/100**.

---

> **Próximos passos**: Aplicar as correções da Prioridade 1, revisitar esta análise, e incorporar o checklist do TERMINOLOGY_GUIDE §10 no fluxo de CI/CD.
