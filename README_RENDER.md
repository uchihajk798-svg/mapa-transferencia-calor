# INVEST AI API — Render (branch isolada)
A branch `invest-ai-api-render` contém a API FastAPI em `INVEST_AI_backend_source.zip` e o `Dockerfile.render` da raiz.

## Serviços gratuitos criados
- Render Postgres: `invest-ai-db`
- Render Key Value: `invest-ai-cache`
- Web service: `invest-ai-api`

## Variáveis necessárias para produção
Configure no painel Environment do serviço **sem expor credenciais no GitHub**:
- `DATABASE_URL` = endereço **interno** do Postgres, trocando prefixo `postgresql://` para `postgresql+psycopg://`. Guarde credenciais apenas no Render.
- `REDIS_URL` = endereço **interno** (com senha, se necessário) do Key Value, no formato `redis://...`.
- `JWT_SECRET` = segredo forte gerado aleatoriamente, com 48+ caracteres.
- `APP_ENV` = `production`
- `COOKIE_SECURE` = `true`
- `CORS_ORIGINS` = domínio HTTPS autorizado do frontend, separado por vírgulas se necessário.

O backend aborta a inicialização em produção se não houver segredos fortes, cookie seguro ou Redis. A ausência de `DATABASE_URL` faz o código usar SQLite local e NÃO deve ser usada para contas reais porque o disco gratuito do Render é efêmero.

Não confunda deploy do serviço com cadastro funcional. Após configurar variáveis, aguarde deploy `live`, teste `/api/health` e faça cadastro/login em conta de teste.
Recuperação de senha por e-mail continua indisponível sem SMTP configurado.

O banco PostgreSQL do plano gratuito possui data de expiração, que exige acompanhamento antes de receber informações reais de usuários.


## INVEST AI IA generativa (v0.6)
O backend inclui POST /api/ai/explain exigindo sessão autenticada. Sem OPENAI_API_KEY, retorna 503 de maneira explícita. Com variável OPENAI_API_KEY configurada somente no Render, usa Responses API e OPENAI_MODEL (padrão gpt-4.1-mini), store=false, limites de caracteres e autenticação. A API/modelo não está liberada no site público até que backend seguro e conta online sejam validados. O uso da API de IA pode ter custos de fornecedor; não contratar nada automaticamente.

INVEST_AI_backend_source.zip v0.6 contém testes adicionais para rota protegida e configuração ausente.
