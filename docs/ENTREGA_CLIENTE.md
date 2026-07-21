# 📦 Documento de Entrega — Sistema Gestão KPI (JR Joias)

**Desenvolvido por:** Falcioni Consultoria
**Data:** 23/06/2026

---

## 1. O que é

Sistema web (PWA) para **gestão dos indicadores de desempenho** de todos os setores da JR Joias, com metas em três níveis (Bronze / Prata / Ouro) e bonificação por indicador. Funciona em computador e celular, e pode ser "instalado" como aplicativo.

## 2. Acesso ao sistema

- **Endereço:** https://pjr-gestaokpi.netlify.app
- **Como instalar no celular:** abrir o link no navegador → menu → "Adicionar à tela inicial".

### Perfis de acesso
| Perfil | O que faz |
|--------|-----------|
| **Gestão Geral** | Visão consolidada de todos os setores |
| **Gestor de Setor** | Lança e acompanha os indicadores do seu setor e da sua equipe |
| **Auxiliar / Colaborador** | Lança e acompanha os próprios indicadores |

> As senhas iniciais são entregues separadamente e devem ser trocadas no primeiro acesso.

## 3. Setores incluídos (10)

Banho · Cadastro · Estoque · Portaria/Manutenção · Estoque Bruto · Padronização · Fundição · Recepção · Financeiro · Comercial.

## 4. Recursos

- Lançamentos diários que se consolidam no mês
- Cálculo automático de nível (Bronze/Prata/Ouro) e bonificação
- Dashboard com gráficos, placar e evolução anual
- Ranking de colaboradores por setor
- Histórico mensal e diário
- Integração de dados com Power BI

## 5. Infraestrutura (para a equipe de TI do cliente)

| Item | Plataforma |
|------|------------|
| Hospedagem do app | Netlify |
| Código-fonte | GitHub (repositório `pjr-sistemas/gestaokpi`) |
| Banco de dados | Google Firebase (Firestore) |

> Os dados e o código estão **na nuvem**, não dependem de nenhum computador local.

## 6. Recomendações de segurança (importante)

1. Trocar todas as senhas iniciais por senhas fortes.
2. Revisar as regras de segurança do Firebase.
3. Ativar backup/exportação periódica do banco de dados.
4. (Evolução) Implementar autenticação por usuário (Firebase Authentication).

## 7. Suporte

Manutenções, ajustes de indicadores e novos setores: **Falcioni Consultoria**.
