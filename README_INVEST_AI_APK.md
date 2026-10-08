# INVEST AI Mobile v0.3 — carteira local mais funcional

A branch é exclusiva do APK para testes. **Não mesclar ao projeto de física da branch main**.

Esta versão **não habilita cadastro/login online**: a API FastAPI ainda não foi publicada. Em vez de mostrar um cadastro impossível, abre um modo local com carteira manual, compras, vendas, preço médio, histórico, dados persistidos no Android, lista de acompanhamento, Academia e simulador. Preços de criptomoedas e Selic são consultados diretamente em provedores externos e podem estar indisponíveis. **Os dados locais não estão criptografados nem sincronizados com um servidor**.

A compilação acontece no GitHub Actions, arquivo .github/workflows/invest-ai-apk.yml; depois do status verde, baixe o artifact INVEST_AI_MOBILE_APK.

Pendente: backend HTTPS, banco Postgres, notificações, IA conversacional, radar e avaliação em dispositivo real. Não executar ordens financeiras.
