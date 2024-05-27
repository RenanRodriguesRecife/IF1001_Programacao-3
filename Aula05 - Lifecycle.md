# Lifecycle

- Lifecycle
- Callback
  - onCreate()
  - onStart()
  - onResume()
  - onStop()
  - onRestart()
  - onDestroy()

## Lifecycle

- São **diferentes estados** no **ciclo de vida** de um **aplicativo**

- **Activity** fornece vários **callbacks** que permitem que a atividade saiba quando um **estado muda** ou que o **sistema está criando**
  - Programar como a atividade deve se comportar quando o usuário sai e retorna dela

- Callback do ciclo de vida pode ajudar seu app e evitar o seguinte:
  - **Falhas** se o usuário receber uma chamada telefônica ou mudar
  - **Consumo de recursos** importante do sistema quando o usuário não estiver usando ativamente o aplicativo
  - **Perda do progresso** do usuário se ele sair do aplicativo e retornar mais tarde
  - **Falhas ou perdas do progresso** do usuário quando a **orientação da tela mudar** entre paisagem e retrato
 
  
<img src=".assets/91.jpg">

## onCreate()

- **Precisa ser implementado**
- **Acionado** assim que o sistem **cria a atividade**
- Acontece apenas **uma vez** durante toda a vida útil da atividade

```kotlin
class ImageButton_Example : AppCompatActivity(), View.OnClickListener{

  val LOG_MSG = "main_activity"
  lateinit var imageButton1: ImageButton

  override fun onCreate(savedInstanceState: Bundle?){
    super.onCreate(savedInstanceState)
    enableEdgeToEdge()
    setContentView(R.layout.imagebutton_example)

    imageButton1 = findViewById<ImageButton>(R.id.imagebutton1) as ImageButton
    imageButton1.setOnClickListener(this)
}

  override fun onClick(p0: View?){
    Log.d(LOG_MSG, "image button click")
  }
}
```

## onStart()

- Essa chamada torna a **atividade visível para o usuário** enquanto o app se prepara para que a **atividade entre em primeiro plano** e se torne **interativa**.

```kotlin

override fun onStart(){
  super.onStart()

  val year = calendar.get(Calendar.YEAR)
  val month = calendar.get(Calendar.MONTH)
  val day = calendar.get(Calendar.DAY_OF_MONTH)

  val hour = calendar.get(Calendar.HOUR_OF_DAY)
  val minute = calendar.get(Calendar.MINUTE)
  val second = calendar.get(Calendar.SECOND)

  Log.d(LOG_MSG, "onStart() " + day + "/" + month + "/" + year + " " + hour + ":" + minute + ":" + second)
}
```

- Essa chamada torna a **atividade visível para o usuário** enquanto o app se prepara para que a **atividade entre em primeiro plano** e se torne **interativa**.

## onResume()

- É nesse estado que o aplicativo interage com o usuário
- Permenece nesse estado até

  - Receber uma ligação
 
  - Navegar para outra atividade
 
  - Desligar tela/dispositivo
 
```kotlin

