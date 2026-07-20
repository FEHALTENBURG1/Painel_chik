# Painel Chikungunya RIDE-DF

O painel busca automaticamente o CSV atualizado em:

`https://raw.githubusercontent.com/FEHALTENBURG1/dados_chikungunya/refs/heads/main/dados/chikungunya_ride.csv`

A população municipal usada para calcular incidência é carregada de:

`https://raw.githubusercontent.com/FEHALTENBURG1/dados_chikungunya/refs/heads/main/populacao_ride.csv`

## Funcionamento

- O arquivo `index.html` não contém mais indicadores fixos.
- Ao abrir a página, o navegador baixa o CSV mais recente e recalcula todos os KPIs, gráficos e tabelas.
- O ano corrente é selecionado automaticamente; se não existir, usa o ano epidemiológico mais recente disponível.
- A última semana epidemiológica é obtida da coluna `SE`.
- A URL recebe um parâmetro de atualização e a requisição usa `cache: no-store`, reduzindo o risco de exibir uma versão antiga em cache.

## Publicação

Publique `index.html` e `chart.umd.js` juntos no mesmo diretório do GitHub Pages. O repositório `dados_chikungunya` precisa permanecer público.

## Classificação usada

- Confirmado: `CLASSI_FIN = 13`
- Notificação negativa: `CLASSI_FIN = 5`
- Em investigação: demais valores ou campo vazio
