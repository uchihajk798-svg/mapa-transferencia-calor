# INVEST AI Web — versão provisória 0.4

Repositório original mantido em branch isolada `invest-ai-web`. O arquivo `INVEST_AI_web_source.zip` contém Next.js + TypeScript com modo local: carteira manual, simulador e educação. O workflow `INVEST AI WEB - Validar site` verifica TypeScript e gera `frontend/out`.

Para criar um Render Static Site gratuito:
- Repo: `https://github.com/uchihajk798-svg/mapa-transferencia-calor`
- Branch: `invest-ai-web`
- Build: `unzip -q -o INVEST_AI_web_source.zip && cd frontend && npm install --no-audit --no-fund && npm run build`
- Publish directory: `frontend/out`

O site abre sem login e guarda seus dados apenas no navegador. Cadastro online não está pronto: falta API HTTPS conectada ao PostgreSQL/Redis do Render. Não apresentar carteira local como conta segura na nuvem. Saiba mais no README dentro do zip.
