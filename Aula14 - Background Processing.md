- Background processing
  - Async e await
  - Handlers e looper

## launch

- Inicia uma nova sub-rotina e não retorna o resultado para o autor da chamada. Qualquer trabalho que seja considerado "**disparar e esquecer**" pode ser iniciado usando launch.

 ```kotlin

  lifecycleScope.launch(){
    counter()
  }

```

- Qual vai ser o resultado do seguinte código

```kotlin

  lifecycleScope.launch(){
    counter()
    counter2()
}
```

## Atividade

<img src=".assets/174.jpg">

- No clique do primeiro botão

```kotlin

lifecycleScope.launch(){
  counter()
  counter2()
  Toast.makeText(applicationContext,"launch sequentially", Toast.LENGHT_SHORT).show()
```

- No clique do segundo botão


```kotlin

lifecycleScope.launch(){
  launch(counter())
  launch(counter2())
  Toast.makeText(applicationContext,"launch sequentially", Toast.LENGHT_SHORT).show()
```
  
## async

- Inicia uma nova sub-rotina e permite retornar o resultado com uma função de suspensão chamada **await**

```kotlin
lifecycleScope.launch{
  val deferred1 = async { counter()}
  deferred2 = async { counter2()}
  deferred1.await()
  deferred2.await()
}
```

- Podemos cancelar uma async chamando o cancal()

```kotlin
deferred2.cancel()
```

<img src=".assets/175.jpg">

<img src=".assets/176.jpg">

<img src=".assets/177.jpg">

## Criando seu próprio escopo

```kotlin
class ExampleClass{
//Job and Dispatcher are combined into a CoroutineContext which
//wii be discussed shortly

val scope = CoroutineScope(Job() + Dispatchers.Main)

fun exampleMethod(){
  //Starts a new coroutine within the scope
  scope.launch{
    //New coroutine that can call suspend functions
    fetchDocs()
  }
}

fun cleanUp(){
  // Cancel the scope to cancel ongoing coroutines work
 scope.cancel()
}
}
```

## Nomeando sua sub-rotina

```kotlin
class ExampleClass{
  val scope = CoroutineScope(Job() + Dispatchers.Main)
  fun exampleMethod(){
    //Starts a new coroutine on Dispatchers.Main as it's the scope's default
    val job1 = scope.launch{
      //New coroutine with CoroutineName = "coroutine" (default)
    }

    //Starts a new coroutine on Dispatchers.Default

    val job2 = scope.launch(Dispatchers.Default + CoroutineName("BackgroundCoroutine")){
        //New Coroutine with CoroutineName = "BackgroundCoroutine" (overridden)
    }
}
}
```

## Outras formas de criação de threads

- runnable
  - É uma interface que requer implementação do método run():
 
```kotlin
val runnable = object:Runnable{
    override fun run(){
      for(i in 1 <= ... <= 100){
        println("first runnable value: $i")
      }
}
}
```

- Para executar a thread:

```kotlin
runnable.run()
```

## Outras forma de criaçaõ de threads

- handler
  - Encarregado de enviar mensagens entre threads. Para isso precisa de um runnable
      - post, sendMessage, postDelayed

- looper
  - Encarregado de executar as mensagens de um thread
 
- messageQueue
  - lista de mensagens para serem executadas no looper
 
<img src=".assets/178.jpg">

