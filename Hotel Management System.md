import 'package:flutter/material.dart';

void main() {
  runApp(const HotelApp()); 
}

class HotelApp extends StatelessWidget {
  const HotelApp({super.key});

  @override
  Widget build(BuildContext context) {
    return MaterialApp(
      title: 'Hotel Management',
      theme: ThemeData(
        scaffoldBackgroundColor: Colors.white,
        appBarTheme: const AppBarTheme(
          backgroundColor: Colors.indigo,
          foregroundColor: Colors.white,
        ),
        elevatedButtonTheme: ElevatedButtonThemeData(
          style: ElevatedButton.styleFrom(
            backgroundColor: Colors.indigo,
            foregroundColor: Colors.white,
            minimumSize: Size(300, 60),
            textStyle: TextStyle(fontSize: 20),
          ),
        ),
      ),
      home: const HomeScreen(),
    );
  }
}

class HomeScreen extends StatelessWidget {
  const HomeScreen({super.key});

  @override
  Widget build(BuildContext context) {
    return Scaffold(
      appBar: AppBar(
        centerTitle: true,
        title: const Text(
          'WELCOME',
          style: TextStyle(fontWeight: FontWeight.bold),
        ),
      ),
      body: Center(
        child: ElevatedButton(
          child: const Text('Hotel Management'),
          onPressed: () {
            Navigator.push(
              context,
              MaterialPageRoute(builder: (context) => const ModuleSelectionScreen()),
            );
          },
        ),
      ),
    );
  }
}

class ModuleSelectionScreen extends StatelessWidget {
  const ModuleSelectionScreen({super.key});

  @override
  Widget build(BuildContext context) {
    return Scaffold(
      appBar: AppBar(
        title: const Text('Select Module'),
        centerTitle: true,
      ),
      body: Padding(
        padding: const EdgeInsets.all(20.0),
        child: Column(
          mainAxisAlignment: MainAxisAlignment.center,
          children: [
            ElevatedButton(
              child: const Text('01. Customer Module'),
              onPressed: () {
                print('Customer Module Selected');
              },
            ),
            const SizedBox(height: 20),
            ElevatedButton(
              child: const Text('02. Staff Module'),
              onPressed: () {
                print('Staff Module Selected');
              },
            ),
            const SizedBox(height: 20),
            ElevatedButton(
              child: const Text('03. Admin Module'),
              onPressed: () {
                print('Admin Module Selected');
              },
            ),
          ],
        ),
      ),
    );
  }
}
