import 'package:flutter/material.dart';

void main() {
  runApp(MyApp());
}

class MyApp extends StatelessWidget {
  @override
  Widget build(BuildContext context) {
    return MaterialApp(
      debugShowCheckedModeBanner: true,
      title: 'Student Profile Card',
      home: StudentProfile(),
    );
  }
}

class StudentProfile extends StatelessWidget {
  @override
  Widget build(BuildContext context) {
    return Scaffold(
      backgroundColor: Colors.blueGrey[50],
      appBar: AppBar(
        title: Text("Student Profile Card"),
        backgroundColor: Color(0xff5b09e1),
        centerTitle: true,
      ),
      body: Center(
        child: SingleChildScrollView(
          child: Column(
            mainAxisAlignment: MainAxisAlignment.center,
            children: [
              // Profile Image from Internet
              CircleAvatar(
                radius: 55,
                backgroundColor: Colors.white,
                child: ClipOval(
                  child: Image.network(
                    'https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcRvB0Il5CgmRxNpH0ZNPo6c1TZqbClYjN0ARlWxXY-pIQ&s=10',
                    width: 110,
                    height: 110,
                    fit: BoxFit.cover,
                    errorBuilder: (context, error, stackTrace) {
                      return Icon(
                        Icons.person,
                        size: 60,
                        color: Color(0xff5b09e1),
                      );
                    },
                  ),
                ),
              ),

              SizedBox(height: 20),

              Text(
                "Student Name: SHAIK ABDUL AZIZ",
                style: TextStyle(
                  fontSize: 22,
                  fontWeight: FontWeight.bold,
                ),
              ),

              SizedBox(height: 8),

              Text(
                "Roll Number: 24PA1A05L0",
                style: TextStyle(fontSize: 18),
              ),

              SizedBox(height: 8),

              Text(
                "Branch: CSE",
                style: TextStyle(fontSize: 18),
              ),

              SizedBox(height: 25),

              // Phone Card
              Container(
                margin: EdgeInsets.symmetric(horizontal: 30, vertical: 10),
                padding: EdgeInsets.all(15),
                decoration: BoxDecoration(
                  color: Colors.white,
                  borderRadius: BorderRadius.circular(15),
                  boxShadow: [
                    BoxShadow(
                      color: Colors.grey,
                      blurRadius: 6,
                      offset: Offset(2, 3),
                    ),
                  ],
                ),
                child: Row(
                  mainAxisSize: MainAxisSize.min,
                  children: [
                    Icon(Icons.phone, color: Colors.green),
                    SizedBox(width: 10),
                    Text(
                      "+91 8797999567",
                      style: TextStyle(fontSize: 18),
                    ),
                  ],
                ),
              ),

              // Email Card
              Container(
                margin: EdgeInsets.symmetric(horizontal: 30, vertical: 10),
                padding: EdgeInsets.all(15),
                decoration: BoxDecoration(
                  color: Colors.white,
                  borderRadius: BorderRadius.circular(15),
                  boxShadow: [
                    BoxShadow(
                      color: Colors.grey,
                      blurRadius: 6,
                      offset: Offset(2, 3),
                    ),
                  ],
                ),
                child: Row(
                  mainAxisSize: MainAxisSize.min,
                  children: [
                    Icon(Icons.email, color: Colors.red),
                    SizedBox(width: 10),
                    Text(
                      "shaik1930@gmail.com",
                      style: TextStyle(fontSize: 18),
                    ),
                  ],
                ),
              ),
            ],
          ),
        ),
      ),
    );
  }
}
