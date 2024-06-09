## MarqueeWidget

This is a simple package that gives you the power to turn any Flutter Widget into a `Marquee`. With this, you can further control the speed and also allows for manual `swiping gestures`.




## Features

- A `child` widget param that can accommodate any flutter or custom widget.

- A `TextDirection` param that allows you control the `Directionality` of the `child`.

- An `Axis` direction to enable you control the scroll direction for the `singleChildScrollView` wrapper for the `child`.

- A `Duration` controller, for the `animationDuration`, `backDuration` and the `pauseDuration` of the Marquee.

- A `Curve`parametric animation controller to adjust the rate of change of an animation over time for the `forwardAnimation` and `backwardAnimation`.

- An `autoRepeat` boolean value, to control the looping of the Marquee.


## Get Started

In the `pubspec.yaml` of your flutter project, add the following to your dependency;

```dart
dependencies:
  marquee_widget: <latest_version>
```
In the file you may wish to implement this Marquee

```dart
import 'package: marquee_widget/marquee_widget.dart';
```


## Basic Usage

```dart
    MarqueeWidget(
        animationDuration: const Duration(seconds: 20),
        backDuration: const Duration(seconds: 20),
        pauseDuration: const Duration(seconds: 2),
        directionOption: DirectionOption.twoDirection,
        child: SizedBox( // Can accept any Widget
            height: 100,
            child: ListView(
            scrollDirection: Axis.horizontal,
            shrinkWrap: true,
            children: List.generate(
                _imageList.length,
                (index) => Container(
                height: 100,
                width: 100,
                margin: const EdgeInsets.symmetric(horizontal: 10),
                decoration: BoxDecoration(
                    color: Colors.greenAccent,
                    borderRadius: BorderRadius.circular(10),
                ),
                child: ClipRRect(
                    borderRadius: BorderRadius.circular(10),
                    child: Image.network(
                    _imageList[index],
                    fit: BoxFit.cover,
                    ),
                ),
                ),
            ),
            ),
        ),
    ),
```


## Example

- For Widget Image Marquee
```dart
import 'package:flutter/material.dart';
import 'package:marquee_widget/src/marquee_widget.dart';

void main() {
  runApp(MyApp());
}

class MyApp extends StatelessWidget {
  @override
  Widget build(BuildContext context) {
    return MaterialApp(
      debugShowCheckedModeBanner: false,
      title: ' Marquee Demo',
      theme: ThemeData(
        primarySwatch: Colors.blue,
      ),
      home: Scaffold(
        appBar: AppBar(
          title: const Text('Widget  Marquee'),
        ),
        body: Container(
          padding: const EdgeInsets.symmetric(horizontal: 10, vertical: 10),
          width: double.infinity,
          child: Column(
            children: [
              MarqueeWidget(
                animationDuration: const Duration(seconds: 20),
                backDuration: const Duration(seconds: 20),
                pauseDuration: const Duration(seconds: 2),
                directionOption: DirectionOption.twoDirection,
                child: SizedBox(
                  height: 100,
                  child: ListView(
                    scrollDirection: Axis.horizontal,
                    shrinkWrap: true,
                    children: List.generate(
                      _imageList.length,
                      (index) => Container(
                        height: 100,
                        width: 100,
                        margin: const EdgeInsets.symmetric(horizontal: 10),
                        decoration: BoxDecoration(
                          color: Colors.greenAccent,
                          borderRadius: BorderRadius.circular(10),
                        ),
                        child: ClipRRect(
                          borderRadius: BorderRadius.circular(10),
                          child: Image.network(
                            _imageList[index],
                            fit: BoxFit.cover,
                          ),
                        ),
                      ),
                    ),
                  ),
                ),
              ),
              const SizedBox(
                height: 20,
              ),
              MarqueeWidget(
                animationDuration: const Duration(seconds: 40),
                backDuration: const Duration(seconds: 40),
                pauseDuration: const Duration(seconds: 2),
                directionOption: DirectionOption.twoDirection,
                child: SizedBox(
                  height: 100,
                  child: ListView(
                    scrollDirection: Axis.horizontal,
                    shrinkWrap: true,
                    children: List.generate(
                      _imageList.length,
                      (index) => Container(
                        height: 100,
                        width: 100,
                        margin: const EdgeInsets.symmetric(horizontal: 10),
                        decoration: BoxDecoration(
                          color: Colors.greenAccent,
                          borderRadius: BorderRadius.circular(10),
                        ),
                        child: ClipRRect(
                          borderRadius: BorderRadius.circular(10),
                          child: Image.network(
                            _imageList[index],
                            fit: BoxFit.cover,
                          ),
                        ),
                      ),
                    ),
                  ),
                ),
              ),
            ],
          ),
        ),
      ),
    );
  }

  final List<String> _imageList = [
    "https://media.istockphoto.com/id/1146517111/photo/taj-mahal-mausoleum-in-agra.jpg?s=612x612&w=0&k=20&c=vcIjhwUrNyjoKbGbAQ5sOcEzDUgOfCsm9ySmJ8gNeRk=",
    "https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcSfmb4MpLzlccjigLtvQNuUpSI6L1oOpfUXsg&s"
    
  ];
}

```