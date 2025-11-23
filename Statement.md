Project Problem Statement

Title: Student Performance Prediction using Linear Regression & Tkinter GUI

1. Background / Context

Educational performance prediction is an important area in academic analytics. Students’ final scores depend on various factors such as study patterns, attendance, and previous academic performance. Predicting these performance outcomes helps teachers identify at-risk students early and provide timely guidance.

With the increasing availability of digital educational data, machine learning models can be used to forecast final scores and improve decision-making. However, many educators are not familiar with programming tools, so a simple and user-friendly interface is necessary.

2. Problem Definition

The problem is to build a system that predicts the final examination score of a student using measurable inputs such as hours studied, attendance percentage, and previous exam score.

The system should:

Read a dataset of past student performance

Train a machine learning model (Linear Regression)

Allow users to enter new student data

Predict the final score out of 100

Provide an easy-to-use GUI for non-technical users

Display evaluation metrics like MSE and R² score

3. Objectives of the Project

To design a machine learning model capable of predicting student performance.

To identify the relationship between study hours, attendance, previous score, and final performance.

To build a desktop GUI application using Tkinter for easy input and prediction.

To display meaningful evaluation metrics for model accuracy.

To categorize predicted results into interpretation levels (e.g., Good, At Risk, High Risk).

4. Scope of the Project

Works for numeric inputs only (hours studied, attendance, previous score).

Predicts score only within range 0–100.

Linear Regression used as base model.

GUI usable on Windows, Linux, macOS (Python installed required).

No internet required; runs completely offline.

5. Expected Output

Predicted final exam score displayed on GUI

Clear interpretation message such as:

Very good performance expected

At risk — study more

High risk — urgent improvement needed

Display of model evaluation metrics:

MSE

R² Score

6. Problem Constraints

Requires a properly formatted students.csv dataset

Model accuracy depends on dataset size and quality

Inputs must be valid numeric values

Tkinter layout limitations on small screens

7. Success Criteria

The project will be considered successful if:

The model predicts final scores with reasonable accuracy

The GUI runs without errors

Users can easily input values and receive predictions

System displays correct evaluation metrics
