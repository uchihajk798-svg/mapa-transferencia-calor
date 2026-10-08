# INVEST AI — correção Supabase

Fonte migrada para Supabase Auth + backup privado e Cloudflare Worker opcional. Render continua ativo até a Cloudflare estar validada. Configure NEXT_PUBLIC_SUPABASE_URL e NEXT_PUBLIC_SUPABASE_PUBLISHABLE_KEY (ambas públicas) durante build. As tabelas e RPC foram criadas no projeto Supabase invest-ai. Não usar service_role nem colocar segredos em código. Testar cadastro por e-mail antes do público.
