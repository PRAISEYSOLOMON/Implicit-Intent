# Implicit-Intent
Developing an application in android studio based on the concepts of implicit intent
## In Activity_main.xml:
```
<?xml version="1.0" encoding="utf-8"?>
<androidx.constraintlayout.widget.ConstraintLayout xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:app="http://schemas.android.com/apk/res-auto"
    xmlns:tools="http://schemas.android.com/tools"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    tools:context=".MainActivity">

    <TextView
        android:id="@+id/textView"
        android:layout_width="244dp"
        android:layout_height="55dp"
        android:text="Implicit Intent"
        android:textColor="#8625AA"
        android:textSize="34sp"
        android:textStyle="bold|italic"
        app:layout_constraintBottom_toTopOf="@+id/editTextText"
        app:layout_constraintEnd_toEndOf="parent"
        app:layout_constraintHorizontal_bias="0.55"
        app:layout_constraintStart_toStartOf="parent"
        app:layout_constraintTop_toTopOf="parent"
        app:layout_constraintVertical_bias="0.595" />

    <EditText
        android:id="@+id/editTextText"
        android:layout_width="293dp"
        android:layout_height="78dp"
        android:ems="10"
        android:hint="Enter the URL"
        android:inputType="text"
        android:textColor="#8625AA"
        android:textSize="24sp"
        app:layout_constraintBottom_toTopOf="@+id/button"
        app:layout_constraintEnd_toEndOf="parent"
        app:layout_constraintHorizontal_bias="0.364"
        app:layout_constraintStart_toStartOf="parent"
        app:layout_constraintTop_toTopOf="parent"
        app:layout_constraintVertical_bias="0.808" />

    <Button
        android:id="@+id/button"
        android:layout_width="148dp"
        android:layout_height="71dp"
        android:text="Search"
        app:layout_constraintBottom_toBottomOf="parent"
        app:layout_constraintEnd_toEndOf="parent"
        app:layout_constraintStart_toStartOf="parent"
        app:layout_constraintTop_toTopOf="parent"
        app:layout_constraintVertical_bias="0.752" />

</androidx.constraintlayout.widget.ConstraintLayout>
```
## In ActivityMain.java
```
package com.example.implicitintent;

import androidx.appcompat.app.AppCompatActivity;

import android.content.Intent;
import android.net.Uri;
import android.os.Bundle;
import android.view.View;
import android.widget.Button;
import android.widget.EditText;

public class MainActivity extends AppCompatActivity {

    @Override
    protected void onCreate(Bundle savedInstanceState) {

        EditText editText;
        Button button;

        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);

        button = findViewById(R.id.button);
        editText = (EditText) findViewById(R.id.editTextText);

        button.setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View view){
                String url=editText.getText().toString();
                Intent intent = new Intent(Intent.ACTION_VIEW, Uri.parse(url));
                startActivity(intent);
            }

        });

    }
}
```
## Output:

![out2](https://github.com/PRAISEYSOLOMON/Implicit-Intent/assets/119394259/ad844905-6087-47ea-8154-ca5fb61bdc98)

![out1](https://github.com/PRAISEYSOLOMON/Implicit-Intent/assets/119394259/f6fa31ae-3625-4646-ba04-4448f65a1286)

## Result:
Thus, the appkicaation is created and implemented successfully using implicit intent concepts in Android studio.
