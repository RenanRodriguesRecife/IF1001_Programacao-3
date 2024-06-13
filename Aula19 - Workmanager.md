# Workmanager

- Recomendado para **trabalhos persistentes**
  - O trabalho é persistente quando **permanece programado após as reinicializações do app e do sistema**
 
- É uma biblioteca que gerencia trabalhos que requerem uma combinação de **execução oportunista e garantiada**
  - **Execução oportunista** significa que o WorkManager faz o trabalho em segundo plano o **quanto antes**
 
  - **Execução garantida** se refere à lógica para **iniciar o trabalho em diversas situações**, mesmo se você sair do app
 
## Tupos de trabalho

- Imediato: tarefas que precisam começar imediatamente e terminar em breve. Podem ser priorizados

- De longa duração: tarefas que podem ser executadas por mais tempo, potencialmente mais de 10 minutos

- Adiável: tarefas programadas que começam posteriormente e podem ser executadas periodicamente

<img src=".assets/215.jpg">

<img src=".assets/216.jpg">

## Quando utilizar

Alguns exemplos de tarefas que fazem um bom uso do WorkManager:

- Consultar periodicamente as últimas notícias
- Aplicar filtros a uma imagem e salvá-la.
- Sincronização periódica de dados locais com a rede.

## Principais classes e conceitos

- **Worker**
  - **Define como o work vai ser executado**. Aceita **inputs** (workerParameters) e produz **outputs**(Data/chave - valor). Sempre vai retornar um resultado representado **SUCCESS, FAILURE ou RETRY**
 
- **WorkRequest**
  - Representa uma tarefa. Deve no mínimo especificar qual classe Worker vai executar a tarefa
 
- **Constraints**
  - **Conjunto de requisitos** que podem ser definidos. São **validados antes** que uma execução de um WorkRequest possa reaolmente acontecer. Assim o WorkRequest **só vai ser executado se esses requisitos forem atendidos.**
 
- **WorkManager**
  - **Gerencia as tarefas** que são agendadas **de forma distribuída** e **honrando as restrições** específicadas de **cada tarefa**.
(Na prática o mínimo é 15 minutos para funcionar no android)

- **WorkInfo**
  - Contém **informações sobre cada tarefa**. Podemos usar para **observar o estado da tarefa** e baseado em cada estado **tomar uma ação**
 
### Atividade

- Utilizar o workmanager para enviar uma notificação somente uma vez

1- passo

- Declarar a dependência no arquivo build:Module app

```kotlin
dependencies{
  //WorkManager dependency
  implementation("androidx.work:work-runtime-ktx: 2.9.0")
```

2 - passo

- Criar uma classe que herda Worker e implementa doWork()

```kotlin
package com.aimirisolutions.demos

import android.content.Context
import androidx.work.Worker
import androidx.work.WorkerParameters

class MyNotificationWorkManager(context: Context, workerParams: WorkerParameters):Worker(context,workerParams){
  override fun doWork(): Result{
    TODO("Not yet implemented")
}
}
```

3 - passo

- Implementar qual vai ser nossa tarefa

```kotlin
override fun doWork():Result{
  val notificationManager:NotificationManager = applicationContext.getSystemService(
    Context.NOTIFICATION_SERVICE) as NotificationManager

 if(Build.VERSION.SDK_INT >= Build.VERSION_CODES.O){
  val channel: NotificationChannel = NotificationChannel(
    "YOUR_CHANNEL_ID",
    "YOUR_CHANNEL_NAME", NotificationManager.IMPORTANCE_DEFAULT)
  channel.enableLights(true)
  channel.lightColor = Color.BLUE
  channel.description = "YOUR_NOTIFICATION_CHANNEL_DESCRIPTION"
  notificationManager.createNotificationChannel(channel)
}

val notification = NotificationCompat.Builder(
  applicationContext,
  "YOUR_CHANNEL_ID")
  .setSmallIcon(R.mipmap.ic_launcher)
  .setContentTitle("programação 3")
  .setContentText("my service")

//Perform the background task here.
//such as displaying a notification
notificationManager.notify(0,notification.build())

return Result.success()
}
```

4- passo

- Criar nossa work request no clique do botão

```kotlin
R.id.workmanager_notification -> {
  val notificationWorkRequest: WorkRequest = OneTimeWorkRequest.Builder(MyNotificationWorkManager::class.java)
  .setInitialDelay(3,TimeUnit.SECONDS)
  .build()
  WorkManager.getInstance(this).enqueue(notificationWorkRequest)
}
```

- Adicionando um constraint

```kotlin
  val constraints = Constraints.Builder()
    .setRequiresBatteryNotLow(true)
    .setRequiredNetworkType(NetworkType.CONNECTED)
    .setRequiresCharging(true)
    .setRequiresStorageNotLow(true)
    .setRequiresDeviceIdle(true)
    .build()
```

### Atividade

- Adicionadno um contraint

```kotlin
R.id.workmanager_notification_contraints -> {
  val contraints: Constraints = Constraints.Builder()
    .setRequiredNetworkType(NetworkType.CONNECTED)
    .setRequiresCharging(true)
    .build()

  val notificationWorkRequest: WorkRequest = OneTimeWorkRequest.Builder(MyNotificationWorkManager::class.java)
  .setInitialDelay(3,TimeUnit.SECONDS)
  .setConstraints(contraints)
  .build()
WorkManager.getInstance(this).enqueue(notificationWorkRequest)
}
```

- Utilizar o workmanager para enviar uma notificação inúmeras vezes

```kotlin
override fun doWork():Result{
  val notificationManager: NotificationManager = applicationContext.getSystemService(
    Context.NOTIFICATION_SERVICE) as NotificationManager

  if(Build.VERSION.SDK_INT >= Build.VERSION_CODES.O){
    val channel: NotificationChannel = NotificationChannel(
      "YOUR_CHANNEL_ID"
      "YOUR_CHANNEL_NAME", NotificationManager.IMPORTANCE_DEFAULT)
   channel.enableLights(true)
   channel.lightColor = Color.BLUE
   channel.description = "YOUR_NOTIFICATION_CHANNEL_DESCRIPTION"
   notificationMananger.createNotificationChannel(channel)
}

val notification = NotificationCompat.Bulder(
  applicationContext,
  "YOUR_CHANNEL_ID")
  .setSmallIcon(R.mipmap.ic_launcher)
  .setContentTitle("programação 3 ..." + tmp)
  .setContentText("my service")

//Perform the backgrond tesk here,
//such as displaying a notification
notificationManager.notify(0, notification.build())

Log.d("LOG","my notification work manager")

tmp++

return Result.retry()
}
```

- Utilizar o workmanager para enviar uma notificação inúmeras vezes

```kotlin
R.id.workmanager_notification_period -> {
  periodicWorkRequest = PeriodicWorkRequest.Builder(MyNotificationWorkManagerPeríod::class.java, 3, TimeUnit.SECONDS).build()
WorkManager.getInstance(this).enqueue(periodicWorkRequest)
}
R.id.workmanager_notification_period_stop -> {
  WorkManager.getInstance(this).cancelWorkById(periodicWorkRequest.id)
}
```

- Enviando mensagens I - na atividade

```kotlin
R.id.workmanager_notification_send_msg -> {
  val inputData = Data.Builder()
    .putString("data1","blah blah blah")
    .putBoolean("data2",true)
    .build()
  val notificationWorkRequest: WorkRequest = OneTimeWorkRequest.Builder(MyNotificationWorkManagerSendMsg::class.java)
  .setInputData(inputData)
  .build()
WorkManager.getInstance(this).enqueue(notificationWorkRequest)
}
```

- Recebendo mensagens no worker

```kotlin
  val data1: String? = inputData.getString("data1")
  val data2: Boolean = inputData.getBoolean("data2",false)

```

- Enviando Mensagens 2

```kotlin
R.id.workmanager_notification_send_msg2 -> {
