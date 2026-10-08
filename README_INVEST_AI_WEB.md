# INVEST AI Web 0.5.1

Site publicado: https://invest-ai-web.onrender.com

Modo local sem cadastro. Radar educacional de variações de preços com fonte CoinGecko, alertas na página, watchlist, carteira manual, distribuição por custo de aquisição, simulador, educação, backup JSON e perfil local.

**Importante:** NÃO há conta online e sincronização até que a API FastAPI com PostgreSQL e Redis seja publicada e verificada. Alertas não são push. Cotações podem ser indisponíveis/atrasadas. O radar não é previsão nem recomendação.

`unzip INVEST_AI_web_source.zip && cd frontend && npm install && npm test && npm run lint && npm run build`

Patch 0.5.1: preserva os dados originais do navegador quando encontra uma versão inválida ou inconsistente, evitando sobrescrita automática.
