# Estudos do Flutter

Neste estudo, estou buscando compreender o ponto inicial mais crucial para a apresentação de uma estrutura de pastas. Isso pode parecer algo simples, mas ao longo do projeto e à medida que ele cresce, torna-se cada vez mais impossível não dar atenção a esse aspecto. Ao observar pessoas trabalhando e realizando commits devido à velocidade e exigências de entrega, muitas vezes a organização do projeto é deixada em segundo plano. Durante meus estudos no Flutter, não encontrei uma abordagem clara e explícita para uma estrutura adequada em projetos corporativos, que permita crescimento sem preocupações com desorganização. Este é um ponto crucial.

## Introdução

Neste ponto, vou explicar a estrutura básica conforme é configurada no início do projeto Flutter, e como as pastas estão organizadas. Vale ressaltar que este artigo pode tornar-se obsoleto com o tempo, à medida que o framework evolui e amadurece. Na época em que escrevi este artigo, a estrutura de pastas estava da seguinte forma:

```shell
.
├── analysis_options.yaml
├── android
│   ├── app
│   │   ├── build.gradle
│   │   └── src
│   ├── app_flutter_android.iml
│   ├── build.gradle
│   ├── gradle
│   │   └── wrapper
│   ├── gradle.properties
│   ├── gradlew
│   ├── gradlew.bat
│   ├── local.properties
│   └── settings.gradle
├── app_flutter.iml
├── build
├── ios
│   ├── Flutter
│   │   ├── AppFrameworkInfo.plist
│   │   ├── Debug.xcconfig
│   │   ├── flutter_export_environment.sh
│   │   ├── Generated.xcconfig
│   │   └── Release.xcconfig
│   ├── Runner
│   │   ├── AppDelegate.swift
│   │   ├── Assets.xcassets
│   │   ├── Base.lproj
│   │   ├── GeneratedPluginRegistrant.h
│   │   ├── GeneratedPluginRegistrant.m
│   │   ├── Info.plist
│   │   └── Runner-Bridging-Header.h
│   ├── RunnerTests
│   │   └── RunnerTests.swift
│   ├── Runner.xcodeproj
│   │   ├── project.pbxproj
│   │   ├── project.xcworkspace
│   │   └── xcshareddata
│   └── Runner.xcworkspace
│       ├── contents.xcworkspacedata
│       └── xcshareddata
├── lib
│   ├── main.dart
├── linux
│   ├── CMakeLists.txt
│   ├── flutter
│   │   ├── CMakeLists.txt
│   │   ├── ephemeral
│   │   ├── generated_plugin_registrant.cc
│   │   ├── generated_plugin_registrant.h
│   │   └── generated_plugins.cmake
│   ├── main.cc
│   ├── my_application.cc
│   └── my_application.h
├── macos
│   ├── Flutter
│   │   ├── ephemeral
│   │   ├── Flutter-Debug.xcconfig
│   │   ├── Flutter-Release.xcconfig
│   │   └── GeneratedPluginRegistrant.swift
│   ├── Runner
│   │   ├── AppDelegate.swift
│   │   ├── Assets.xcassets
│   │   ├── Base.lproj
│   │   ├── Configs
│   │   ├── DebugProfile.entitlements
│   │   ├── Info.plist
│   │   ├── MainFlutterWindow.swift
│   │   └── Release.entitlements
│   ├── RunnerTests
│   │   └── RunnerTests.swift
│   ├── Runner.xcodeproj
│   │   ├── project.pbxproj
│   │   ├── project.xcworkspace
│   │   └── xcshareddata
│   └── Runner.xcworkspace
│       ├── contents.xcworkspacedata
│       └── xcshareddata
├── pubspec.lock
├── pubspec.yaml
├── README.md
├── test
├── web
│   ├── favicon.png
│   ├── icons
│   │   ├── Icon-192.png
│   │   ├── Icon-512.png
│   │   ├── Icon-maskable-192.png
│   │   └── Icon-maskable-512.png
│   ├── index.html
│   └── manifest.json
└── windows
    ├── CMakeLists.txt
    ├── flutter
    │   ├── CMakeLists.txt
    │   ├── ephemeral
    │   ├── generated_plugin_registrant.cc
    │   ├── generated_plugin_registrant.h
    │   └── generated_plugins.cmake
    └── runner
        ├── CMakeLists.txt
        ├── flutter_window.cpp
        ├── flutter_window.h
        ├── main.cpp
        ├── resource.h
        ├── resources
        ├── runner.exe.manifest
        ├── Runner.rc
        ├── utils.cpp
        ├── utils.h
        ├── win32_window.cpp
        └── win32_window.h
```

Como podemos observar, existem várias pastas. Vou destacar aquelas voltadas para a implementação da estrutura para a execução do código Dart e onde ele será executado em suas respectivas plataformas:

1. A pasta `android` é destinada ao desenvolvimento específico para o sistema operacional Android. Nela, encontramos o código-fonte necessário para a construção e execução do aplicativo em dispositivos Android. Essa seção engloba desde configurações de compilação até implementações específicas para a integração com o sistema operacional.

2. Na pasta `ios`, concentram-se todos os artefatos relacionados à execução do aplicativo em dispositivos iOS, abordando aspectos cruciais para a interoperabilidade com o ecossistema da Apple. Isso inclui configurações do projeto, integração de plugins específicos do iOS e ajustes necessários para otimização de desempenho e experiência do usuário.

3. A pasta `macos` é dedicada ao suporte experimental para a execução da aplicação em desktops com macOS. Este é um projeto em constante evolução, visando proporcionar uma experiência nativa e eficiente para usuários de computadores Apple. Aqui, são consideradas particularidades do ambiente desktop, como tratamento de janelas e interações com periféricos específicos.

4. Em `linux`, exploramos a capacidade do Flutter de se estender aos sistemas operacionais baseados em Linux. Esta seção é crucial para o desenvolvimento de aplicações desktop em ambientes Linux, aproveitando as peculiaridades desse ecossistema e garantindo uma experiência otimizada para os usuários Linux.

5. A pasta `windows` engloba todas as configurações e implementações necessárias para a execução da aplicação em sistemas operacionais Microsoft, com foco principal no Windows. Aspectos como a integração com a interface do usuário do Windows, suporte a dispositivos específicos e otimizações de desempenho são contemplados aqui.

6. A pasta `build` é fundamental para a construção da aplicação, armazenando todos os artefatos resultantes do processo de compilação. Isso inclui os executáveis finais para cada plataforma suportada, bem como outros recursos compilados essenciais para a execução do aplicativo.

7. Adicionalmente, a pasta `web` é um projeto específico para o desenvolvimento de aplicações web usando o Flutter. Este ambiente oferece uma abordagem singular, permitindo que o código Flutter seja executado no navegador, proporcionando uma experiência de desenvolvimento consistente entre aplicações móveis e web. Este projeto destaca-se pela versatilidade e eficácia na criação de interfaces ricas e dinâmicas para a web.

Terminando esta seção sobre as pastas, vamos analisar agora os arquivos que estão no primeiro nível do diretório:

1. `analysis_options.yaml`: Este arquivo contém opções de análise estática do código, proporcionando configurações específicas para ferramentas de análise.

2. `app_flutter.iml`: Este arquivo é gerado automaticamente pelo IntelliJ IDEA, sendo usado para armazenar configurações específicas do projeto.

3. `pubspec.lock`: Este arquivo trava as versões exatas das dependências utilizadas no projeto Flutter, garantindo a consistência entre diferentes instalações.

4. `pubspec.yaml`: Este arquivo é fundamental e contém as configurações do projeto, incluindo as dependências, nome do aplicativo, versão, entre outras informações.

5. `README.md`: Este arquivo contém a documentação principal do projeto, fornecendo informações sobre sua finalidade, como configurar e executar, além de outras orientações importantes.

Além desses arquivos, é importante mencionar que o Flutter pode gerar outros arquivos automaticamente durante o desenvolvimento.

## Pasta Lib

Tratamos dos arquivos padrão; agora, abordaremos duas partes essenciais deste artigo: a pasta `lib` e, ao final, destacaremos a seção de testes. Inicialmente, concentraremos nossa análise na pasta `lib`, pois a estrutura adotada aqui será refletida na organização da pasta de testes. Esta abordagem não implica em uma simples cópia e colagem, mas sim em uma similaridade estrutural. A razão por trás dessa abordagem é facilitar a localização rápida e eficiente dos testes relacionados a um determinado código, proporcionando uma visão pragmática e sem demoras excessivas. Afinal, o objetivo dos testes é compreender o código, não perder tempo procurando onde determinadas funcionalidades estão implementadas.

A seguir, apresentaremos uma possível estrutura dentro da pasta `lib`:

- **`lib/`**
  - **`src/`**: Esta subpasta abriga o código-fonte principal da aplicação. É comum ter um diretório `src` para diferenciar o código específico da aplicação de outros recursos.
    - **`widgets/`**: Contém widgets personalizados reutilizáveis em diferentes partes da aplicação, promovendo a modularidade e a manutenção simplificada.
    - **`screens/`**: Aqui ficam as diferentes telas (ou páginas) da aplicação, cada uma em seu próprio arquivo para facilitar a manutenção e a compreensão.
    - **`models/`**: Esta seção engloba as classes de modelo que representam dados na aplicação. Manter essas classes organizadas facilita a gestão e a evolução do modelo de dados.
    - **`services/`**: Inclui classes responsáveis por serviços específicos, como chamadas de API, gerenciamento de estado global, entre outros.
  - **`main.dart`**: O ponto de entrada principal da aplicação, onde é feita a inicialização e configuração do Flutter.
  - **`constants.dart`**: Arquivo para armazenar constantes utilizadas em toda a aplicação, proporcionando uma centralização desses valores.

Esta estrutura é projetada para promover a modularidade e a clareza no desenvolvimento, tornando a aplicação mais fácil de entender e manter. A organização por funcionalidade facilita a localização de código relacionado, contribuindo para um código mais limpo e eficiente.

Muito interessante essa organização que apresentei, de fato para um projeto pequeno faça sentido, ao logo dos anos e minha experiência sempre me deparei com estruturas onde components ficavam na mesma pasta e isso ao logo do tempo quando iria crescendo ficava cada vez mais, que trabalhando com java é bastante acostumado em ver no projeto abrindo uma pasta controller ou services ou repositories ou entities, e o scroll de uma forma muito grande, a muitos isso não deve incomodar muito, de fato possa apresentar "frescura", mas no quesito organiçação é problematico.
