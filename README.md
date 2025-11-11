# Ex.No:3a Develop program to create a text field and a button “Navigate”. When you enter “www.gmail.com” and press navigate button it should open google page using Implicit Intents.


## AIM:

To create a navigate button using Implicit Intent to display the gmail page using Android Studio.

## EQUIPMENTS REQUIRED:

Latest Version Android Studio

## ALGORITHM:

Start the program.
Create a new Android project in Android Studio.
Name the project (e.g., MyNavigateApp).
Select appropriate SDK and finish setup.

Design the UI (activity_main.xml):
Add a TextView for instructions (optional).
Add an EditText to allow the user to enter a URL (e.g., "www.gmail.com
").
Add a Button with the text “Navigate”.

Open MainActivity.java (or MainActivity.kt):
Initialize the EditText and Button using findViewById().
Set OnClickListener for the Button:
When clicked, read the text entered in the EditText.

Prepend "https://" if it’s missing.
Create an Implicit Intent:
Use Intent(Intent.ACTION_VIEW, Uri.parse(url)).

Start the Activity with the Intent:
Call startActivity(intent) to launch the browser and open the page.
Run the application:

Enter "www.gmail.com" in the text field.
Press the Navigate button.
The default browser opens the Gmail page.
Stop the program.


## PROGRAM:
```
/*
Program to print the text “Implicitintent”.
Developed by: THEJA SREE G
Registeration Number : 212224110056
*/
```

## OUTPUT

activity_main.xml

```
<?xml version="1.0" encoding="utf-8"?>
<LinearLayout xmlns:android="http://schemas.android.com/apk/res/android"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    android:orientation="vertical"
    android:padding="20dp"
    android:gravity="center">

    <EditText
        android:id="@+id/urlEditText"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:hint="Enter URL (e.g. www.gmail.com)"
        android:inputType="textUri"
        android:padding="10dp"
        android:textSize="18sp"/>

    <Button
        android:id="@+id/navigateButton"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:text="Navigate"
        android:padding="12dp"
        android:textSize="18sp"
        android:layout_marginTop="20dp"/>
</LinearLayout>

```
MainActivity.java

```
package com.example.myimplicitintent;

import android.content.Intent;
import android.net.Uri;
import android.os.Bundle;
import android.widget.Button;
import android.widget.EditText;
import android.widget.Toast;

import androidx.appcompat.app.AppCompatActivity;

public class MainActivity extends AppCompatActivity {

    EditText urlEditText;
    Button navigateButton;

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);

        urlEditText = findViewById(R.id.urlEditText);
        navigateButton = findViewById(R.id.navigateButton);

        navigateButton.setOnClickListener(v -> {
            String url = urlEditText.getText().toString().trim();

            if (!url.isEmpty()) {
                if (!url.startsWith("http://") && !url.startsWith("https://")) {
                    url = "https://" + url;
                }

                Intent intent = new Intent(Intent.ACTION_VIEW, Uri.parse(url));
                startActivity(intent);
            } else {
                Toast.makeText(MainActivity.this, "Please enter a URL", Toast.LENGTH_SHORT).show();
            }
        });
    }
}

```
AndroidManifest.xml

```
<?xml version="1.0" encoding="utf-8"?>
<manifest xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:tools="http://schemas.android.com/tools">

    <application
        android:allowBackup="true"
        android:dataExtractionRules="@xml/data_extraction_rules"
        android:fullBackupContent="@xml/backup_rules"
        android:icon="@mipmap/ic_launcher"
        android:label="@string/app_name"
        android:roundIcon="@mipmap/ic_launcher_round"
        android:supportsRtl="true"
        android:theme="@style/Theme.MyImplicitIntent">

        
        <activity
            android:name=".MainActivity"
            android:exported="true">

            <intent-filter>
                <action android:name="android.intent.action.MAIN" />
                <category android:name="android.intent.category.LAUNCHER" />
            </intent-filter>
        </activity>

    </application>

</manifest>

```

strings.xml

```
<resources>
    <string name="app_name">MyImplicitIntent</string>
    <string name="hint_enter_url">Enter URL (e.g. www.gmail.com)</string>
    <string name="btn_navigate">Navigate</string>
</resources>
```

# Execution

<img width="1919" height="1079" alt="Screenshot 2025-09-16 082942" src="https://github.com/user-attachments/assets/cddc2ce0-154a-470c-ae62-901802551b49" />


<img width="1919" height="1076" alt="Untitled design (9)" src="https://github.com/user-attachments/assets/46089697-004e-4467-965d-93875c799599" />

<img width="1919" height="1076" alt="Untitled design (5)" src="https://github.com/user-attachments/assets/030b93b7-46ac-432a-beec-e8608c1539f2" />

<img width="1920" height="1200" alt="Screenshot 2025-11-11 133341" src="https://github.com/user-attachments/assets/1d36cee1-4375-463b-8197-bcf49b5c79cd" />


## RESULT
Thus a Simple Android Application create a navigate button using Implicit Intent to display the gmail page using Android Studio is developed and executed successfully.


