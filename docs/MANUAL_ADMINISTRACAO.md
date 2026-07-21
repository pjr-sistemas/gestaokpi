# 🛠️ Manual de Administração — Sistema Gestão KPI (JR Joias)

> Documento de transferência de administração. Contém **acessos e credenciais** — guarde com segurança e troque as senhas/tokens após assumir.
> Desenvolvido por Falcioni Consultoria · 23/06/2026

---

## 1. As 3 plataformas que sustentam o sistema

O app vive em 3 serviços na nuvem. Para administrar, é preciso ter acesso aos três:

| # | Plataforma | Para que serve | Endereço |
|---|-----------|----------------|----------|
| A | **Netlify** | Hospeda o app (coloca no ar) | https://app.netlify.com |
| B | **GitHub** | Guarda o código-fonte | https://github.com/pjr-sistemas/gestaokpi |
| C | **Firebase (Google)** | Banco de dados (lançamentos, metas, senhas) | https://console.firebase.google.com |

---

## 2. Contas e acessos atuais

### A) Netlify
- **Conta:** jrsistemasinternos@gmail.com
- **Site:** pjr-gestaokpi
- **URL pública:** https://pjr-gestaokpi.netlify.app
- **Site ID:** 5de4696e-b3d9-4444-9e34-7070673f17b1
- **Painel:** https://app.netlify.com/projects/pjr-gestaokpi

### B) GitHub
- **Organização:** pjr-sistemas
- **Usuário:** SistemasClaude
- **Repositório:** https://github.com/pjr-sistemas/gestaokpi
- **Token de acesso:** (entregue separadamente / deve ser regenerado pelo novo administrador)

### C) Firebase
- **Projeto:** jr-banho
- **Banco:** Firestore
- ⚠️ **Atenção:** este projeto Firebase é **compartilhado** por outros apps da JR Joias (JR Banho, Cadastro, Estoque). Ao administrar, cuidado para não mexer nas coleções dos outros apps.

---

## 3. Senhas internas do sistema (uso diário)

| Acesso | Senha inicial | Onde trocar |
|--------|---------------|-------------|
| Gestão Geral (Ítalo) | `admin123` | Dentro do app → Gestão Geral → Config |
| Gestor de cada setor | `gestor123` | App → setor → Config → Senhas |
| Auxiliar de cada setor | `auxiliar123` | App → setor → Config → Senhas |
| Cadeado de valores (R$) | `admin123` | (mesma config) |

> **Troque todas no primeiro acesso.** As senhas ficam guardadas no Firebase (coleções `senhas_*`).

---

## 4. Como ATUALIZAR o app (publicar mudanças)

O código é um arquivo principal: `index.html`. O fluxo para publicar uma alteração:

1. Editar o `index.html` (ex.: mudar uma meta, adicionar setor).
2. Subir para o GitHub (commit + push).
3. Publicar no Netlify (deploy).

**Forma simples (sem programar):** entrar no painel do Netlify → site pjr-gestaokpi → aba **Deploys** → arrastar a pasta do projeto para fazer um novo deploy ("Drag and drop").

**Forma técnica (linha de comando):** compactar a pasta em .zip e enviar via API do Netlify usando **POST** em `/api/v1/sites/{SITE_ID}/deploys` (atenção: PUT não funciona, retorna 404).

---

## 5. Como mexer nos DADOS / INDICADORES

- **Metas e senhas de cada setor:** direto no app, na aba **Config** do gestor.
- **Nomes de gestores e auxiliares:** app → Gestão Geral, ou Config do setor.
- **Estrutura de indicadores (criar/remover indicador, novo setor):** exige editar o `index.html` (objeto `SD` no código). Recomenda-se apoio técnico.
- **Dados brutos (lançamentos):** ficam no Firebase, coleções `lancamentos_*`. Podem ser vistos/exportados pelo console do Firebase.

---

## 6. Integração com Power BI

Cada setor disponibiliza uma URL de leitura do Firestore (vista na aba Config → API do gestor). Use-a como fonte de dados no Power BI.

---

## 7. Recomendações ao assumir a administração

1. **Transferir a propriedade das contas** para o cliente (Netlify, GitHub, Firebase) — não apenas compartilhar senhas.
2. **Regenerar tokens** (GitHub e Netlify) após a transferência.
3. **Trocar todas as senhas internas** do sistema.
4. **Revisar as regras de segurança do Firebase** (Firestore → Rules).
5. **Ativar backup automático** do Firestore.
6. (Evolução) **Login por usuário** via Firebase Authentication, para segurança real.

---

## 8. Suporte e evolução

Novos setores, ajustes de indicadores e melhorias: **Falcioni Consultoria**.
