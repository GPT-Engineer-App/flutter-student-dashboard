# flutter-student-dashboard

 add this to my flutter code Navigation Bar: Links to Home (current homework), Completed Homework, Profile, Settings.
Review Answers: Post-deadline, an option to view correct answers and teacher comments.

import 'package:flutter/material.dart';
import 'homework/homework_list_page.dart';
import '../interactive_learning/interactive_tools_page.dart';
import '../performance_tracking/performance_page.dart';

class StudentHomePage extends StatelessWidget {
  const StudentHomePage({super.key});

  @override
  Widget build(BuildContext context) {
    var buildCard = _buildCard(
                context,
                'View Homework',
                const HomeworkListPage(),
              );
    return Scaffold(
      appBar: AppBar(
        title: const Text('Student Home'),
        backgroundColor: Colors.amber,
      ),
      body: Container(
        color: const Color.fromARGB(255, 0, 0, 0),
        child: Center(
          child: Column(
            mainAxisAlignment: MainAxisAlignment.center,
            children: <Widget>[
              buildCard,
              _buildCard(
                context,
                'Mandatory Video',
                const InteractiveToolsPage(),
              ),
              _buildCard(
                context,
                'Performance Tracking',
                const PerformancePage(),
              ),
            ],
          ),
        ),
      ),
    );
  }

  Widget _buildCard(BuildContext context, String title, Widget page) {
    return Card(
      shape: RoundedRectangleBorder(
        borderRadius: BorderRadius.circular(15.0),
      ),
      color: const Color(0xFF212121),
      margin: const EdgeInsets.symmetric(vertical: 10.0, horizontal: 25.0),
      child: ListTile(
        title: Center(
          child: Text(
            title,
            style: const TextStyle(
              color:  Colors.amber,
              fontSize: 18.0,
              fontWeight: FontWeight.bold,
            ),
          ),
        ),
        onTap: () {
          Navigator.push(
            context,
            MaterialPageRoute(builder: (context) => page),
          );
        },
      ),
    );
  }
}

## Collaborate with GPT Engineer

This is a [gptengineer.app](https://gptengineer.app)-synced repository 🌟🤖

Changes made via gptengineer.app will be committed to this repo.

If you clone this repo and push changes, you will have them reflected in the GPT Engineer UI.

## Tech stack

This project is built with React and Chakra UI.

- Vite
- React
- Chakra UI

## Setup

```sh
git clone https://github.com/GPT-Engineer-App/flutter-student-dashboard.git
cd flutter-student-dashboard
npm i
```

```sh
npm run dev
```

This will run a dev server with auto reloading and an instant preview.

## Requirements

- Node.js & npm - [install with nvm](https://github.com/nvm-sh/nvm#installing-and-updating)
