# SESAI — Plataforma de Modelagem de Processos · Fluxo Detalhado (v5.0)

Plataforma institucional para validação colaborativa dos fluxos de **obras e engenharia** da
Secretaria Especial de Saúde Indígena (SESAI) / Ministério da Saúde, contemplando as **4 modalidades
de contratação/execução** do documento *Fluxo Detalhado DSEI — Processo Licitatório*.

---

## 🧩 Processos cobertos (abas de processo)

| Aba | Modalidade | Fonte | Etapas |
|-----|-----------|-------|--------|
| ⚖️ Execução Indireta de Obra | Licitação tradicional (Da Demanda à Licitação) | Fluxo Detalhado + Macroprocesso Vol. 2 | 52 atividades |
| 🏗 Execução Direta de Obras — Completa | Licitação apenas de materiais + mão de obra própria/voluntária | Fluxo Detalhado (pág. 5 e 9–10) | 15 etapas |
| 📋 Contratação Direta | Dispensa / Inexigibilidade | Fluxo Detalhado (pág. 6) | 9 etapas |
| 🏛️ Incorporação de Imóvel | Aquisição de imóvel existente | Fluxo Detalhado (pág. 7) | 6 etapas |

### Fluxo-mestre (macro) — Gatilhos determinantes
```
Início → Planejamento estratégico → Processo licitatório/contratação
      → Execução contratual → Pagamento → Conclusão da obra → Manutenção ↻
```
| Gatilho | Evento |
|---------|--------|
| **1** | Aprovação da demanda |
| **2** | Contratação da empresa / Plano de execução |
| **3** | Entregas parciais |
| **4** | Entrega definitiva |

### Rotas da Execução Direta (gateway da etapa 2)
- **Rota A** — Licitação para compra de materiais (o DSEI executa);
- **Rota B** — Contratação de mão de obra especializada;
- **Rota C** — Mão de obra própria do DSEI ou voluntária (com registro de doação de material).

---

## ⚠️ Pendências mapeadas (OBS do Fluxo Detalhado)

1. **Execução indireta** — verificar a legalidade da mobilização da obra pelo DSEI;
2. **Execução direta** — verificar cota de combustível específica;
3. **Execução direta** — definir responsável pelo controle dos materiais nos DSEIs;
4. **Execução direta** — entregas de materiais devem ser programadas conforme o cronograma
   (evitar vencimento de garantias e estoque inadequado);
5. **Contratação direta** — incluir em contrato a obrigatoriedade de treinamento em
   Segurança no Trabalho e Equipamentos ≫ Responsabilidades;
6. **Contratação direta** — todos os processos passam por análise jurídica da CJU, DSEI e SESAI.

---

## 🌐 Publicação no GitHub Pages

1. Suba para a raiz do repositório: `index.html`, `flow.html`, `bpmn.html`, `README.md`
   e a pasta `data/` com os JSONs de processo;
2. **Settings → Pages → Deploy from branch → main / root → Save**;
3. Acesse `https://<usuario>.github.io/<repositorio>/`.

## 📥 Como importar os novos processos

Na plataforma (com login de editor): **＋ Novo processo → Importar JSON** e cole o conteúdo de:
- `data/execucao-direta-completa.json`
- `data/contratacao-direta.json`
- `data/incorporacao.json`

Ou versione-os direto no repositório e referencie no `PROCS.list` do `index.html`.

## 🔑 Credenciais (modo de edição)

| Usuário | Senha | Perfil |
|---------|-------|--------|
| `editor` | `sesai2024` | Editor de fluxo |
| `admin` | `sesai@admin` | Administrador |

## 👥 Atores

DSEI/Gabinete · SESANI · SEOFI · SELOG · SEPAT · DEAMB/COABS · Comunidade/Parceiros

---
*SESAI · Ministério da Saúde · v5.0 — atualizado para contemplar o Fluxo Detalhado DSEI (4 modalidades + gatilhos + manutenção)*
