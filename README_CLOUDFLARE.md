# INVEST AI — Cloudflare Workers + Supabase (Free)

## Projeto pronto para importar na Cloudflare
* Site atual: https://invest-ai-web.onrender.com (não será desligado automaticamente).
* Branch exclusiva do Cloudflare: `invest-ai-cloudflare`
* Nome exato do Worker: `invest-ai-web`
* O código-fonte está em `INVEST_AI_web_source.zip`, e o build extrai para `frontend/`.
* A configuração raiz `wrangler.jsonc` aponta para o código do Worker e para os arquivos estáticos Next.js exportados. O frontend lê a chave **publishable** do Supabase via `cloudflare.public.env`. Ela é pública por definição; NENHUMA service_role ou senha privada está presente.

### Na Cloudflare
1. Faça login em https://dash.cloudflare.com/ e escolha o plano **Workers Free**; não assine Workers Paid.
2. Workers & Pages > Create application > Import a repository > GitHub. Autorize o repositório `uchihajk798-svg/mapa-transferencia-calor`.
3. Escolha a branch de produção `invest-ai-cloudflare`. O nome do Worker tem de ser exatamente **invest-ai-web** (igual ao campo name do wrangler.jsonc).
4. Root directory: `/` (raiz, deixe padrão).
5. **Build command:** `npm install --no-audit --no-fund && npm run build`.
6. **Deploy command:** `npx wrangler deploy`.
7. Salve e implante; aguarde `Success`. Endereço final será informado pela Cloudflare no domínio *.workers.dev. NÃO suponha o endereço antes de ser criado.
8. Teste a página inicial e `https://SEU-SUBDOMINIO.workers.dev/api/health`. health deve retornar status ok e auth_configured true; ai_enabled false é esperado.
9. Supabase > Authentication > URL Configuration: adicione **a URL exata** Cloudflare que foi gerada nas URLs de redirecionamento e configure Site URL para a URL Cloudflare somente após validar. Confirme o e-mail de registro e teste logins/backup.
10. A opção IA generativa está inativa. Futuramente, adicione GEMINI_API_KEY como **Secret** somente se houver uma chave gratuita sua. Não coloque nenhuma chave em GitHub, chat ou NEXT_PUBLIC.

### Sem custos
Workers Free tem cotas; requisições acima dos limites podem falhar. Supabase Free também tem cotas e suspensão por inatividade. Não ativar faturamento. Não apagar Render antes de confirmar todos os testes.

### Como reproduzir o build local
```sh
npm install --no-audit --no-fund
npm run build
npm run validate
```
