# Comparação das versões dos processos — SESAI

**Objetivo:** subsidiar a definição da versão oficial de cada processo (definição nº 1 pendente
da revisão técnica). Nenhuma versão é recomendada aqui por suposição — as diferenças de
conteúdo são decisões de negócio da equipe.

**Fontes comparadas:**

- **Interna** — constantes embutidas no `index.html` (revisão `942cf26`), carregadas
  automaticamente ao abrir a plataforma;
- **data/** — JSONs do repositório, usados apenas em importação manual;
- **README** — descrições publicadas no repositório.

## 1. Resumo das divergências

| Processo | README / data/ | Interna (index.html) | Situação |
|---|---:|---:|---|
| Planejamento Estratégico | não listado como processo separado | 16 etapas | só existe na versão interna |
| Execução Indireta | README: 52 atividades; sem JSON | 46 etapas | recorte do macroprocesso + 7 etapas próprias |
| Execução Direta | 15 etapas (JSON) | 18 etapas | divergência de conteúdo — ver §3 |
| Contratação Direta | 9 etapas (JSON) | 10 etapas | 1 etapa a mais na interna — ver §4 |
| Incorporação de Imóvel | 6 etapas (JSON) | 9 etapas | divergência relevante — ver §5 |

## 2. Execução Indireta — composição da versão interna (46 etapas)

A versão interna é montada em duas partes:

- **39 atividades** extraídas do macroprocesso (52 atividades), apenas dos estágios 3 a 6
  (STAGE_3: 7 · STAGE_4: 9 · STAGE_5: 10 · STAGE_6: 13) — ou seja, os estágios 1 e 2
  (identificação da demanda e planejamento) ficam de fora por pertencerem ao Planejamento
  Estratégico;
- **7 etapas próprias** de pós-licitação: mobilização e execução contratual, acompanhamento
  e fiscalização, entregas parciais/medições/pagamentos, apuração de responsabilidade,
  TRP, conclusão/TRD, e registro de entrega com acionamento da manutenção.

**Ponto a validar:** confirmar que o recorte "estágios 3–6 + pós-licitação" é a regra de
negócio correta e documentá-la; hoje essa composição existe apenas no código.

## 3. Execução Direta — interna (18) × JSON (15)

Etapas com correspondência direta nos dois lados (título idêntico ou equivalente):

- Aprovação da demanda
- Definição da rota de execução direta
- Trilha A — licitação de materiais (JSON: "Processo licitatório para compra de materiais")
- Trilha A — atesto de retirada de material (SEPAT)
- Trilha A — atesto de entrega do material na aldeia
- Trilha B — mão de obra especializada (JSON: "Processo de fornecimento de mão de obra…")
- Trilha C — mão de obra própria/voluntária (JSON: "Plano de execução com mão de obra…")
- Reunião com a comunidade · Ordem de Serviço · Execução e acompanhamento ·
  Relatório situacional mensal · Entrega à comunidade/Termo de Conclusão ·
  Registro de entrega e manutenção

**Só na versão interna (18):**

1. Termo de abertura do processo de gestão e execução
2. Análise preliminar e projeto básico da obra
3. Trilha A — Liquidação, vinculação à obra e liberação
4. **Trilha D — Locação ou compra de equipamentos** ← a "quarta trilha" que não consta do
   README (que descreve apenas as rotas A, B e C)
5. Apuração de responsabilidade (quando houver inadimplemento)

**Só no JSON (15):**

1. Cadastro do estoque e liberação de materiais
2. ART e documentos técnicos

**Ponto crítico a validar (definição nº 2 da revisão):** a Trilha D deve existir? Quais
trilhas podem ser combinadas e quais precisam terminar antes de a obra prosseguir?

## 4. Contratação Direta — interna (10) × JSON (9)

As 9 etapas do JSON têm correspondência exata na versão interna. A interna acrescenta:

- **Tentativa licitatória prévia registrada (quando aplicável)** — etapa opcional.

## 5. Incorporação de Imóvel — interna (9) × JSON (6)

Correspondem nos dois lados: aprovação da demanda/análise de alternativas, processo de
aquisição, regularização patrimonial (SEPAT), destinação aos serviços, manutenção.

**Só na versão interna (9):** registro da doação recebida; projeto da obra doada;
acompanhamento da execução da obra doada; avaliações e diligência documental
(5 grupos de verificação).

**Só no JSON (6):** "Avaliações técnicas, patrimoniais, jurídicas e orçamentárias" —
aparentemente corresponde, em escopo, à etapa interna "Avaliações e diligência documental",
com redação diferente.

**Leitura:** a versão interna cobre adicionalmente o cenário de **doação de obra/imóvel**
(3 etapas opcionais), ausente do JSON.

## 6. Diferenças de estrutura (campos)

| Campo | Versão interna | JSONs de data/ |
|---|---|---|
| `id` estável por etapa | sim | sim (ids diferentes dos internos) |
| `_btype` (tipo BPMN), `_bnote` | sim | não |
| `_track` / `_fork` / `_join` (trilhas paralelas) | sim (Execução Direta) | não |
| `optional` / `optLabel` | sim | parcial |
| `gateway_after` / `loopTarget` | sim | não |
| `_passos` (detalhamento operacional) | sim | sim |

Consequência prática: **importar o JSON não reproduz a versão interna** — faltam os campos
que alimentam a geração BPMN e as trilhas paralelas. A versão interna é hoje a mais completa
estruturalmente; a dos JSONs precisaria ser enriquecida caso seja escolhida como referência.

## 7. O que a equipe precisa decidir

1. **Versão oficial por processo** — interna, JSON ou conciliação (quadros §3–§5 indicam
   item a item o que existe de cada lado);
2. **Execução Direta:** Trilha D (equipamentos) é válida? Combinações e precedências das
   trilhas A/B/C(/D)?
3. **Execução Indireta:** confirmar o recorte estágios 3–6 + 7 etapas de pós-licitação
   como regra documentada;
4. Após a decisão, os dados consolidados devem receber **versão de formato e registro de
   alterações** (CHANGELOG), para que esta divergência não volte a ocorrer.

---
*Gerado por comparação automatizada entre as constantes do `index.html` (rev. `942cf26`) e os
arquivos `data/*.json`; correspondências por igualdade/similaridade de título — revisar os itens
marcados como equivalentes antes de decidir.*
