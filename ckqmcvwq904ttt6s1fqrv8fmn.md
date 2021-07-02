## Create Simple Alert Dialogue in Java | android

Alert Dialogue can be used to display any message to the user or take user choices for some task . 
Let's see how we can use it in our code. But before that, we need to have our environment ready.

**Pre-requisite:**

1. JDK installed if you want to code in Java.

2. Android Studio

# Start Coding
<iframe width="560" height="315" src="https://www.youtube.com/embed/lV8YK9AGv2U" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

1) In the main activity the button will create the alert dialog when it is clicked.

``` activity_main.xml ```


```
<?xml version="1.0" encoding="utf-8"?>
<LinearLayout xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:app="http://schemas.android.com/apk/res-auto"
    xmlns:tools="http://schemas.android.com/tools"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    android:orientation="vertical"
    android:padding="20dp"
    tools:context=".MainActivity">

<EditText
    android:id="@+id/name"
    android:hint="Name"
    android:layout_marginTop="100dp"
    android:layout_gravity="center"
    android:gravity="center"
    android:layout_width="match_parent"
    android:layout_height="50dp"/>

<Button
    android:id="@+id/btn"
    android:layout_width="100dp"
    android:layout_height="50dp"
    android:layout_gravity="center"
    android:background="#000000"
    android:textColor="#ffffff"
    android:text="Submit"
     />

</LinearLayout>

``` 
 
2)The **setTitle() **method will display the message. The   dialog **interface.dismiss()** destroys the dialog. ** alert.setCanceledOnTouchOutside( false )** dismiss the touch outside. If you are working in different activity , use that class name while creating **alertdialog** object.


``` MainActivity.java ```



```

package com.example.alertdialogue;

import androidx.appcompat.app.AlertDialog;
import androidx.appcompat.app.AppCompatActivity;

import android.content.DialogInterface;
import android.content.Intent;
import android.os.Bundle;
import android.view.View;
import android.widget.Button;
import android.widget.EditText;

public class MainActivity extends AppCompatActivity {

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate( savedInstanceState );
        setContentView( R.layout.activity_main );
        final EditText editText=findViewById( R.id.name );
        Button button=findViewById( R.id.btn );

        button.setOnClickListener( new View.OnClickListener() {
            @Override
            public void onClick(View view) {
                String name=editText.getText().toString().trim();
                AlertDialog.Builder alertdialog=new AlertDialog.Builder(MainActivity.this);
                alertdialog.setTitle( "Hi "+name+". Welcome to Codengocool " );
                alertdialog.setPositiveButton( "Ok", new DialogInterface.OnClickListener() {
                    @Override
                    public void onClick(DialogInterface dialogInterface, int i) {
                        dialogInterface.dismiss();
                        Intent intent=new Intent( MainActivity.this,Second.class );
                        startActivity( intent );
                    }
                } );

                alertdialog.setNegativeButton( "Cancel", new DialogInterface.OnClickListener() {
                    @Override
                    public void onClick(DialogInterface dialogInterface, int i) {
                        dialogInterface.dismiss();
                    }
                } );

                AlertDialog alert = alertdialog.create();
                alert.setCanceledOnTouchOutside( false );
                alert.show();
            }
        } );



    }
}

``` 

3) Creating a Second activity to show how the positive button works.


```  activity_second.xml ``` 


```
<?xml version="1.0" encoding="utf-8"?>
<LinearLayout xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:app="http://schemas.android.com/apk/res-auto"
    xmlns:tools="http://schemas.android.com/tools"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    android:orientation="vertical"
    android:gravity="center"
    tools:context=".Second">
<TextView
    android:layout_width="wrap_content"
    android:layout_height="wrap_content"
    android:layout_gravity="center"
    android:text="WElCOME"/>
</LinearLayout>

``` 


4)Just displaying a random message in Textview.

``` Second.java ``` 

 
```
package com.example.alertdialogue;

import androidx.appcompat.app.AppCompatActivity;

import android.os.Bundle;

public class Second extends AppCompatActivity {

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate( savedInstanceState );
        setContentView( R.layout.activity_second );
    }
}



``` 

 
 ## Output   

<iframe width="560" height="315" src="https://www.youtube.com/embed/YDlSMBchQWc" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

  
## Resources:

1.   [javatpoint](https://www.javatpoint.com/android-alert-dialog-example) 
2. [AlertDialog](https://developer.android.com/reference/android/app/AlertDialog)
3. [Dialog](https://developer.android.com/guide/topics/ui/dialogs) 