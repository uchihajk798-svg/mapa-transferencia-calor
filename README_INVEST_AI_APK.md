# INVEST AI Mobile — APK Android

Este ramo `invest-ai-mobile-apk` contém o código-fonte mobile no arquivo `INVEST_AI_mobile_source.zip` e o GitHub Actions para compilar um **APK release instalável** (assinado com chave de teste, não apropriada para publicação na Play Store). O projeto principal do repositório na branch `main` não foi alterado por este processo, exceto pelo arquivo de teste de permissão criado anteriormente.

No GitHub, abra **Actions → INVEST AI - Compilar APK Android**. Veja a execução disparada pelo push; se o workflow não iniciar automaticamente, use **Run workflow** escolhendo a branch `invest-ai-mobile-apk`.

Se a execução terminar com êxito, entre em **Artifacts** e baixe `INVEST_AI_MOBILE_APK`, que contém o arquivo `app-release.apk`.

Observação: Sem configurar o backend em HTTPS e `EXPO_PUBLIC_API_URL`, o app disponibiliza somente funcionalidades locais como conteúdos educativos e simulador. Este é um APK para TESTES, não uma versão de produção nem uma recomendação de investimento.
