# Ex.No:2b To create a two screens , first screen will take one number input from user. After click on Factorial button, second screen will open and it should display factorial of the same number using Explicit Intents.


## AIM:

To create a two screens , first screen will take one number input from user. After click on Factorial button, second screen will open and it should display factorial of the same number using Explicit Intents.


## EQUIPMENTS REQUIRED:

Latest Version Android Studio

## ALGORITHM:
Start app → show first screen.

User enters a number in the box.

User presses the Factorial button.

Read the number from the box.

Send this number to the second screen using explicit intent.

Open the second screen.

Second screen receives the number.

Calculate factorial of the number.

Show the factorial result in a TextView.

End.

## PROGRAM:
```
Program to implement ExplicitIntent.
Developed by: SUDARSAN.A
Registration Number :212224220111
```
### MainActivity.java
```java
package com.example.explicitintent;

import android.content.Intent;
import android.os.Bundle;
import android.view.View;
import android.widget.Button;
import android.widget.EditText;

import androidx.appcompat.app.AppCompatActivity;

public class MainActivity extends AppCompatActivity
{

    EditText numberInput;
    Button factorialBtn;

    @Override
    protected void onCreate(Bundle savedInstanceState)
    {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);

        numberInput = findViewById(R.id.editTextNumber);
        factorialBtn = findViewById(R.id.buttonFactorial);

        factorialBtn.setOnClickListener(new View.OnClickListener()
        {
            @Override
            public void onClick(View v)
            {
                String numStr = numberInput.getText().toString();
                if (!numStr.isEmpty())
                {
                    int number = Integer.parseInt(numStr);
                    Intent intent = new Intent(MainActivity.this, MainActivity2.class);
                    intent.putExtra("number", number);
                    startActivity(intent);
                }
            }
        });
    }
}

```
### MainActivity2.java
```java
package com.example.explicitintent;

import android.os.Bundle;
import android.widget.TextView;

import androidx.appcompat.app.AppCompatActivity;

public class MainActivity2 extends AppCompatActivity
{

    TextView resultView;

    @Override
    protected void onCreate(Bundle savedInstanceState)
    {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main2);

        resultView = findViewById(R.id.textViewResult);
        int number = getIntent().getIntExtra("number", 0);
        long fact = factorial(number);
        resultView.setText("Factorial of " + number + " = " + fact);
    }
    private long factorial(int n)
    {
        long result = 1;
        for (int i = 1; i <= n; i++)
        {
            result *= i;
        }
        return result;
    }
}
```
### activity_main.xml
```xml
<?xml version="1.0" encoding="utf-8"?>
<androidx.constraintlayout.widget.ConstraintLayout xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:app="http://schemas.android.com/apk/res-auto"
    xmlns:tools="http://schemas.android.com/tools"
    android:id="@+id/main"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    tools:context=".MainActivity">

    <EditText
        android:id="@+id/editTextNumber"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:hint="Enter a number"
        android:inputType="number"
        app:layout_constraintBottom_toBottomOf="parent"
        app:layout_constraintEnd_toEndOf="parent"
        app:layout_constraintHorizontal_bias="1.0"
        app:layout_constraintStart_toStartOf="parent"
        app:layout_constraintTop_toTopOf="parent"
        app:layout_constraintVertical_bias="0.384" />

    <Button
        android:id="@+id/buttonFactorial"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:text="Factorial"
        app:layout_constraintBottom_toBottomOf="parent"
        app:layout_constraintEnd_toEndOf="parent"
        app:layout_constraintStart_toStartOf="parent"
        app:layout_constraintTop_toTopOf="parent"
        app:layout_constraintVertical_bias="0.527" />

    <TextView
        android:id="@+id/textView"
        android:layout_width="222dp"
        android:layout_height="51dp"
        android:layout_marginStart="116dp"
        android:text="Explicit Intent"
        android:textColor="#233DD3"
        android:textSize="24sp"
        app:layout_constraintBottom_toTopOf="@+id/editTextNumber"
        app:layout_constraintStart_toStartOf="parent"
        app:layout_constraintTop_toTopOf="parent"
        app:layout_constraintVertical_bias="0.463" />
</androidx.constraintlayout.widget.ConstraintLayout>
```
### activity_main2.xml
```xml
<?xml version="1.0" encoding="utf-8"?>
<androidx.constraintlayout.widget.ConstraintLayout xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:app="http://schemas.android.com/apk/res-auto"
    xmlns:tools="http://schemas.android.com/tools"
    android:id="@+id/main"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    tools:context=".MainActivity2">

    <TextView
        android:id="@+id/textViewResult"
        android:layout_width="231dp"
        android:layout_height="65dp"
        android:text="Result will appear here"
        android:textSize="20sp"
        app:layout_constraintBottom_toBottomOf="parent"
        app:layout_constraintEnd_toEndOf="parent"
        app:layout_constraintStart_toStartOf="parent"
        app:layout_constraintTop_toTopOf="parent" />

    <TextView
        android:id="@+id/textView"
        android:layout_width="222dp"
        android:layout_height="51dp"
        android:text="Explicit Intent"
        android:textColor="#233DD3"
        android:textSize="24sp"
        app:layout_constraintBottom_toTopOf="@+id/textViewResult"
        app:layout_constraintEnd_toEndOf="parent"
        app:layout_constraintHorizontal_bias="0.582"
        app:layout_constraintStart_toStartOf="parent"
        app:layout_constraintTop_toTopOf="parent"
        app:layout_constraintVertical_bias="0.585" />
</androidx.constraintlayout.widget.ConstraintLayout>
```
## OUTPUT
### MainActivity.java
<img width="959" height="506" alt="image" src="https://github.com/user-attachments/assets/31c9c588-b1e9-46d4-87aa-91f3d3369337" />

### activity_main.xml
<img width="959" height="503" alt="image" src="https://github.com/user-attachments/assets/edbdb3cb-260a-4143-b5ed-1bb183d76f8b" />

### activity_main2.xml
<img width="959" height="505" alt="image" src="https://github.com/user-attachments/assets/2b8368f0-8d05-45c7-93fc-b781937f7afa" />

### First Screen
<img width="959" height="503" alt="image" src="https://github.com/user-attachments/assets/98a89e4e-69c5-4011-86e7-25daf6322621" />
<img width="245" height="451" alt="image" src="https://github.com/user-attachments/assets/2c032fd5-d9bf-4611-8b2c-35b3cdea87f9" />


### Second Screen 
<img width="959" height="504" alt="image" src="https://github.com/user-attachments/assets/14ba4611-f3f8-49f9-9c8b-b9f5545ae72f" />
<img width="244" height="454" alt="image" src="https://github.com/user-attachments/assets/3a7a0516-3ad7-4cc4-bfda-c55b7d79bc41" />


## RESULT
Thus a Simple Android Application create a Explicit Intents using Android Studio is developed and executed successfully.


