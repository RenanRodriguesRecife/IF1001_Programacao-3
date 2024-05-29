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

