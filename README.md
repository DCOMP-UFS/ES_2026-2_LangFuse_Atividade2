# Atividade 2 — Auditoria Forense de Software e Plano de Resgate Técnico

**Disciplina:** Engenharia de Software (COMP0503)  
**Projeto analisado:** [langfuse/langfuse](https://github.com/langfuse/langfuse)  
**Equipe:** Dean Vinícius Palmeira de Meneses; Hilton Hunaldo Costa Silva Brito

---

## Vídeo de Auditoria Técnica

[Assistir no Google Drive](https://drive.google.com/file/d/1S0k9nr6PIrACr3TfmejYOUEQCW-Ggqjh/view?usp=sharing)

---

## Artefatos

| Arquivo | Descrição |
|---|---|
| `relatorio.pdf` | Relatório técnico completo (Evidência + Diagnóstico + Recomendação por item) |
| `slides.pdf` | Apresentação de impacto (Beamer/LaTeX) com riscos e plano de resgate |
| `relatorio.tex` | Fonte LaTeX do relatório |
| `slides.tex` | Fonte LaTeX dos slides |
| `prints/` | Prints de evidências referenciados nos documentos |

---

## Como reproduzir a análise

### Pré-requisitos

- [pdflatex](https://www.tug.org/texlive/) ou [Tectonic](https://tectonic-typesetting.github.io/) instalado
- Acesso ao repositório [langfuse/langfuse](https://github.com/langfuse/langfuse) no GitHub

### Gerando os PDFs

```bash
pdflatex relatorio.tex
pdflatex slides.tex
```

Ou com Tectonic:

```bash
tectonic relatorio.tex
tectonic slides.tex
```

### Verificando as evidências no código

Todos os trechos analisados estão linkados diretamente no relatório. Para navegar:

1. Clone o repositório original:
   ```bash
   git clone https://github.com/langfuse/langfuse.git
   ```
2. Abra no VS Code e navegue até os arquivos e linhas indicados em cada seção do relatório.

### Principais pontos de evidência

| Eixo | Arquivo | Linha |
|---|---|---|
| A1 — Arqueologia de Issues | [Issue #13933](https://github.com/langfuse/langfuse/issues/13933) | — |
| A2 — TODOs críticos | `worker/src/queues/webhooks.ts` | 49, 568 |
| A2 — TODOs críticos | `worker/src/queues/otelIngestionQueue.ts` | 215 |
| B1 — Violação DIP | `packages/shared/src/server/llm/fetchLLMCompletion.ts` | 303–413 |
| B2 — God Object | `packages/shared/src/server/llm/fetchLLMCompletion.ts` | 303–413 |
| B3 — DRY | `web/src/components/trace2/lib/tree-building.ts` | 466 |
| C1 — Singleton | `packages/shared/src/db.ts` | 8–18 |
| C2 — Adapter | `packages/shared/src/utils/chatml/adapters/index.ts` | 11–37 |

---

## Estrutura do repositório

```
ES_2026-2_LangFuse_Atividade2/
├── relatorio.pdf       # Relatório técnico
├── relatorio.tex       # Fonte LaTeX do relatório
├── slides.pdf          # Apresentação Beamer
├── slides.tex          # Fonte LaTeX dos slides
└── prints/             # Prints de evidências
```
