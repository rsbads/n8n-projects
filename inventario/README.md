# README criado com auxílio de IA

# 📦 Pipeline de Inventário

Pipeline de processamento de dados que lê um inventário de produtos no Google Sheets, agrupa por categoria, calcula totais e gera um relatório consolidado em outra aba da planilha.

---

## 🎯 Problema que resolve

Eliminar o trabalho manual de consolidar e resumir dados de estoque — o pipeline processa tudo automaticamente e atualiza o relatório com um clique.

---

## ⚙️ Como funciona

```
Manual Trigger → ID Planilha → Sheets (leitura) → Sort (categoria) → Aggregate → Code (agrupamento) → Sheets (relatório)
```

1. Disparado manualmente com um clique
2. Lê todos os produtos da aba "Inventário"
3. Ordena alfabeticamente por categoria
4. Agrega todos os itens em um único objeto
5. Executa código JavaScript para agrupar por categoria e calcular totais
6. Grava o relatório consolidado na aba "Relatório" (append or update)

---

## 🛠️ Tecnologias

- **n8n** — orquestração do fluxo
- **Google Sheets** — fonte de dados e destino do relatório
- **JavaScript** (nó Code) — lógica de agrupamento por categoria

---

## 💡 O que aprendi

- Ler e escrever dados no Google Sheets via OAuth2
- Usar o nó Sort para ordenar itens
- Usar o nó Aggregate para consolidar múltiplos itens
- Escrever lógica de agrupamento com o nó Code em JavaScript
- Usar "Append or Update" para não duplicar dados no relatório

---

## 📊 Exemplo de saída (aba Relatório)

| Categoria | Total_Itens | Quantidade_Total |
|---|---|---|
| Eletrônicos | 5 | 48 |
| Móveis | 3 | 12 |
| Periféricos | 4 | 30 |
