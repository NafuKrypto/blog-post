## Android: How to Create Multiple Edittext inside  an Alert Dialog

Alert Dialogue can be used to display any message to the user or take user choices for some task . We use it in our code to display messages from servers or maybe take single item input. A lot of us may not know that it is also possible to take multiple inputs from a user through alert dialog.

In this blog , I will show you how you can take multiple inputs from a user with edit text inside an alert dialog.

**Pre-requisite:**

- JDK installed if you want to code in Java.

- Android Studio

###  Preview of the Output
<iframe width="560" height="315" src="https://www.youtube.com/embed/47YjUtR6GGk" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

``` 1)  I am adding 4 text views to display the result after submission from the user. ``` 

``` activity_main.xml ``` 


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

    <TextView
        android:id="@+id/name_person"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:fontFamily="monospace"
        android:gravity="center"
        android:text="Name: "
        android:textColor="@color/colorPrimaryDark"
        android:textSize="25sp" />
    <TextView
        android:id="@+id/age_person"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:fontFamily="monospace"
        android:gravity="center"
        android:text="Age: "
        android:textColor="@color/colorPrimaryDark"
        android:textSize="25sp" />
    <TextView
        android:id="@+id/id_person"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:fontFamily="monospace"
        android:gravity="center"
        android:text="ID: "
        android:textColor="@color/colorPrimaryDark"
        android:textSize="25sp" />
    <TextView
        android:id="@+id/add_person"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:fontFamily="monospace"
        android:gravity="center"
        android:text="Address: "
        android:textColor="@color/colorPrimaryDark"
        android:textSize="25sp" />

<Button
    android:id="@+id/btn"
    android:layout_width="200dp"
    android:layout_height="50dp"
    android:background="#3F51B5"
    android:textColor="#ffffff"
    android:gravity="center"
    android:text="Add Information"
    android:layout_marginTop="10dp"
    android:textSize="22sp"
     />

</LinearLayout>

``` 

**Design Layout :**
 
![emu1.PNG](https://cdn.hashnode.com/res/hashnode/image/upload/v1625765124840/ZSE1Vi3iJ.png)

```  2) Now in the drawable/editbox.xml file , I am going to create a style to represent the edit box . I will call it later in the MainActivity by R.drawable.editbox. ``` 

``` editbox.xml ``` 

```
<?xml version="1.0" encoding="utf-8"?>
<shape xmlns:android="http://schemas.android.com/apk/res/android"
    android:shape="rectangle">
    <solid android:color="#DDF2FF" />
    <stroke android:width="0.5dp"
        android:color="#2196F3" />
    <corners
        android:radius="5dp"/>
</shape>

``` 

```  3) In the MainActivity , when the ÄDD Information" button is clicked , the alert dialog is opened. I am setting the background and the gravity through some set functions. All the edittext is containing with a linear layout which have a 20dp margin with the set margin() functions.   alertdialog.setView(  ) function is a must. Without it , you won't be able to view all the elements. Also don't forget to call adView().```

``` MainActivity.java ``` 


```
package com.example.alertdialogue;

import androidx.appcompat.app.AlertDialog;
import androidx.appcompat.app.AppCompatActivity;

import android.content.DialogInterface;
import android.os.Bundle;
import android.view.Gravity;
import android.view.View;
import android.widget.Button;
import android.widget.EditText;
import android.widget.LinearLayout;
import android.widget.TextView;
 

public class MainActivity extends AppCompatActivity {



    String name_str,age_str,address_str,id_str;
    TextView textViewName,textViewAge,textViewID,textViewAdd;
    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate( savedInstanceState );
        setContentView( R.layout.activity_main );

         textViewName=findViewById( R.id.name_person );
         textViewAge=findViewById( R.id.age_person );
         textViewID=findViewById( R.id.id_person );
         textViewAdd=findViewById( R.id.add_person );

        Button button =findViewById( R.id.btn );

        button.setOnClickListener( new View.OnClickListener() {
            @Override
            public void onClick(View view) {

                AlertDialog.Builder alertdialog =new AlertDialog.Builder( MainActivity.this );
                alertdialog.setTitle( "Fill up the blanks" );
                final EditText name = new EditText(MainActivity.this);
                final EditText age = new EditText(MainActivity.this);
                final EditText id = new EditText(MainActivity.this);
                final EditText address = new EditText(MainActivity.this);

                name.setHint( "Name" );  //editbox1 hint
                name.setGravity( Gravity.CENTER ); //editbox in center
                name.setBackgroundResource( R.drawable.editbox); //editbox style design

                age.setHint( "Age" );  //editbox2 hint
                age.setGravity( Gravity.CENTER );
                age.setBackgroundResource( R.drawable.editbox);

                id.setHint( "ID" ); //editbox3 hint
                id.setGravity( Gravity.CENTER );
                id.setBackgroundResource( R.drawable.editbox);

                address.setHint( "Address" );//editbox4 hint
                address.setGravity( Gravity.CENTER );
                address.setBackgroundResource( R.drawable.editbox);

                //set up in a linear layout
                LinearLayout.LayoutParams layoutParams = new LinearLayout.LayoutParams(
                        LinearLayout.LayoutParams.MATCH_PARENT, LinearLayout.LayoutParams.WRAP_CONTENT);
                layoutParams.setMargins( 20,20,20,20); //set margin

                LinearLayout lp=new LinearLayout( getApplicationContext() );
                lp.setOrientation( LinearLayout.VERTICAL );

                lp.addView( name ,layoutParams);
                lp.addView( age,layoutParams );
                lp.addView( id ,layoutParams);
                lp.addView( address ,layoutParams);
                alertdialog.setView( lp );
                alertdialog.setPositiveButton( "OK", new DialogInterface.OnClickListener() {
                    @Override
                    public void onClick(DialogInterface dialogInterface, int i) {
                        dialogInterface.dismiss();
                         name_str = name.getText().toString().trim();
                         age_str=age.getText().toString().trim();
                         id_str=id.getText().toString().trim();
                         address_str=address.getText().toString().trim();
                        //Display everything
                        textViewName.setText( "Name: "+name_str );
                        textViewAge.setText( "Age: "+age_str );
                        textViewID.setText( "ID: "+id_str );
                        textViewAdd.setText( "Address: "+address_str );

                    }
                } );

                alertdialog.setNegativeButton( "Cancel", new DialogInterface.OnClickListener() {
                    @Override
                    public void onClick(DialogInterface dialogInterface, int i) {
                        dialogInterface.dismiss();
                    }
                } );

                AlertDialog alert=alertdialog.create();
                alert.setCanceledOnTouchOutside( false );
                alert.show();
            }
        } );




    }
}


``` 


