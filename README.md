# n8n-projects
Projetos práticos de automação com n8n — clima, inventário e sistema de aprovação

# README criado com auxílio e IA

# 🤖 Portfólio de Automações — n8n

Projetos práticos desenvolvidos durante o aprendizado de automação com **n8n**, rodando localmente via Docker.

Cada projeto foi construído do zero, cobrindo conceitos progressivos de automação: APIs, webhooks, integrações com Google Sheets, Telegram e Gmail.

---

## 📁 Projetos

| Projeto | Nível | Descrição |
|---|---|---|
| [🌧️ Carinha do Clima](./clima/) | Iniciante | Monitor de clima com alerta de chuva via Telegram |
| [📦 Pipeline de Inventário](./inventario/) | Intermediário | Leitura, agrupamento e relatório de estoque no Google Sheets |
| [✅ Sistema de Aprovação](./aprovacao/) | Avançado | Fluxo de solicitação com aprovação via webhook e notificação por Gmail |

---

## 🛠️ Tecnologias utilizadas

- [n8n](https://n8n.io) — plataforma de automação low-code
- Docker — ambiente local de execução
- Google Sheets — armazenamento e relatórios
- Gmail — notificações por e-mail
- Telegram Bot API — alertas em tempo real
- wttr.in — API pública de previsão do tempo
- Webhook (n8n Wait node) — fluxos com aprovação humana

---
4. Configure as credenciais necessárias (Telegram, Google, Gmail)
