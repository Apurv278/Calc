# Calc
package com.example.appu.samplecalc;

import android.annotation.SuppressLint;
import android.support.v7.app.AppCompatActivity;
import android.os.Bundle;
import android.view.View;
import android.widget.Button;
import android.widget.TextView;

public class MainActivity extends AppCompatActivity {

    private Button one;   private Button two;   private Button three;
    private Button four;  private Button five;  private Button six;
    private Button seven; private Button eight; private Button nine;
    private Button zero;
    private Button add;   private Button mul;
    private Button sub;   private Button div;
    private Button equal; private Button clear;

    private char ACT;

    private double val1 = Double.NaN;
    private double val2;

    private final char ADDITION = '+';
    private final char Multiplication = '*';
    private final char Division = '/';
    private final char Subtraction = '-';
    private final char Equal = ' ';


    private TextView info;
    private TextView result;



    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);

        setUIVeiw();

        zero.setOnClickListener(new View.OnClickListener() {
            
            @Override
            public void onClick(View v) {
                info.setText(info.getText().toString() + "0");
            }
        });

        one.setOnClickListener(new View.OnClickListener() {
            
            @Override
            public void onClick(View v) {
                info.setText(info.getText().toString() + "1");
            }
        });

        two.setOnClickListener(new View.OnClickListener() {
            
            @Override
            public void onClick(View v) {
                info.setText(info.getText().toString() + "2");
            }
        });

        three.setOnClickListener(new View.OnClickListener() {
            
            @Override
            public void onClick(View v) {
                info.setText(info.getText().toString() + "3");
            }
        });

        four.setOnClickListener(new View.OnClickListener() {
            
            @Override
            public void onClick(View v) {
                info.setText(info.getText().toString() + "4");
            }
        });

        five.setOnClickListener(new View.OnClickListener() {
            
            @Override
            public void onClick(View v) {
                info.setText(info.getText().toString() + "5");
            }
        });

        six.setOnClickListener(new View.OnClickListener() {
            
            @Override
            public void onClick(View v) {
                info.setText(info.getText().toString() + "6");
            }
        });

        seven.setOnClickListener(new View.OnClickListener() {
            
            @Override
            public void onClick(View v) {
                info.setText(info.getText().toString() + "7");
            }
        });

        eight.setOnClickListener(new View.OnClickListener() {
            
            @Override
            public void onClick(View v) {
                info.setText(info.getText().toString() + "8");
            }
        });

        nine.setOnClickListener(new View.OnClickListener() {
            
            @Override
            public void onClick(View v) {
                info.setText(info.getText().toString() + "9");
            }
        });

        add.setOnClickListener(new View.OnClickListener() {
            
            @Override
            public void onClick(View v) {
                compute();
                ACT = ADDITION;
                result.setText(String.valueOf(val1) + "+");
                info.setText(null);
            }
        });

        sub.setOnClickListener(new View.OnClickListener() {
            
            @Override
            public void onClick(View v) {
                compute();
                ACT = Subtraction;
                result.setText(String.valueOf(val1) + "-");
                info.setText(null);
            }
        });

        mul.setOnClickListener(new View.OnClickListener() {
            
            @Override
            public void onClick(View v) {
                compute();
                ACT = Multiplication;
                result.setText(String.valueOf(val1) + "*");
                info.setText(null);
            }
        });

        div.setOnClickListener(new View.OnClickListener() {
            
            @Override
            public void onClick(View v) {
                compute();
                ACT = Division;
                result.setText(String.valueOf(val1) + "/");
                info.setText(null);
            }
        });

        equal.setOnClickListener(new View.OnClickListener() {
            
            @Override
            public void onClick(View v) {
                compute();
                ACT = Equal;
                result.setText(result.getText().toString() +  String.valueOf(val2) + "=" + String.valueOf(val1));
                info.setText(null);
            }
        });

        clear.setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View v) {
                if (info.getText().length() > 0) {
                    CharSequence name = info.getText().toString();
                    info.setText(name.subSequence(0,name.length()-1));
                }
                else {
                    val1 = Double.NaN;
                    val2 = Double.NaN;
                    info.setText(null);
                    result.setText(null);
                }
            }
        });
    }


    private void setUIVeiw() {
        one = findViewById(R.id.button14);
        two = findViewById(R.id.button12);
        three =findViewById(R.id.button11);
        four = findViewById(R.id.button10);
        five = findViewById(R.id.button9);
        six = findViewById(R.id.button8);
        seven = findViewById(R.id.button7);
        eight = findViewById(R.id.button6);
        nine = findViewById(R.id.button4);
        zero = findViewById(R.id.button15);
        add = findViewById(R.id.button18);
        mul = findViewById(R.id.button20);
        div = findViewById(R.id.button21);
        sub = findViewById(R.id.button19);
        equal = findViewById(R.id.button17);
        info = findViewById(R.id.textView);
        result = findViewById(R.id.textView2);
        clear = findViewById(R.id.button16);

    }

    private void compute(){
        if(!Double.isNaN(val1)){
            val2 = Double.parseDouble(info.getText().toString());

            switch (ACT){
                case ADDITION:
                    val1 = val1 + val2;
                    break;
                case Multiplication:
                    val1 = val1 * val2;
                    break;
                case Subtraction:
                    val1 = val1 - val2;
                    break;
                case Division:
                    val1 = val1 / val2;
                    break;
                case Equal:
                    break;
            }

        }
        else {
            val1 = Double.parseDouble(info.getText().toString());
        }
    }
}
