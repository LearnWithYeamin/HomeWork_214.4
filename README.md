<p align="center">
<h1 align='center'>Season 2 / Section 1 / HomeWork 214.4 Solution</h1>
<h3 align='center'>
   Visit my youtube channel <a href="https://www.youtube.com/@LearnWithYeamin">Learn With Yeamin</a>
</h3>
</p>

## Step 1: Here is `activity_main.xml` code.
```xml
<?xml version="1.0" encoding="utf-8"?>
<LinearLayout xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:tools="http://schemas.android.com/tools"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    android:orientation="vertical"
    android:padding="16dp"
    tools:context=".MainActivity">

    <TextView
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:text="Input marks for each subject:"
        android:textSize="18sp"
        android:textStyle="bold" />

    <EditText
        android:id="@+id/editTextPhysics"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:hint="Physics"
        android:inputType="number" />

    <EditText
        android:id="@+id/editTextChemistry"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:hint="Chemistry"
        android:inputType="number" />

    <EditText
        android:id="@+id/editTextBiology"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:hint="Biology"
        android:inputType="number" />

    <EditText
        android:id="@+id/editTextMathematics"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:hint="Mathematics"
        android:inputType="number" />

    <EditText
        android:id="@+id/editTextComputer"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:hint="Computer"
        android:inputType="number" />

    <Button
        android:id="@+id/buttonCalculate"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:layout_gravity="center_horizontal"
        android:layout_marginTop="16dp"
        android:text="Calculate" />

    <TextView
        android:id="@+id/textViewResult"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:layout_gravity="center_horizontal"
        android:layout_marginTop="16dp"
        android:textSize="18sp"
        android:textStyle="bold" />

</LinearLayout>
```
## Step 2: Here is `MainActivity.java` code.
```java
package com.myeamin.homework_2144;

import android.os.Bundle;

import androidx.appcompat.app.AppCompatActivity;

import android.view.View;
import android.widget.Button;
import android.widget.EditText;
import android.widget.TextView;

/**
 * MainActivity class defines the behavior for an app that calculates the percentage
 * and grade based on the marks of five subjects: Physics, Chemistry, Biology,
 * Mathematics, and Computer.
 */
public class MainActivity extends AppCompatActivity {

    // UI components
    EditText editTextPhysics, editTextChemistry, editTextBiology, editTextMathematics, editTextComputer;
    Button buttonCalculate;
    TextView textViewResult;

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);

        // Initialize the UI components
        editTextPhysics = findViewById(R.id.editTextPhysics);
        editTextChemistry = findViewById(R.id.editTextChemistry);
        editTextBiology = findViewById(R.id.editTextBiology);
        editTextMathematics = findViewById(R.id.editTextMathematics);
        editTextComputer = findViewById(R.id.editTextComputer);
        buttonCalculate = findViewById(R.id.buttonCalculate);
        textViewResult = findViewById(R.id.textViewResult);

        // Set a click listener on the calculate button
        buttonCalculate.setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View v) {
                // Retrieve the user input as a trimmed string
                String physicsStr = editTextPhysics.getText().toString().trim();
                String chemistryStr = editTextChemistry.getText().toString().trim();
                String biologyStr = editTextBiology.getText().toString().trim();
                String mathematicsStr = editTextMathematics.getText().toString().trim();
                String computerStr = editTextComputer.getText().toString().trim();

                // Check if any input string is empty
                if (physicsStr.isEmpty() || chemistryStr.isEmpty() || biologyStr.isEmpty() || mathematicsStr.isEmpty() || computerStr.isEmpty()) {
                    textViewResult.setText("Please enter marks for all subjects.");
                } else {
                    // Parse the input string to an integer
                    int physics = Integer.parseInt(physicsStr);
                    int chemistry = Integer.parseInt(chemistryStr);
                    int biology = Integer.parseInt(biologyStr);
                    int mathematics = Integer.parseInt(mathematicsStr);
                    int computer = Integer.parseInt(computerStr);

                    // Check if any input mark is greater than 100
                    if (physics > 100 || chemistry > 100 || biology > 100 || mathematics > 100 || computer > 100) {
                        textViewResult.setText("Please enter marks equal to or below 100 for all subjects.");
                    } else {
                        // Calculate total mark
                        int totalMarks = physics + chemistry + biology + mathematics + computer;
                        double percentage = (totalMarks / 5.0);

                        // Determine the grade based on the calculated percentage value
                        String grade;
                        if (percentage >= 90) {
                            grade = "Grade A";
                        } else if (percentage >= 80) {
                            grade = "Grade B";
                        } else if (percentage >= 70) {
                            grade = "Grade C";
                        } else if (percentage >= 60) {
                            grade = "Grade D";
                        } else if (percentage >= 40) {
                            grade = "Grade E";
                        } else {
                            grade = "Grade F";
                        }

                        // Format the percentage value with two decimal places
                        String percentageText = String.format("%.2f", percentage);
                        textViewResult.setText("Percentage = " + percentageText + "\n" + grade);
                    }
                }
            }
        });
    }
}
```
## Authors

**MD YEAMIN** - Android Software Developer <a href="https://www.youtube.com/@LearnWithYeamin">**(Learn With Yeamin)**</a> 

<h1 align="center">Thank You ❤️</h1>
