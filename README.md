<!-- 
This README describes the package. If you publish this package to pub.dev,
this README's contents appear on the landing page for your package.

For information about how to write a good package README, see the guide for
[writing package pages](https://dart.dev/guides/libraries/writing-package-pages). 

For general information about developing packages, see the Dart guide for
[creating packages](https://dart.dev/guides/libraries/create-library-packages)
and the Flutter guide for
[developing packages and plugins](https://flutter.dev/developing-packages). 
-->

TODO: 

## Features

package to customize themes in flutter projects

## Getting started

TODO: List prerequisites and provide or point to information on how to
start using the package.

## Usage

Here is how to use that package
to `/example` folder. 

```dart
const like = 'sample';
```

## Additional information

For any questions about collaborating or improving the application, write to mamanipari@gmail.com

## Example en Contador por defecto

```dart
import 'package:flutter/material.dart';
import 'package:app_bar_dmp/src/theme/AppTheme.dart';
import 'package:app_bar_dmp/src/comp/CustomAppBar.dart';

void main() {
  runApp(const MyApp());
}

class MyApp extends StatelessWidget {
  const MyApp({Key? key}) : super(key: key);
  @override
  Widget build(BuildContext context) {
    return MaterialApp(
      title: 'Flutter Demo',
      theme: ThemeData(
        primarySwatch: Colors.blue,
      ),
      home: const MyHomePage(title: 'Flutter Demo Home Page'),
    );
  }
}

class MyHomePage extends StatefulWidget {
  const MyHomePage({Key? key, required this.title}) : super(key: key);
  final String title;

  @override
  State<MyHomePage> createState() => _MyHomePageState();
}

class _MyHomePageState extends State<MyHomePage> {
  int _counter = 0;
  void _incrementCounter() {
    setState(() {
      _counter++;
      AppTheme.colorX=Colors.blue;
    });
  }
  //Agregado
  void accion() {
    setState(() {
    });
  }


  @override
  Widget build(BuildContext context) {
    //Inicio Agregado
    return MaterialApp(
      debugShowCheckedModeBanner: false,
      title: 'UPeU',
      themeMode: AppTheme.useLightMode ? ThemeMode.light : ThemeMode.dark,
      theme: AppTheme.themeData,//Fin Agregado
      home: Scaffold(
        appBar: CustomAppBar(accionx: accion as Function),

        body: Center(
          child: Column(
            mainAxisAlignment: MainAxisAlignment.center,
            children: <Widget>[
              const Text(
                'You have pushed the button this many times:',
              ),
              Text(
                '$_counter',
              ),
            ],
          ),
        ),
        floatingActionButton: FloatingActionButton(
          onPressed: _incrementCounter,
          tooltip: 'Increment',
          child: const Icon(Icons.add),
        ), // This trailing comma makes auto-formatting nicer for build methods.
      ),
    );
  }
}
```