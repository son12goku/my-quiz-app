
JAVA FILE


package com.example.android.quiz;

import androidx.appcompat.app.AppCompatActivity;

import android.os.Bundle;
import android.view.View;
import android.widget.EditText;
import android.widget.RadioButton;
import android.widget.TextView;

public class MainActivity extends AppCompatActivity {

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);
    }
    // to print result

    public void printresult(View view){
        String printmessage = answer(view);
        TextView priceTextView = (TextView) findViewById(R.id.result);
        priceTextView.setText(printmessage);
    }
    //to make sting of final  answer

    private String answer(View view){

        String messageprint;
        // to get value of 1st question

        EditText answer1Feild = (EditText) findViewById(R.id.answer_one);
        String answer1 = answer1Feild.getText().toString();

        messageprint = checkAnswer1(answer1);
        // to get answer of 2nd question

        messageprint += onClicked2(view);

        // to get value of 3rd question

        EditText answer3Feild = (EditText) findViewById(R.id.answer_three);
        String answer3 = answer3Feild.getText().toString();

        messageprint += checkAnswer3(answer3);
        // to get answer of 4th question

        messageprint += onClicked4(view);

        // to get value of 5th question

        EditText answer5Feild = (EditText) findViewById(R.id.answer_five);
        String answer5 = answer5Feild.getText().toString();

        messageprint += checkAnswer5(answer5);

        return messageprint ;
    }
    //for check 2nd answer

    public String onClicked2(View view) {
        // Is the button now checked?
        boolean checked = ((RadioButton) view).isChecked();

        // to return message
        String message = null;

        // Check which radio button was clicked
        switch(view.getId()) {
            case R.id.two_right_answer:
                if (checked)
                    message = "\n Your 2nd answer is right ";
                break;
            default:
                message = "\n Your 2nd answer is wrong ";
                break;
        }
            return message ;
    }

    //for check 4th answer

    public String onClicked4(View view) {
        // Is the button now checked?
        boolean checked = ((RadioButton) view).isChecked();

        // to return message
        String message =null ;

        // Check which radio button was clicked
        switch(view.getId()) {
            case R.id.four_right_answer:
                if (checked)
                    message = "\n Your 4th answer is right ";
                break;
            default:
                message = "\n Your 2nd answer is wrong ";
                break;
        }
    return message;
    }
    

    // to 1st check answer
    private String checkAnswer1(String answer){
        String message = null;
        if (answer == "100"){
            message += "\n Your 1st question is right";
        } else{
            message += "\n Your 1st question is wrong";
        }
        return message ;
    }

    // to 3rd check answer
    private String checkAnswer3(String answer) {
        String message = null;
        if (answer == "ACE") {
            message += "\n Your 3rd question is right";
        } else {
            message += "\n Your 3rd question is wrong";
        }
        return message;
    }

    // to 5th check answer
    private String checkAnswer5(String answer) {
        String message = null;
        if (answer == "13") {
            message += "\n Your 5th question is right";
        } else {
            message += "\n Your 5th question is wrong";
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
            android:text="Q.2. What is use of Rename card?"
            android:padding="8dp"
            android:textSize="20dp"/>

        <RadioGroup
            android:layout_width="wrap_content"
            android:layout_height="wrap_content">

        <RadioButton
            android:layout_width="wrap_content"
            android:layout_height="wrap_content"
            android:text="To change the character "
            android:id="@+id/two_wrong_answer_2"
            android:paddingLeft="8dp"
            android:textSize="16dp"/>

        <RadioButton
            android:layout_width="wrap_content"
            android:layout_height="wrap_content"
            android:text="To change the name of player's clan"
            android:paddingLeft="8dp"
            android:id="@+id/two_wrong_answer_1"
            android:textSize="16dp"/>

        <RadioButton
            android:layout_width="wrap_content"
            android:layout_height="wrap_content"
            android:text="To change the name of player's name"
            android:paddingLeft="8dp"
            android:id="@+id/two_right_answer"
            android:textSize="16dp"/>

        <RadioButton
            android:layout_width="wrap_content"
            android:layout_height="wrap_content"
            android:text="To change the player's profile picutre"
            android:paddingLeft="8dp"
            android:id="@+id/two_wrong_answer_3"
            android:textSize="16dp"/>

        </RadioGroup>

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
            android:text="Q.4. Which is the highest Tire in PUBG Mobile"
            android:padding="8dp"
            android:textSize="20dp"/>

        <RadioGroup
            android:layout_width="wrap_content"
            android:layout_height="wrap_content">

        <RadioButton
            android:layout_width="wrap_content"
            android:layout_height="wrap_content"
            android:text="ACE"
            android:id="@+id/four_wrong_answer_1"
            android:paddingLeft="8dp"
            android:textSize="16dp"/>

        <RadioButton
            android:layout_width="wrap_content"
            android:layout_height="wrap_content"
            android:text="DIAMOND"
            android:paddingLeft="8dp"
            android:id="@+id/four_wrong_answer_2"
            android:textSize="16dp"/>

        <RadioButton
            android:layout_width="wrap_content"
            android:layout_height="wrap_content"
            android:text="CONQUEROR"
            android:id="@+id/four_right_answer"
            android:paddingLeft="8dp"
            android:textSize="16dp"/>

        <RadioButton
            android:layout_width="wrap_content"
            android:layout_height="wrap_content"
            android:text="CROWN"
            android:paddingLeft="8dp"
            android:id="@+id/four_wrong_answer_3"
            android:textSize="16dp"/>

        </RadioGroup>

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
            android:onClick="printresult"
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
            android:text="Please Submit Your Answer"
            android:layout_gravity="center"
            android:id="@+id/result"
            android:padding="8dp"
            android:textSize="20dp"/>

    </LinearLayout>
</ScrollView>

