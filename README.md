EXPERIMENT 2 – ADAPTIVE AND RESPONSIVE UI DESIGN
Aim
To create a Flutter application that automatically adapts its layout according to
screen size.
Step 1
Create the project:
flutter create responsive_ui
cd responsive_ui
code .
Step 2
Run:
flutter run
Step 3
Open:
lib/main.dart
Step 4 – Create a responsive layout
Use LayoutBuilder:
LayoutBuilder(
builder: (context, constraints) {
if (constraints.maxWidth < 600) {
return const Center(
child: Text('Mobile Layout'),
);
}
return const Center(
child: Text('Desktop / Tablet Layout'),
);
},
),
Step 5 – Create mobile layout

For smaller screens:
Column(
children: [
Card(
child: ListTile(
title: Text('Student'),
),
),
Card(
child: ListTile(
title: Text('Courses'),
),
),
],
)
Step 6 – Create desktop layout
For larger screens:
Row(
children: [
Expanded(
child: Card(
child: ListTile(
title: Text('Students'),
),
),
),
Expanded(
child: Card(
child: ListTile(
title: Text('Courses'),
),
),
),
],
)
Step 7 – Test different screen sizes
Resize the browser window or use different emulator sizes.
Small screen → Column
Large screen → Row
Expected Result: The same application should automatically adjust its UI
according to the available screen size.



Let's create EXPERIMENT 2 – ADAPTIVE AND RESPONSIVE UI DESIGN using Flutter in VS Code on Windows.

Follow these steps one by one.
Step 1 – Create Flutter project
Open VS Code → Terminal → New Terminal.

Select PowerShell and enter:
flutter create responsive_ui


Step 2 – Open the project
cd responsive_ui
code .


Step 3 – Open main.dart
In VS Code Explorer:
1. Open the lib folder.
2. Click main.dart.
3. Delete all existing code.
4. Copy and paste the following complete code.
Step 4 – Complete Flutter code
Copy and paste
import 'package:flutter/material.dart';

void main() {
  runApp(const MyApp());
}

class MyApp extends StatelessWidget {
  const MyApp({super.key});

  @override
  Widget build(BuildContext context) {
    return MaterialApp(
      debugShowCheckedModeBanner: false,
      home: const ResponsivePage(),
    );
  }
}

class ResponsivePage extends StatelessWidget {
  const ResponsivePage({super.key});

  @override
  Widget build(BuildContext context) {
    return Scaffold(
      appBar: AppBar(
        title: const Text('Responsive UI Design'),
        backgroundColor: Colors.blue,
      ),
      body: LayoutBuilder(
        builder: (context, constraints) {
          if (constraints.maxWidth < 600) {
            return Column(
              children: [
                Card(
                  margin: const EdgeInsets.all(10),
                  child: const ListTile(
                    leading: Icon(Icons.people),
                    title: Text('Students'),
                  ),
                ),
                Card(
                  margin: const EdgeInsets.all(10),
                  child: const ListTile(
                    leading: Icon(Icons.book),
                    title: Text('Courses'),
                  ),
                ),
              ],
            );
          }

          return Row(
            children: [
              Expanded(
                child: Card(
                  margin: const EdgeInsets.all(10),
                  child: const ListTile(
                    leading: Icon(Icons.people),
                    title: Text('Students'),
                  ),
                ),
              ),
              Expanded(
                child: Card(
                  margin: const EdgeInsets.all(10),
                  child: const ListTile(
                    leading: Icon(Icons.book),
                    title: Text('Courses'),
                  ),
                ),
              ),
            ],
          );
        },
      ),
    );
  }
}


Step 5 – Save the code
Press:
Ctrl + S


Step 6 – Run the application
In the VS Code terminal:
flutter run -d chrome


If web support is not enabled, run:
flutter config --enable-web
flutter create .
flutter run -d chrome
