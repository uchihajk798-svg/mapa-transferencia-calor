# INVEST AI Web v0.5
Atualização da versão web com radar de variações baseado em cotações reais do CoinGecko, alertas no próprio site, lista de acompanhamento, concentração por classe, validação de backup e perfil local.

## Disponibilidade
Site: https://invest-ai-web.onrender.com
Hospedado no Render Static Site (branch `invest-ai-web`). Não há backend de login publicado.

## Como executar localmente
`unzip INVEST_AI_web_source.zip`
`cd frontend && npm install && npm run test && npm run lint && npm run build`

## Limitações reais
- Dados financeiros são registrados apenas no localStorage do navegador, não sincronizados em conta.
- Os preços públicos podem ficar indisponíveis ou atrasados. O radar exige timestamp válido e recente.
- Avisos funcionam só dentro do site aberto. Sem push e sem processamento em background.
- O cálculo de concentração é baseado em custo de compra, não patrimônio atualizado.
- Análises da IA e inteligência geopolítica permanecem pendentes. Não são promessas ou recomendações.
- Antes de produção com usuários reais, criar backend persistente e seguro, migrar dados e ajustar conformidade com LGPD/CVM.
