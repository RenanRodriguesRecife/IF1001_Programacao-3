# Activity layouts / widgets

- Android Manifest

- Activity

- Widgets

    - Button

    - Text

    - EditText

    - ImageView

    - ImageButton


<img src=".assets/75.jpg">

<img src=".assets/76.jpg">

<img src=".assets/77.jpg">

<img src=".assets/78.jpg">

<img src=".assets/79.jpg">

<img src=".assets/80.jpg">

<img src=".assets/81.jpg">

<img src=".assets/82.jpg">

Acho que está desatualizado. fun onClick não está funcionando

```kotlin
button.setOnClickListener(){
            Log.d(LOG_MSG,"button click1")
}
```

<img src=".assets/83.jpg">

Acho que o código está errado um exemplo de EditText

```kotlin


package com.geeksforgeeks.myfirstkotlinapp
 
import androidx.appcompat.app.AppCompatActivity
import android.os.Bundle
import android.widget.Button
import android.widget.EditText
import android.widget.Toast
 
class MainActivity : AppCompatActivity() {
 
    override fun onCreate(savedInstanceState: Bundle?) {
        super.onCreate(savedInstanceState)
        setContentView(R.layout.activity_main)
 
        // finding the button
        val showButton = findViewById<Button>(R.id.showInput)
 
        // finding the edit text
        val editText = findViewById<EditText>(R.id.editText)
 
        // Setting On Click Listener
        showButton.setOnClickListener {
 
            // Getting the user input
            val text = editText.text
 
            // Showing the user input
            Toast.makeText(this, text, Toast.LENGTH_SHORT).show()
        }
    }
}
```

<img src=".assets/84.jpg">

<img src=".assets/85.jpg">

<img src=".assets/86.jpg">

<img src=".assets/87.jpg">

<img src=".assets/88.jpg">

<img src=".assets/89.jpg">

<img src=".assets/90.jpg">
