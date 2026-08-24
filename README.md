# Configuração do Ambiente Flutter

Flutter é um framework de código aberto voltado para desenvolvimento mobile e multiplataforma (Android, iOS, Web, Windows, Linux, macOS), tendo como linguagem principal o **Dart**.

Este guia mostra o passo a passo para configurar o ambiente de desenvolvimento em Flutter.

## Índice

1. [Pré-requisitos](#1-pré-requisitos)
2. [Baixando o Flutter SDK](#2-baixando-o-flutter-sdk)
3. [Configurando as variáveis de ambiente](#3-configurando-as-variáveis-de-ambiente)
4. [Instalando o editor de código](#4-instalando-o-editor-de-código)
5. [Criando um emulador](#5-criando-um-emulador)
6. [Verificando a instalação](#6-verificando-a-instalação)
7. [Testando com um Hello World](#7-testando-com-um-hello-world)
8. [Problemas comuns](#8-problemas-comuns)

---

## 1. Pré-requisitos

O Flutter pode ser um pouco pesado, por isso vale checar os requisitos mínimos antes de começar:

- **Memória RAM:** recomendado 8 GB ou mais
- **Espaço em disco:** no mínimo 2,5 GB livres (Windows), podendo variar em outros sistemas
- **Git:** usado internamente pelo Flutter para baixar pacotes e dependências
- **Sistema operacional:** Windows 10/11, macOS ou uma distribuição Linux com 64 bits

## 2. Baixando o Flutter SDK

- Acesse [flutter.dev](https://flutter.dev) e baixe o SDK correspondente ao seu sistema operacional (`.zip` para Windows, `.zip`/`.dmg` para macOS, ou via terminal no Linux)
- Extraia a pasta em um local sem espaços ou caracteres especiais no caminho (ex: `C:\src\flutter` no Windows)
- Evite pastas que exijam privilégios de administrador, como `Program Files`

## 3. Configurando as variáveis de ambiente

Esse é o passo que mais trava quem está começando — é ele que faz o comando `flutter` funcionar em qualquer lugar do terminal.

**Windows:**
1. Pesquise por "Variáveis de Ambiente" no menu Iniciar
2. Em "Variáveis do usuário", selecione `Path` e clique em "Editar"
3. Adicione o caminho da pasta `bin` dentro da pasta do Flutter (ex: `C:\src\flutter\bin`)
4. Reinicie o terminal para aplicar a mudança

**macOS/Linux:**
1. Abra o arquivo de configuração do seu shell (`~/.zshrc`, `~/.bashrc` ou `~/.bash_profile`)
2. Adicione a linha: `export PATH="$PATH:[CAMINHO_PARA_O_FLUTTER]/bin"`
3. Salve e execute `source ~/.zshrc` (ou o arquivo correspondente) para aplicar

## 4. Instalando o editor de código

O Flutter é compatível tanto com **Android Studio** quanto com **VS Code**.

**Opção A — Android Studio:**
- Baixe e instale em [developer.android.com/studio](https://developer.android.com/studio)
- Durante a instalação, garanta que o Android SDK, o Android SDK Platform-Tools e o Android Virtual Device sejam instalados
- Instale o plugin **Flutter** pelo menu `Plugins` (ele já instala o plugin Dart junto)

**Opção B — VS Code:**
- Baixe e instale em [code.visualstudio.com](https://code.visualstudio.com)
- Instale a extensão **Flutter** (que já traz o Dart Code junto)
- Reinicie o VS Code após a instalação
- Mesmo usando VS Code, ainda é necessário instalar o Android Studio (ou pelo menos o Android SDK via `sdkmanager`) para compilar para Android

## 5. Criando um emulador

- Abra o Android Studio → **More Actions** → **Virtual Device Manager**
- Clique em **Create Device**, escolha um modelo de celular e uma imagem de sistema (recomendado: a versão mais recente do Android com Google Play)
- Finalize a criação e inicie o emulador antes de rodar o app

Alternativamente, você pode conectar um celular físico com a **depuração USB** ativada.

## 6. Verificando a instalação

Rode o comando abaixo no terminal para checar se está tudo certo:

```bash
flutter doctor
```

Esse comando verifica o SDK, as licenças do Android, o toolchain e os editores instalados, apontando exatamente o que ainda falta configurar. Resolva os itens marcados com `[✗]` antes de seguir em frente — geralmente são licenças do Android não aceitas (`flutter doctor --android-licenses`) ou variáveis de ambiente mal configuradas.

## 7. Testando com um Hello World

Crie um novo projeto para testar:

```bash
flutter create hello_world
cd hello_world
flutter run
```

Ou, se preferir testar rapidamente com um código simples:

```dart
import 'package:flutter/material.dart';

void main() {
  runApp(
    const Center(
      child: Text(
        'Hello, world!',
        textDirection: TextDirection.ltr,
        style: TextStyle(color: Colors.blue),
      ),
    ),
  );
}
```

Se a tela exibir "Hello, world!", o ambiente está configurado corretamente.

## 8. Problemas comuns

| Problema | Possível solução |
|---|---|
| Comando `flutter` não reconhecido | Verifique se o caminho `flutter/bin` foi adicionado corretamente ao `PATH` e reinicie o terminal |
| Licenças do Android pendentes | Execute `flutter doctor --android-licenses` e aceite todas |
| Emulador não inicia | Verifique se a virtualização (VT-x/AMD-V) está habilitada na BIOS |
| `flutter doctor` trava em "Waiting for another flutter command" | Delete o arquivo de lock em `flutter/bin/cache/lockfile` |

---

## Recursos adicionais

- [Documentação oficial do Flutter](https://docs.flutter.dev)
- [Cookbook do Flutter](https://docs.flutter.dev/cookbook)
- [Pub.dev — pacotes Flutter/Dart](https://pub.dev)
