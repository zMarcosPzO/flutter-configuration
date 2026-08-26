# Configuração do Ambiente Flutter

Flutter é um framework de código aberto destinado ao desenvolvimento mobile e multiplataforma, que inclui Android, iOS, Web, Windows, Linux e macOS. A linguagem principal do Flutter é o Dart.

## 1. Pré-requisitos

O Flutter pode consumir recursos consideráveis, então é importante verificar os requisitos mínimos antes de iniciar:

- **Memória RAM:** recomenda-se pelo menos 8 GB.

- **Espaço em disco:** requer no mínimo 2,5 GB livres no Windows, e a quantidade pode variar em outros sistemas operacionais.

- **Git:** é utilizado internamente pelo Flutter para baixar pacotes e dependências.

- **Sistema operacional:** deve ser Windows 10 ou 11, macOS ou uma distribuição Linux de 64 bits.

## 2. Baixando o Flutter SDK

- Visite [flutter.dev](https://flutter.dev) e faça o download do SDK que corresponde ao seu sistema operacional. Use o arquivo `.zip` para Windows, o `.zip` ou `.dmg` para macOS, ou faça o download via terminal no Linux.

- Extraia a pasta em um local que não contenha espaços ou caracteres especiais no caminho, por exemplo, `C:\src\flutter` no Windows.

- Evite colocar o SDK dentro de pastas que exijam privilégios de administrador, como `Program Files`.

## 3. Configurando as variáveis de ambiente

Esse é o passo que costuma causar mais dificuldades para quem está começando, pois permite que o comando `flutter` funcione em qualquer terminal.

**Windows:**

1. Procure por 'Variáveis de Ambiente' no menu Iniciar.

2. Na seção 'Variáveis do usuário', escolha `Path` e clique em 'Editar'.

3. Adicione o caminho da pasta `bin` que fica dentro da pasta do Flutter, por exemplo `C:\src\flutter\bin`.

4. Reinicie o terminal para que a alteração seja aplicada.

**macOS/Linux:**

1. Abra o arquivo de configuração do seu shell, que pode ser `~/.zshrc`, `~/.bashrc` ou `~/.bash_profile`.

2. Insira a linha `export PATH=\"$PATH:[CAMINHO_PARA_O_FLUTTER]/bin\"`.

3. Salve o arquivo e execute `source ~/.zshrc` (ou o arquivo que você editou) para aplicar as alterações.

## 4. Instalando o editor de código

Flutter funciona tanto com o **Android Studio** quanto com o **VS Code**.

**Opção A — Android Studio:**

- Baixe e instale a partir de [developer.android.com/studio](https://developer.android.com/studio).

- Durante a instalação, verifique se o Android SDK, o Android SDK Platform-Tools e o Android Virtual Device são instalados.

- Instale o plugin **Flutter** através do menu `Plugins`; o Flutter já instala o plugin Dart automaticamente.

**Opção B — VS Code:**

- Baixe e instale a partir de [code.visualstudio.com](https://code.visualstudio.com).

- Instale a extensão **Flutter**, que já inclui o Dart Code.

- Reinicie o VS Code depois de instalar a extensão.

- Mesmo que você use apenas o VS Code, ainda precisa instalar o Android Studio ou, pelo menos, o Android SDK via `sdkmanager`, para compilar aplicativos Android.

## 5. Criando um emulador

- Abra o Android Studio e navegue até **More Actions** → **Virtual Device Manager**.

- Clique em **Create Device**, selecione um modelo de celular e escolha uma imagem de sistema. Recomenda-se usar a versão mais recente do Android que inclua o Google Play.

- Conclua a criação do dispositivo virtual e inicie o emulador antes de rodar o aplicativo.

Alternativamente, você pode conectar um celular físico com a **depuração USB** ativada.

## 6. Verificando a instalação

Execute o comando abaixo no terminal para verificar se tudo está funcionando corretamente:

```bash

flutter doctor

```

O comando `flutter doctor` verifica o SDK, as licenças do Android, a ferramenta de compilação e os editores instalados, e indica exatamente o que ainda precisa ser configurado. Resolva os itens marcados com `[✗]` antes de prosseguir, pois geralmente se tratam de licenças do Android que não foram aceitas (`flutter doctor --android-licenses`) ou de variáveis de ambiente configuradas incorretamente.

## 7. Testando com um Hello World

Crie um novo projeto para testar:

```bash

flutter create hello_world

cd hello_world

flutter run

```

Ou, se preferir testar rapidamente com um código simples, use:

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

Se a tela exibir 'Hello, world!', isso indica que o ambiente está configurado corretamente.

## 8. Problemas comuns

| Problema | Possível solução |

|---|---|

| Comando `flutter` não reconhecido | Verifique se o caminho `flutter/bin` foi adicionado corretamente ao `PATH` e reinicie o terminal |

