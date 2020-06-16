java file
package com.example.android.quiz;

import androidx.appcompat.app.AppCompatActivity;

import android.os.Bundle;
import android.view.View;
import android.widget.EditText;
import android.widget.TextView;

public class MainActivity extends AppCompatActivity {

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);
    }
    // to print result

    //to make sting of final  answer

    public void answer(View view){

        String message;
        // to get value of 1st question

        EditText answer1Feild = (EditText) findViewById(R.id.answer_one);
        String answer1 = answer1Feild.getText().toString();

        message = checkAnswer1(answer1);
        // to get answer of 2nd question


        EditText answer2Feild = (EditText) findViewById(R.id.answer_two);
        String answer2 = answer2Feild.getText().toString();

        message += checkAnswer2(answer2);

        // to get value of 3rd question

        EditText answer3Feild = (EditText) findViewById(R.id.answer_three);
        String answer3 = answer3Feild.getText().toString();

        message += checkAnswer3(answer3);

        // to get answer of 4th question

        EditText answer4Feild = (EditText) findViewById(R.id.answer_four);
        String answer4 = answer4Feild.getText().toString();

        message = checkAnswer4(answer4);

        // to get value of 5th question

        EditText answer5Feild = (EditText) findViewById(R.id.answer_five);
        String answer5 = answer5Feild.getText().toString();

        message += checkAnswer5(answer5);

        TextView priceTextView = (TextView) findViewById(R.id.result);
        priceTextView.setText(message );
    }

    // to 1st check answer
    private String checkAnswer1(String answer){
        String message ;
        if (answer.equals("100")){
            message = "\n Your 1st question is right";
        } else{
            message = "\n Your 1st question is wrong";
        }
        return message ;
    }

    // to 2st check answer
    private String checkAnswer2(String answer){
        String message ;
        if (answer.equals("To change player's name")){
            message = "\n Your 2nd question is right";
        } else{
            message = "\n Your 2nd question is wrong";
        }
        return message ;
    }

    // to 3rd check answer
    private String checkAnswer3(String answer) {
        String message ;
        if (answer.equals("ACE")) {
            message = "\n Your 3rd question is right";
        } else {
            message = "\n Your 3rd question is wrong";
        }
        return message;
    }

    // to 14th check answer
    private String checkAnswer4(String answer) {
        String message;
        if (answer.equals("CONQUEROR")) {
            message = "\n Your 4th question is right";
        } else {
            message = "\n Your 4th question is wrong";
        }
        return message;
    }
    
    // to 5th check answer
    private String checkAnswer5(String answer) {
        String message ;
        if (answer.equals("13")) {
            message = "\n Your 5th question is right";
        } else {
            message = "\n Your 5th question is wrong";
        }
        return message;
    }
}


xml file

<?xml version="1.0" encoding="utf-8"?>
<ScrollView xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:app="http://schemas.android.com/apk/res-auto"
    xmlns:tools="http://schemas.android.com/tools"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    tools:context=".MainActivity">
    <LinearLayout
        android:layout_width="match_parent"
        android:layout_height="match_parent"
        android:orientation="vertical">

        <TextView
            android:layout_width="wrap_content"
            android:layout_height="wrap_content"
            android:text="Q.1. Which is the highest R.P. in PUBG Mobile app ? (In number)"
            android:padding="8dp"
            android:textSize="20dp"/>

        <EditText
            android:layout_width="match_parent"
            android:layout_height="wrap_content"
            android:hint="Answer"
            android:id="@+id/answer_one"
            android:padding="8dp"/>

        <TextView
            android:layout_width="wrap_content"
            android:layout_height="wrap_content"
            android:text="Q.2. For What changes the Rename card used ?"
            android:padding="8dp"
            android:textSize="20dp"/>
        <EditText
            android:layout_width="match_parent"
            android:layout_height="wrap_content"
            android:hint="Answer"
            android:id="@+id/answer_two"
            android:padding="8dp"/>

        <TextView
            android:layout_width="wrap_content"
            android:layout_height="wrap_content"
            android:text="Q.3. Which Tier is come after CROWN Tier in PUBG Mobile ? (In capital)"
            android:padding="8dp"
            android:textSize="20dp"/>

        <EditText
            android:layout_width="match_parent"
            android:layout_height="wrap_content"
            android:hint="Answer"
            android:id="@+id/answer_three"
            android:padding="8dp"/>

        <TextView
            android:layout_width="wrap_content"
            android:layout_height="wrap_content"
            android:text="Q.4. Which is the highest Tire in PUBG Mobile ? (In capital)"
            android:padding="8dp"
            android:textSize="20dp"/>

        <EditText
            android:layout_width="match_parent"
            android:layout_height="wrap_content"
            android:hint="Answer"
            android:id="@+id/answer_four"
            android:padding="8dp"/>

        <TextView
            android:layout_width="wrap_content"
            android:layout_height="wrap_content"
            android:padding="8dp"
            android:text="Q.5. What is the current season in PUBG Mobile ? (In number)"
            android:textSize="20dp" />

        <EditText
            android:layout_width="match_parent"
            android:layout_height="wrap_content"
            android:hint="Answer"
            android:id="@+id/answer_five"
            android:padding="8dp"/>

        <Button
            android:layout_width="wrap_content"
            android:layout_height="wrap_content"
            android:text="Submit"
            android:padding="8dp"
            android:onClick="answer"
            android:layout_gravity="center"
            android:textSize="18dp"/>

        <TextView
            android:layout_width="wrap_content"
            android:layout_height="wrap_content"
            android:text="RESULT"
            android:padding="8dp"
            android:layout_gravity="center"
            android:textSize="20dp"/>

        <TextView
            android:layout_width="wrap_content"
            android:layout_height="wrap_content"
            android:text="Please Submit Your Answers first"
            android:layout_gravity="center"
            android:id="@+id/result"
            android:padding="8dp"
            android:textSize="20dp"/>

    </LinearLayout>
</ScrollView>
