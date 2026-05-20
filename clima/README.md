# README criado com auxílio de IA

# 🌧️ Carinha do Clima

Monitor de clima automatizado que verifica a previsão do tempo em Recife toda manhã e envia um alerta no Telegram caso a chance de chuva ultrapasse o limite configurado.

---

## 🎯 Problema que resolve

Evitar ser pego de surpresa pela chuva — o bot avisa automaticamente às 7h se vale a pena levar o guarda-chuva.

---

## ⚙️ Como funciona

```
Schedule (7h) → Configurações → HTTP Request (wttr.in) → Tratamento de dados → IF
                                                                                 ├── chuva > 65% → Mensagem de alerta → Telegram
                                                                                 └── chuva ≤ 65% → Mensagem tranquila → Telegram
```

1. Todo dia às 7h o workflow dispara automaticamente
2. Busca a previsão do tempo via API pública do wttr.in
3. Extrai temperatura, sensação térmica, chance de chuva e descrição
4. Compara a chance de chuva com o limite configurado (65%)
5. Envia mensagem personalizada no Telegram — alerta ou tranquilidade

---

## 🛠️ Tecnologias

- **n8n** — orquestração do fluxo
- **wttr.in** — API pública de clima (sem cadastro, sem custo)
- **Telegram Bot API** — envio das notificações

---

## 💡 O que aprendi

- Consumir APIs públicas com o nó HTTP Request
- Extrair campos de JSON aninhado
- Usar o nó IF para bifurcar o fluxo com base em condições numéricas
- Centralizar configurações em um nó Set (cidade, chat ID, limite)
- Agendar execuções com o Schedule Trigger

---

## 📸 Exemplo de mensagem

```
⚠️ ALERTA DE CHUVA em Recife!
🌧️ Chance de chuva: 100%
🌡️ Temperatura: 25°C
👕 Sensação térmica: 27°C
📋 Condição: Chuva fraca nas proximidades

Leve o guarda-chuva hoje!
```
