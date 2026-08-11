Flutter é um framework de código aberto voltado a desenvolvimento mobile e multiplataformas (android, IOS, web, Windows, linux, macOs), tendo como sua linguagem o Dart.

Aqui está um breve passo a passo de como configurar o ambiente para desenvolver em Flutter:

1 - Instalação do SDk;
2 - Configuração de variáveis;
3 - Instalação do Android Studio ( O flutter é compatível  com o VS code, contando que você baixe a SDK dele)
4 - Criação de um emulador;

2. Pré-requisitos:
  O Flutter pode ser um pouco pesado, por isso, tem que analisar os requisitos mínimos.
  - Memoria RAM: recomendado 8gb ou até mais;
  - Espaço: No mínimo 2,5 gb livre
  - GIT: o GIT é usado internamente no Flutter

3. Baixando o Flutter:
  - Acesse [flutter.dev](https://flutter.dev) e baixe o `.zip` do Flutter SDK para Windows e extraia a pasta
  - Instale o Android Studio ( caso for programar em VS code, baixar a SDK)

4. Baixando pelo VS code
  -  Baixe e instale o VS Code em [code.visualstudio.com](https://code.visualstudio.com).
  - Instale a extensão Flutter (Dart Code)
  - Reinicie o VS Code após a instalação.

5. Verifique a instalação
  - Após instalar o flutter, escreva o código abaixo para testar a instalação:
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

-Se a tela apareceu "Hello, world", é sinal que o código deu certo e o ambiente está configurado
