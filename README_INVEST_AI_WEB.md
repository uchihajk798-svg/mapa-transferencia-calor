# INVEST AI — atualização v0.7.2 (Supabase Auth + carteira)
Deploy: Render Static Site (branch invest-ai-web), mantendo a mesma URL https://invest-ai-web.onrender.com
O arquivo INVEST_AI_web_source.zip é a versão completa, contendo frontend Next.js para build e Cloudflare Worker para futura migração.

## Render: configurar somente variáveis públicas
NEXT_PUBLIC_SUPABASE_URL=https://dpsctcnnuffojiufgbic.supabase.co
NEXT_PUBLIC_SUPABASE_PUBLISHABLE_KEY=chave publishable pública obtida no painel do Supabase
NEXT_PUBLIC_WORKER_AI_ENABLED não definir no Render (Worker da IA ainda não publicado).

O cadastro e backup utilizam Supabase Auth com políticas RLS. E-mail de confirmação precisa ter Site URL/Redirect URLs alinhados com o domínio Render.
Backup só com botão Salvar/Restaurar e controle de revisão. A carteira anterior do localStorage não é apagada.
O serviço antigo FastAPI do Render NÃO integra com esta autenticação, e pode ficar desativado; nunca colocar service_role no bundle. IA educativa local continua grátis; botão do Gemini oculto enquanto o Worker não estiver publicado e com chave gratuita.
