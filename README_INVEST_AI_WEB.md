# INVEST AI Web v0.6

Site: https://invest-ai-web.onrender.com

**Novidades em produção**
- Radar Mundo: notícias internacionais recentes agregadas pelo GDELT (com veículo original, data, tema e links).
- Indicadores: Meta Selic SGS 432 e IPCA mensal SGS 433 do Banco Central (dependem da disponibilidade da API).
- Assistente financeiro **explicativo e baseado em regras**, com contexto da carteira, moedas e notícias, sem promessas de lucros.
- Carteira local, alertas no site, radar de preço e simulador mantidos.

**Importante:** IA generativa não está habilitada no site estático. Requer API HTTPS com login, servidor seguro e OPENAI_API_KEY. O backend preparado encontra-se na branch invest-ai-api-render. Não deixar chave na web.

Os dados locais ficam somente no navegador. Sem compra e venda na corretora, nem alertas push. Notícias do agregador não possuem checagem editorial independente. Ausência de dados externos é exibida como indisponibilidade.

O ZIP INVEST_AI_web_source.zip contém o código Next.js. No Render:
- Branch: invest-ai-web
- Build command: unzip -q -o INVEST_AI_web_source.zip && cd frontend && npm install --no-audit --no-fund && npm run build
- Publish: frontend/out

Execução dos testes: unzip INVEST_AI_web_source.zip && cd frontend && npm install && npm test && npm run lint && npm run build.
