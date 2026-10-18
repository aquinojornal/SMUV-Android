# SMUV Android — projeto inicial Kotlin

**Status:** código-fonte inicial, NÃO compilado neste ambiente. Ainda não é um APK de produção.

## Pré-requisitos no Windows
- Android Studio (para instalar Android SDK API 35, Build Tools e emulador) ou Android SDK Command Line Tools
- JDK 17
- Gradle 8.9 (ou wrapper Gradle 8.9 gerado localmente)
- Internet para baixar dependências Maven/Google

## Compilar no VS Code
1. Extraia o ZIP em uma pasta, por exemplo `C:\Projetos\SMUV`.
2. Instale JDK 17 e Android SDK com API 35; configure `ANDROID_HOME`.
3. Instale Gradle 8.9 e execute `gradle wrapper --gradle-version 8.9` na pasta do projeto.
4. Execute `./gradlew.bat assembleDebug` no PowerShell.
5. APK esperado: `app\build\outputs\apk\debug\app-debug.apk` (somente após compilação bem-sucedida).

## Integração real
A API de produção aceita `https://www.smlu.com.br/?rest_route=/smlu-mobile/v1/bootstrap` (HTTP 200 confirmado pelo usuário). URLs `/wp-json/` retornaram 404.
Login é feito por `POST ?rest_route=/smlu-mobile/v1/login` com JSON `{ "username": "...", "password": "..." }`; token Bearer retornado em `token`.

## Limitações atuais
- Primeira base visual e funcional: Splash, Login, Home, consulta de protocolos, rotas, cronogramas e notificações.
- Bota-Fora e Ouvidoria ainda precisam de formulários de envio reais, portanto seus cartões atualmente levam à consulta de protocolos como navegação provisória. Não há simulação de envio.
- Sem armazenamento persistente de sessão (token permanece apenas em memória).
- Sem Google Maps, upload de fotos, OneSignal, notificações push ou rastreamento em tempo real.
- Layout inicial inspirado nas imagens; não validado pixel a pixel.
- O projeto ainda requer validação de compilação e testes no Android.
