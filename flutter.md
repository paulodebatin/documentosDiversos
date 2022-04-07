# Flutter

1) Instalar pacotes
flutter pub pub add <nome do pacote>

2) Atualizar os pacotes com base no pubspec.yaml
flutter pub get

3) Builder para produção
WEB: 
flutter build web 

APK: 
flutter build apk

4) Setar a sdk
flutter config --android-sdk="/home/paulo/Android/Sdk"

5) Ver versões
flutter doctor -v

6) Mudando para  versão 8 do java
export JAVA_HOME=/home/paulo/Downloads/android-studio/jre

7) Trabalhando com emuladores:
a) Vendo os emuladores: 
~/Android/Sdk/emulator$ : ./emulator -list-avds

b) Iniciando um 
~/Android/Sdk/emulator$ : ./emulator @Pixel_3a_API_30_x86

c) Rodar a aplicação com o emaulador
~/projetos/edusoft/pocs/frontend_flutter(feature/196422)$ : flutter run -d emulator 

8) Adicionando suporte da app para uma aplicação desktop (exemplo para Linux)
Na pasta do projeto:
> flutter create --platforms=linux .
> flutter build linux
Será criado o executável em ~projeto/build/linux/release/bundle
Para maiores detalhes: https://flutter.dev/desktop

8) Trocar ícone
Android: 
- AndroidManifest.xml,  android:label e android:icon
    Para gerar o ícone: 
        a) Colocar dependência: flutter_launcher_icons: ^0.9.1 e
        b) Colocar script no pubspec.yaml:
            flutter_icons:
                image_path: "assets/images/fone.png"
                ios: true
                remove_alpha_ios: true
                android: "launcher_icon"
                adaptive_icon_background: "#FFFFFF"
                adaptive_icon_foreground: "assets/images/fone-android.png"
        c) Gerar por linha de comando: 
            flutter pub run flutter_launcher_icons:main