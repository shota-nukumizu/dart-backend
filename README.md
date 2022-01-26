# Dart-sample Application

A simple command-line application made in Dart.

Dartで簡単なアプリを開発

# 環境構築

まずはインストール

```
$ dart create api
```

次に、以下のプログラムを`bin/main.dart`に書けば、Dart制で簡単な開発者サーバを立ち上げられる。

```dart
import 'dart:io';

Future main() async {
  var server = await HttpServer.bind(
    InternetAddress.loopbackIPv4,
    4040,
  );
  print('Listening on localhost:${server.port}');

  await for (HttpRequest request in server) {
    request.response.write('Hello World!');
    await request.response.close();
  }
}
```

# 開発環境

* Visual Studio Code 1.63
* Dart SDK 2.16.0
