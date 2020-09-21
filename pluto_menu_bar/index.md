## PlutoMenuBar for flutter - v0.1.3

<br>

PlutoMenuBar is a horizontal menu bar for flutter.

<br>

### Features
- Multiple sub-menu : Add as many submenus as you like.
- Change the default style : Change the background, font, and border.

<br>

### [Demo Web](https://bosskmk.github.io/pluto_menu_bar/build/web/index.html)
> Try some simple features on the demo site.

<br>

### [Pub.Dev](https://pub.dev/packages/pluto_menu_bar)
> Check out how to install from the official distribution site.

<br>

### Screenshots

![PlutoMenuBar Image](https://bosskmk.github.io/images/pluto_menu_bar_img1.gif)

<br>

### Example
```dart
import 'package:flutter/material.dart';
import 'package:pluto_menu_bar/pluto_menu_bar.dart';

void main() {
  runApp(MyApp());
}

class MyApp extends StatelessWidget {
  final _scaffoldKey = GlobalKey();

  @override
  Widget build(BuildContext context) {
    return MaterialApp(
      home: Scaffold(
        key: _scaffoldKey,
        appBar: AppBar(
          title: Text('PlutoMenuBar'),
        ),
        body: PlutoMenuBarDemo(scaffoldKey: _scaffoldKey),
      ),
    );
  }
}

class PlutoMenuBarDemo extends StatelessWidget {
  final scaffoldKey;

  PlutoMenuBarDemo({
    this.scaffoldKey,
  });

  void message(context, String text) {
    scaffoldKey.currentState.hideCurrentSnackBar();

    final snackBar = SnackBar(
      content: Text(text),
    );

    Scaffold.of(context).showSnackBar(snackBar);
  }

  @override
  Widget build(BuildContext context) {
    return Container(
      child: Column(
        children: [
          SizedBox(
            height: 30,
          ),
          PlutoMenuBar(
            menus: [
              MenuItem(
                title: 'Menu 1',
                children: [
                  MenuItem(
                    title: 'Menu 1-1',
                    onTap: () => message(context, 'Menu 1-1 tap'),
                    children: [
                      MenuItem(
                        title: 'Menu 1-1-1',
                        onTap: () => message(context, 'Menu 1-1-1 tap'),
                        children: [
                          MenuItem(
                            title: 'Menu 1-1-1-1',
                            onTap: () => message(context, 'Menu 1-1-1-1 tap'),
                          ),
                          MenuItem(
                            title: 'Menu 1-1-1-2',
                            onTap: () => message(context, 'Menu 1-1-1-2 tap'),
                          ),
                        ],
                      ),
                      MenuItem(
                        title: 'Menu 1-1-2',
                        onTap: () => message(context, 'Menu 1-1-2 tap'),
                      ),
                    ],
                  ),
                  MenuItem(
                    title: 'Menu 1-2',
                    onTap: () => message(context, 'Menu 1-2 tap'),
                  ),
                ],
              ),
              MenuItem(
                title: 'Menu 2',
                children: [
                  MenuItem(
                    title: 'Menu 2-1',
                    onTap: () => message(context, 'Menu 2-1 tap'),
                  ),
                ],
              ),
              MenuItem(
                title: 'Menu 3',
                onTap: () => message(context, 'Menu 3 tap'),
              ),
              MenuItem(
                title: 'Menu 4',
                onTap: () => message(context, 'Menu 4 tap'),
              ),
              MenuItem(
                title: 'Menu 5',
                onTap: () => message(context, 'Menu 5 tap'),
              ),
            ],
          ),
        ],
      ),
    );
  }
}
```

<br>

### Pluto series
> develop packages that make it easy to develop admin pages or CMS with Flutter.
* [PlutoGrid](https://github.com/bosskmk/pluto_grid)
* [PlutoMenuBar](https://github.com/bosskmk/pluto_menu_bar)

<br>

### License
> MIT
