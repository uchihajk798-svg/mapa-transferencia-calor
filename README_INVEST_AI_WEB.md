# INVEST AI Web v0.7 — IA gratuita e backup de conta
- Site: https://invest-ai-web.onrender.com
- API preparada: https://invest-ai-api-web.onrender.com
- Cadastro online e backup por conta via /api/mobile/auth e /api/me/cloud-backup com tokens temporários em memória, **só disponíveis quando a API tiver PostgreSQL real**.
- Sem cobrança: modo IA educativa por regras sempre gratuito; Gemini Flash-Lite só com chave Google AI Studio Free Tier sem billing, limite 12 perguntas/conta/dia. Não ativar OpenAI API paga.
- Não existe sync automático: ações explícitas Salvar e Restaurar com controle de versão.
- Expiração Postgres gratuito: 2026-11-07. Faça backups.
- Para build Render: unzip -q -o INVEST_AI_web_source.zip && cd frontend && npm install --no-audit --no-fund && npm run build
- Publish: frontend/out
- NEXT_PUBLIC_API_URL=https://invest-ai-api-web.onrender.com (pública, não é segredo).
