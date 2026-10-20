# Laudos ETE · Goiás Verde

Painel de controle dos laudos de análise de água e efluentes da unidade de Luziânia-GO.

**Painel:** https://geanfer10.github.io/Laudos-ETE/

## Como funciona

1. Os laudos em PDF do laboratório (Aqualit) são colocados na pasta `01_ENTRADA` do servidor.
2. O **Robô de Laudos** (`robo_laudos.py`, executado no PC da manutenção) lê os PDFs, padroniza os dados, gera a planilha `laudos.xlsx` e o arquivo `laudos.json`.
3. O robô roda sozinho de hora em hora (dias úteis, 7h às 18h) pelo Agendador de Tarefas do Windows e envia para este repositório o `laudos.json` e o `laudos.xlsx` sempre que houver laudo novo.
4. O painel (`index.html`) lê o `laudos.json` e atualiza sozinho.

## O que o painel mostra

- Indicadores da campanha de coleta: amostras, conformidade, parâmetros fora do limite, pontos reprovados e alertas.
- Cards por ponto de coleta, separados em água bruta e água residual.
- Ficha individual de cada ponto: parecer do laboratório, dados da coleta, matriz de resultados e histórico por parâmetro.
- Comparativo de um parâmetro entre os pontos, com a linha do limite da legislação (CONAMA 357 / Resolução 430).
- Tabela completa de resultados com filtros.
- Alertas de consistência encontrados pelo robô nos laudos.

## Arquivos

| Arquivo | Função |
|---|---|
| `index.html` | Painel (GitHub Pages) |
| `laudos.json` | Base de dados gerada pelo robô — não editar à mão |
| `laudos.xlsx` | Planilha completa (Resultados, Amostras, Matriz, Alertas, Log), baixável pelo painel |
