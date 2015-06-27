# android-sum-of-numbers-toast
suming two numbers and displaying using Toast

package com.example.itians.sum;

import android.app.Activity;

import android.os.Bundle;
import android.view.Gravity;
import android.view.Menu;
import android.view.MenuItem;
import android.view.View;
import android.widget.EditText;
import android.widget.Button;
import android.widget.LinearLayout;
import android.widget.TextView;
import android.widget.Toast;

public class MainActivity extends Activity {

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);

addListenerOnButton();
    }
public void addListenerOnButton()
{
    final EditText editText1= (EditText)findViewById(R.id.editText1);
    final EditText editText2= (EditText)findViewById(R.id.editText2);
    final Button button= (Button)findViewById(R.id.sum);
    button.setOnClickListener(new View.OnClickListener() {
        @Override
        public void onClick(View view) {
            String value1=editText1.getText().toString();
            String value2=editText2.getText().toString();
            int a=Integer.parseInt(value1);
            int b=Integer.parseInt(value2);
            int sum=a+b;
            TextView text=(TextView)findViewById(R.id.textView);
           String s= String.valueOf(sum);

            text.setText(s);
            /*Toast toast=new Toast(getApplicationContext());
            toast.makeText(getApplicationContext(), String.valueOf(sum), Toast.LENGTH_LONG).show();
            toast.setGravity(Gravity.LEFT,4,0);
            toast.setGravity(Gravity.HORIZONTAL_GRAVITY_MASK,4,0);*/

            Toast toast1 = Toast.makeText(getApplicationContext(), "sum of "+String.valueOf(a)+" + "+String.valueOf(b)+" is = "+ String.valueOf(sum), Toast.LENGTH_SHORT);
            LinearLayout toastLayout = (LinearLayout) toast1.getView();
            TextView toastTV = (TextView) toastLayout.getChildAt(0);
            toast1.setGravity(Gravity.CENTER,-190,-250);
            toastTV.setTextSize(30);
            toast1.show();
        }
    });

