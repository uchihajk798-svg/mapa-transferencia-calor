# INVEST AI API 0.7 — 100% gratuito na fase beta

Repositório no Render: branch `invest-ai-api-render`.
Serviço: https://dashboard.render.com/web/srv-db421dui0phs73en2gkg
Postgres: https://dashboard.render.com/d/dpg-db414pmb7d7c739vb3u0-a

## Configuração de credenciais PRIVADAS

O backend usa produção fail-closed: **não inicializa se DATABASE_URL for SQLite ou estiver ausente**, impedindo cadastros perdidos no filesystem efêmero do Render Free.

1. No painel Render Postgres → Connect, copie a **Internal Database URL** (nunca inclua na conversa/GitHub).
2. No serviço API → Environment, adicione `DATABASE_URL` com a URL interna PostgreSQL. O programa converte `postgres://` e `postgresql://` automaticamente para psycopg.
3. Já configurados no serviço: `APP_ENV=production`, `COOKIE_SECURE=true`, `CORS_ORIGINS=https://invest-ai-web.onrender.com`, segredo JWT aleatório e Redis interno gratuito.
4. Salve e faça deploy. Teste `/api/health`: só deve ficar OK com DB e Redis disponíveis.
5. IA gratuita opcional: `GEMINI_API_KEY` emitida pelo **Google AI Studio Free Tier sem ativar billing** (https://aistudio.google.com/api-keys). Sem chave a IA generativa responde 503. **OpenAI API paga NÃO será usada**.
6. Limite Gemini: 12 perguntas por usuário/dia, com Redis. Nunca copie chaves para frontend e não habilite cartão ou pagamento.
7. Banco gratuito tem validade de 30 dias a partir de 2026-10-08: manter backup e migrar antes de 2026-11-07.

Endpoint para conta mobile/bearer: `/api/mobile/auth/register` e `/api/mobile/auth/login`, com acesso por 15 minutos e sem token persistido no navegador. Backup individual: `/api/me/cloud-backup` com revisão otimista. Segue sem e-mail de recuperação. Banco e Redis são necessários para segurança e durabilidade.

As etapas de deploy da API podem falhar enquanto a conexão DATABASE_URL não for configurada. **Isso é proposital: não aceitar contas que serão perdidas.**


Health v0.7.0 publica `persistent_storage=true` exclusivamente quando o servidor está usando PostgreSQL. O site exige essa confirmação antes de habilitar contas.
