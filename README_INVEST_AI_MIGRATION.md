# INVEST AI — Cloudflare + Supabase (preparação de migração)

Esta branch está isolada: nenhum código de produção foi alterado, nenhum plano pago contratado.

* Código e instruções: `INVEST_AI_CLOUDFLARE_SUPABASE_PREVIEW.zip`.
* Cloudflare Workers: hospeda Next.js export + API dinâmica `/api/ai/explain`.
* Supabase Free: autenticação + backup privado por usuário via Postgres RLS e função SQL de versão.
* Gemini opcional: chave secreta guardada apenas no Worker, cota de 12 perguntas/dia/usuário.
* Sem chaves ou projetos conectados, a migração fica em modo de preparação; o site de produção https://invest-ai-web.onrender.com continua no Render.

**Antes de publicar**: conectar Supabase, criar projeto Free, executar migração SQL, inserir URL/chave publishable públicas no build e no Worker, testar RLS entre duas contas e só então autorizar Cloudflare. Veja o README dentro do ZIP.
