Notifications
- Básicas
- Extendidas
- Pending intent
- Ação
- Reply
- Image

#Notifications - Tipos

- Aparecem automaticamente para os usuários em diferentes locais e formatos
  - Ícone na barra de status
  - Entrada mais detalhada na gaveta de notificações
  - Notificações de alerta
  - Notificações de bloqueio
  - Um ícone no ícone do app
 
<img src=".assets/190.jpg">

<img src=".assets/191.jpg">

<img src=".assets/192.jpg">

## Notifications

- A partir do Android 8.0 (API de nível 26), **todas as notificações precisam ser atribuídas a um canal ou não serão exibidas!!!**

  - Abaixo do Android 8.0 (API de nível 26) isso é ignorado
 
  **Precisa ser adicionado a seguinte biblioteca nas dependências do build.gradle.kts do app**

  ```kotlin
  //notifications
  implementation("androidx.core:core-ktx:1.13.1")
  ```

  **Precisa ser adicionado a permissão no manifesto**

  ```
  <user-permission android:name="android.permission.POST_NOTIFICATIONS"/>
  ```

<img src=".assets/193.jpg">

<img src=".assets/194.jpg">

<img src=".assets/195.jpg">
