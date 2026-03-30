Report on Integrated Smart Healthcare System (C Program)
1. Introduction
The presented C program implements an Integrated Smart Healthcare System designed to assist users in basic health analysis and emergency response. The system is menu-driven and provides two primary functionalities:

Health Analysis Module
Emergency Response Module

The program also maintains patient records using file handling and generates a basic health risk assessment based on user input.

2. Objectives
To register and manage patient records.
To analyze symptoms and calculate health risk levels.
To provide preliminary medical advice.
To assist users during emergency situations with basic instructions.

3. System Modules
3.1 Health Analysis Module
This module performs the following tasks:
a) Patient Registration
New patients can enter personal details such as:
Name
Age
Blood group
City
Data is stored in a file named patients.txt along with the current date.

b) Existing Patient Record Access
Existing patients can view stored records from the file.
The system displays all saved patient data.

c) Symptom Analysis
Users can select multiple symptoms from a predefined list:
Fever
Cough and Cold
Headache
Stomach Pain
Skin Problems
Eye Irritation
Chest Pain
Joint Pain
Breathing Difficulty
Tooth Pain
Each symptom is assigned a severity level:
1: Mild
2: Moderate
3: Severe
4: Critical

d) Risk Calculation
Risk score is calculated based on severity.
High-risk symptoms (Chest Pain and Breathing Difficulty) are weighted more heavily.
Risk Levels:
Low: Risk ≤ 3
Moderate: Risk ≤ 7
High: Risk > 7

e) Medical Suggestions
The system provides:
Condition identification
Suggested medication
Recommended doctor specialization
Room allocation
Precautions

f) Advisory Output
Based on risk:
Low: Monitor and rest
Moderate: Visit doctor soon
High: Immediate medical attention
3.2 Emergency Response Module

This module handles urgent situations:

Emergency Types:
Accident
Fire
Cardiac Arrest
General Emergency
Seizures

Features:

User selects emergency type and severity level (1–5).
The system provides:
Immediate instructions
Priority classification

Priority Levels:
Low
Medium
High
Critical

Output:
Displays emergency handling steps.
Confirms dispatch of emergency response.

4. File Handling
The program uses file operations (fopen, fprintf, fgetc, fclose) to:
Store patient records
Retrieve and display stored data

5. Use of Time Functions
The program uses <time.h> to:
Capture the current system date
Store it alongside patient records

6. Advantages
Simple and user-friendly interface.
Combines multiple healthcare functionalities in a single system.
Provides immediate preliminary medical guidance.
Supports persistent data storage.

7. Limitations
No validation for incorrect symptom numbers.
File handling lacks error checking for write operations.
Patient search functionality is not implemented (displays all records instead).
Limited scalability due to fixed-size arrays.
Not suitable for real medical diagnosis; provides only basic guidance.

8. Future Enhancements
Implement patient search by name or ID.
Improve input validation and error handling.
Add a graphical user interface (GUI).
Integrate database systems instead of text files.
Expand symptom database and improve risk calculation algorithms.
Include real-time emergency service integration.

9. Conclusion
The program successfully demonstrates a basic healthcare assistance system using C programming. It integrates patient management, symptom analysis, and emergency handling into a single application. While suitable for academic and demonstration purposes, further improvements are required for practical, real-world deployment.
est Cases for Health Analysis Module

Test Case 1: New Patient Registration with Low Risk
Input:
Choice: 1
Existing Patient: n
Name: Rahul Sharma
Age: 25
Blood Group: B+
City: Mumbai
Symptom: Fever (1)
Severity: 1
Add another symptom: n

 Output:
Patient successfully registered in patients.txt
Risk Score = 1
Risk Level: LOW
Advice: Monitor symptoms and rest
Suggested:
Condition: Fever
Medicine: Paracetamol
Doctor: General Physician

Test Case 2: New Patient with Multiple Moderate Symptoms
Input:
Choice: 1
Existing Patient: n
Name: Anita Verma
Age: 30
Blood Group: O+
City: Delhi
Symptom 1: Cough and Cold (2), Severity: 2
Add another symptom: y
Symptom 2: Headache (3), Severity: 2
Add another symptom: n

 Output:
Risk Score = 4
Risk Level: MODERATE
Advice: Visit doctor soon
Displays both conditions with respective suggestions

Test Case 3: Existing Patient with High Risk Symptom
Input:
Choice: 1
Existing Patient: y
(System displays previous records)
Name: Amit Kumar
Age: 45
Symptom: Chest Pain (7)
Severity: 4
Add another symptom: n

Output:
Risk Score = 8 (weighted ×2)
Risk Level: HIGH
Advice: Visit doctor immediately
Suggested:
Condition: Chest Pain
Doctor: Cardiologist
Emergency precaution message

Test Case 4: Invalid Severity Input Handling
Input:
Choice: 1
Existing Patient: n
Name: Neha Singh
Age: 28
Blood Group: A+
City: Pune
Symptom: Headache (3)
Severity: 5 (invalid)

 Output:
System displays: "Invalid severity."
Prompts user to re-enter valid severity
No risk calculation until valid input is given

Test Case 5: Multiple Symptoms Including High-Risk Condition
Input:
Choice: 1
Existing Patient: n
Name: Raj Mehta
Age: 50
Blood Group: AB-
City: Ahmedabad
Symptom 1: Joint Pain (8), Severity: 2
Add another symptom: y
Symptom 2: Breathing Difficulty (9), Severity: 3
Add another symptom: n

 Output:
Risk Score = 2 + (3×2) = 8
Risk Level: HIGH
Advice: Visit doctor immediately
Displays:
Joint Pain → Orthopedic
Breathing Difficulty → Pulmonologist
