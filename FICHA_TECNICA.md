# 📋 FICHA TÉCNICA — Sistema Gestão KPI (PJR / JR Joias)

**Última atualização:** 23/06/2026
**URL do sistema:** https://pjr-gestaokpi.netlify.app

---

## 1. Visão Geral

Sistema PWA (Progressive Web App) único que consolida os **indicadores de desempenho de todos os setores** da JR Joias em um só lugar, com layout de sistema corporativo (menu lateral). Cada setor tem login de **Gestor** e de **Auxiliar(es)**, com metas em três níveis (**Bronze / Prata / Ouro**) e bonificação em R$ por indicador.

- **Tecnologia:** HTML/CSS/JS (arquivo único) + Service Worker (offline) + manifest PWA
- **Banco de dados:** Google Firebase Firestore — projeto `jr-banho` (compartilhado), instância `gestaokpi`
- **Hospedagem:** Netlify — site `pjr-gestaokpi` (conta `jrsistemasinternos@gmail.com`)
- **Tema:** fundo escuro #0A0A0A, dourado #C9A84C

---

## 2. Tipos de Acesso

| Acesso | Quem | Senha padrão | O que vê |
|--------|------|--------------|----------|
| **Gestão Geral** | Ítalo | `admin123` | Todos os 10 setores (visão consolidada) + configurações do sistema |
| **Supervisora** | Daiane | `daiane123` | Apenas **Comercial + Financeiro** (acompanhamento) |
| **Gestor de Setor** | cada gestor | `gestor123` | Indicadores, dashboard, ranking de auxiliares, histórico e config do seu setor |
| **Auxiliar** | cada colaborador | `auxiliar123` | Seus próprios indicadores e histórico |
| **Admin (cadeado 🔒)** | — | `admin123` | Libera a visualização dos valores em R$ |

> Todas as senhas são alteráveis dentro do sistema (Config do setor / Gestão Geral).

---

## 3. Estrutura dos Setores (10 ativos)

> Convenção: o **nome em negrito** é o gestor(a); os demais são auxiliares.

### 1. 🫧 Banho — Gestor: **Ricardo** (auxiliares múltiplos)
Produção Geral, Retrabalho, Erro Banho, Inovação, Checklist, Pl. Desenvolvimento, Controle de Estoque.

### 2. 📋 Cadastro — Gestor: **Arthur** (1 auxiliar)
Erro de Cadastro, Cadastros Realizados, Inovação, Pl. Desenvolvimento, Checklist, Ocorrências, Prazo de Cadastro.

### 3. 📦 Estoque — Gestora: **Adriana** + auxiliar **Rosângela**
5S, Peças Criadas x Validadas, Tempo Médio OS, Qualif. Terceirizado, Checklist, Inovação, Pl. Desenvolvimento, Controle de Estoque, Qualif. Fornecedor.

### 4. 🚪 Portaria/Manutenção — Gestor: **Fernando** (8 indicadores)
5S, Orçamento de Custo, Tarefas no Prazo, Inovação, Checklist, Pl. Desenvolvimento, Reclam. Segurança, Reclam. Manutenção.
**Auxiliares (Segurança, 4 ind.):** Rogerio, George, Dvanildo, Sario Rafael, Rafael (Manutenção), Cicero (T.I).

### 5. 🪨 Estoque Bruto — Gestora: **Maria Stefanny** (9 indicadores)
Lotes Enviados x Qualificadas, Produção x Solicitado, Prazo de Produção, Inovação, Checklist, Pl. Desenvolvimento, Envio de Lotes p/ Banho, Erro Produção, Controle de Estoque.
**Auxiliares (6 ind.):** Georgia, Juliana, Alana, Aila, Raimunda, Eliane, Antonia.

### 6. 📐 Padronização — Supervisora: **Aline** (7 indicadores)
Produção do Setor, Prazo de Entrega, Inovação, Checklist, Pl. Desenvolvimento, Erros no Setor, Qualificação Terceirizado.
**Auxiliares (5 ind.):** Lucilânia, Edmara, Rosilene, Elisangela, Maria, Alonso (Entregador).

### 7. 🔥 Fundição — Gestor: **Jackson** (9 indicadores)
Produção Mensal, Prazo de Produção, Aproveitamento, Peças x Paradas, Inovação, Checklist, Pl. Desenvolvimento, Qualif. Terceirizada, Recuperação de Peças.
**Auxiliares (5 ind.):** Dioges, Antonio Oliveira, Marcos, Ronycleber, José Leonilson, Natanael, Gleydson.

### 8. 🖥️ Recepção — Gestora: **Josineide** (8 indicadores)
Reclam. Limpeza, Cumprimento de Tarefas, Ocorrências Gerais, Inovação, Checklist, Pl. Desenvolvimento, Demandas x Prazo, Checklist (2).
**Dois grupos de auxiliares com indicadores diferentes:**
- *Serviços Gerais (4 ind.):* **Francy, Eliene**
- *Moto Boy (5 ind.):* **Anderson, Felipe Junior**

### 9. 💰 Financeiro (da organização/corporativo) — Gestora: **Daiane** (9 indicadores)
Cumprimento do Faturamento, Pontualidade dos Resumos, Controle Diário de Caixa, Checklist do Setor, Inovação, Checklist, Notas de Serviço em Dias, 5S de Documentos, Pl. Desenvolvimento.
**Dois auxiliares com indicadores diferentes:**
- *Adriano (4 ind.):* Depósito no Prazo, Tempo de Atendimento, Inovação, Checklist Operacional
- *Camila (4 ind.):* Acuracidade do Mascate, Checklist Operacional, Comprovantes, Inovação

### 10. 🛍️ Comercial — Líder/gestora: **Letícia** (10 indicadores)
Meta de Vendas, Meta de Serviços, Inovação, Checklist, Pl. Desenvolvimento, TKM, Conversão Produto, Conversão Serviço, Pesquisa de Satisfação, Programados x Executado.
**Vendedora (auxiliar, 8 ind.):** Suely.

---

## 4. Funcionamento

- **Lançamentos diários** que se agregam no mês (média para % e horas; soma para ocorrências e pontos).
- Cada indicador é avaliado em **Bronze / Prata / Ouro** (ou "Fora" da meta) e gera bonificação em R$.
- **Dashboard** do gestor: bonificação gestor/auxiliar, total pago, indicadores Ouro, status, placar e evolução anual.
- **Ranking de auxiliares**: o gestor vê cada colaborador com suas metas corretas (nos setores com grupos, cada um aparece com a tag do seu grupo).
- **Histórico** mensal e diário por colaborador.
- **API Power BI**: cada setor disponibiliza URL Firestore (gestor e auxiliar) para integração.

---

## 5. Pendências / A Definir

| Item | Setor | Situação |
|------|-------|----------|
| **TKM** | Comercial (gestor e vendedora) | Placeholder R$ 100/150/200 — falta valor real |
| **Meta de Vendas/Serviços** | Comercial | Assumido como % de atingimento (85/90/100) — confirmar |
| **Tempo Médio de Atendimento** | Financeiro (Adriano) | Placeholder horas 36/24/12 — falta valor real |
| **Tempo Produção/Execução** | Fundição (auxiliar) | Placeholder horas 36/24/12 — falta valor real |
| **Indicadores "Definir"** | Padronização | Assumidos como ocorrências (Ouro 0/Prata 2/Bronze 3) |
| **Checklist duplicado** | Recepção (gestora) | Mantido em dobro para fechar R$150/8 ind — confirmar |
| **Financeiro de Vendas** | (novo setor) | NÃO criado — faltam indicadores de **Iana** (gerente) e **Geane** (auxiliar) |

---

## 6. Dados Técnicos (administração)

- **Firebase:** projeto `jr-banho`, instância `gestaokpi`. Coleções por setor/pessoa (`lancamentos_*`) e configs (`senhas_*`, `colaboradores_*`, `metas_*`).
- **Senha supervisora Daiane:** campo `supervisor_daiane` em `config/senhas_geral`.
- **Deploy (Netlify):** API exige **POST** em `/api/v1/sites/{id}/deploys` com ZIP (PUT retorna 404). Site ID: `5de4696e-b3d9-4444-9e34-7070673f17b1`.
- **Arquivos:** `index.html` (sistema completo), `manifest.json`, `sw.js`, `_headers`.
