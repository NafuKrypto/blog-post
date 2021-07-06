## How to make a SingleItem choice for the user inside an Alert Dialog with Android

We developers do a lot of work with Alert Dialog. One thing that is common for alert dialog is that displaying alert messages with it. But not only you can display messages , but you can also take user input inside an alert dialog.

The advantage here is that , it will save your time designing or coding for a new Activity or Fragment.

Pre-requisite:

 
1.  JDK installed if you want to code in Java.
2.  Android Studio

# Start Coding

<iframe width="560" height="315" src="https://www.youtube.com/embed/QUn6KAaQW3E" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>


```1) Create a New Project. In the activity_main.xml add a Linear Layout and Button like below.```
      
 
```
<?xml version="1.0" encoding="utf-8"?>
<LinearLayout xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:app="http://schemas.android.com/apk/res-auto"
    xmlns:tools="http://schemas.android.com/tools"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    android:orientation="vertical"
    android:gravity="center"
    android:padding="20dp"
    tools:context=".MainActivity">



<Button
    android:id="@+id/btn"
    android:layout_width="500dp"
    android:layout_height="50dp"
    android:layout_gravity="center"
    android:background="#000000"
    android:textColor="#ffffff"
    android:gravity="center"
    android:text="Choose Language"
    android:textSize="20sp"
     />

</LinearLayout>

``` 


```2) Then in the Mainactivity.java class create an object of the Builder class. Set a title with a setTitle() method and in an array named items save all the items name you want your user to select from. The method setSingleChoiceItems() builds the alert dialog with single item selection. 
The values of checkeditem variable checks the item of the Alert dialog when opened.  For this code it will make checked with Bangla each time opened.When you select Ok in the dialog , the dialog will dismissed and a toast message will display your choice made in the radio group. If cancelled , the dialog will just dismissed.``` 


```
package com.example.alertdialogue;

import androidx.appcompat.app.AlertDialog;
import androidx.appcompat.app.AppCompatActivity;

import android.content.DialogInterface;
import android.os.Bundle;
import android.view.View;
import android.widget.Button;
import android.widget.EditText;
import android.widget.Toast;

public class MainActivity extends AppCompatActivity {
    String language;



    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate( savedInstanceState );
        setContentView( R.layout.activity_main );

        Button button=findViewById( R.id.btn );

        button.setOnClickListener( new View.OnClickListener() {
            @Override
            public void onClick(View view) {
               
                AlertDialog.Builder alertdialog=new AlertDialog.Builder(MainActivity.this);
                alertdialog.setTitle( "Choice any one language" );
                String[] items = {"Bengal","English","Korean"};

                int chekeditem=0;
                alertdialog.setSingleChoiceItems( items, chekeditem, new DialogInterface.OnClickListener() {
                    @Override
                    public void onClick(DialogInterface dialogInterface, int i) {
                        switch (i){
                            case 0:
                                language="Bengal";
                                break;
                            case 1:
                                language="English";
                                break;
                            case 2:
                                language="Korean";
                                break;


                        }
                    }
                } );
                alertdialog.setPositiveButton( "Ok", new DialogInterface.OnClickListener() {
                    @Override
                    public void onClick(DialogInterface dialogInterface, int i) {
                        dialogInterface.dismiss();
                        Toast.makeText( MainActivity.this,"You have chosen "+language,Toast.LENGTH_LONG ).show();
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

# Reference:
https://www.geeksforgeeks.org/alert-dialog-with-singleitemselection-in-android/
