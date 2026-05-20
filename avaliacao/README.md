# README criado com auxílio de IA

# ✅ Sistema de Solicitação com Aprovação

Fluxo completo de solicitação de compra com aprovação humana — o solicitante preenche um formulário, o aprovador recebe os detalhes no Telegram com links de aprovação/rejeição, e o resultado é notificado por Gmail e registrado no Google Sheets.

---

## 🎯 Problema que resolve

Substituir aprovações feitas por mensagens informais (WhatsApp, e-mail manual) por um fluxo estruturado, rastreável e com registro automático.

---

## ⚙️ Como funciona

```
Formulário → Edit Fields → Telegram (notifica aprovador + links) → Wait (webhook)→ Switch
                                                                                    ├── aprovado → Gmail ✅ → Sheets
                                                                                    └── rejeitado → Gmail ❌ → Sheets
```

1. Solicitante preenche o formulário (nome, item, quantidade, justificativa)
2. Os dados são normalizados e o status inicial "Pendente" é atribuído
3. O Telegram envia os detalhes ao aprovador com dois links: aprovar e rejeitar
4. O fluxo pausa no nó Wait aguardando o clique em um dos links (webhook GET)
5. O Switch roteia com base no parâmetro `?aprovacao=aprovado` ou `?aprovacao=rejeitado`
6. O Gmail notifica o solicitante com o resultado
7. O Google Sheets registra a solicitação com o status final

---

## 🛠️ Tecnologias

- **n8n** — orquestração do fluxo
- **n8n Form** — formulário de solicitação
- **Telegram Bot API** — notificação do aprovador
- **n8n Wait node** — pausa do fluxo aguardando aprovação humana via webhook
- **Gmail** — notificação do solicitante
- **Google Sheets** — registro histórico das solicitações

---

## 💡 O que aprendi

- Criar formulários nativos com o nó Form do n8n
- Usar o nó Wait no modo "On Webhook Call" para pausar o fluxo aguardando input humano
- Entender como a `$execution.resumeUrl` funciona e como passá-la como link
- Rotear fluxos com o nó Switch baseado em query params (`$json.query.aprovacao`)
- Integrar Gmail com OAuth2 e montar e-mails em HTML
- Mapear campos manualmente no Google Sheets para evitar gravar dados do nó errado

---

## 📋 Exemplo de mensagem no Telegram

```
🔔 Nova solicitação de compra!
👤 Solicitante: Rafael
📦 Item: RTX 5070 TI
🔢 Quantidade: 1
📋 Justificativa: Para estudo
📅 Data: 20 05 2026 - 02:44

Para APROVAR clique: https://...&aprovacao=aprovado
Para REJEITAR clique: https://...&aprovacao=rejeitado
```
