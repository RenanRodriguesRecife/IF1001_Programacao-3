# Data management 

- Armazenamento específico do app

- **Armazenamento compartilhado**
  
- Preferências
  
- Bancos de dados


## Armazenamento específico do app

- **Armazenamento Externo**

  - Incluem um **local dedicado** para **armazenar arquivos persistentes** e outro para **armazenar dados em cache**
 
  - Outros **apps podem acessar** esses locais com as **devidas permissões**
 
    - App precisa armazenar na parte de armazenamento compartilhado doi armazenamento externo
   
  - É **recomendado** verificar se o armazenamento externo está disponível
 
  - A fim de manter o bom desempenho do app, **não abra e feche o mesmo arquivo várias vezes**


- **Armazenamento Externo**

  - Utiliza memória externa do dispositivo
    - Sdcard
   
<img src=".assets/114.jpg">

<img src=".assets/115.jpg">

<img src=".assets/116.jpg">

<img src=".assets/117.jpg">

<img src=".assets/118.jpg">

<img src=".assets/119.jpg">

<img src=".assets/120.jpg">

<img src=".assets/121.jpg">

<img src=".assets/122.jpg">

<img src=".assets/123.jpg">

## Armazenamento específico do app

- **Armazenamento Externo detalhes**

  - O Android 4.4 (**API de nível 19**) ou **mais recentes**, o app não precisa solicitar permissões relacionadas ao armazenamento para acessar diretórios específicos do app no armazenamento externo
 
  - Android 9 (**nível 28 da API**) ou **versões anteriores** o app **pode acessar** os arquivos específicos que pertencem a outros apps, desde que ele tenha as **permissões** de armazenamento adequadas
 
  - Android 10 (**nível 29 da API**) ou mais recentes recebem acesso com escopo ao **armazenamento externo**
 
    - Os app **não** podem **acessar** os **diretórios** específicos do app que pertencem a **outros apps**.
