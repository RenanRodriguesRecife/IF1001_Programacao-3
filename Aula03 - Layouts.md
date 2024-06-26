## Layout

- **Layout** define a **estrutura** de uma **interface** do usuário no seu app
- Possui hierarquia de objetos **View** e **ViewGroup**
  - **View** geralmente desenha algo que o usuário pode **ver e interagir**
  - **ViewGroup** é um **contêiner invisível** que **define** a **estrutura do layout para View** e outros objetos ViewGroup

<img src=".assets/35.jpg">
 
## View e Viewgroup

- **View** geralmente são chamados de **widgets** e podem ser uma das muitas subclasses, como **Button** ou **TextView**

- **ViewGroup** geralmente são chamados de **layouts** e podem ser de vários tipos que fornecem uma estrutura de layout diferente, como **LinearLayout** ou **ConstraintLayout**

- **Layouts** e **widgets** podem ser declarados de **duas maneiras**:
  - **Declarar** elementos de interface em **XML**
  - **Instanciar** elementos do layout em **run-time**
 
- Arquivo xml de layout são salvos no diretório res/layout

<img src=".assets/36.jpg">

<img src=".assets/37.jpg">

<img src=".assets/38.jpg">

### Viewgroups

- **LinearLayout**: alinha seus filhos em uma única direção:vertical ou horizontal
- **RelativeLayout**: alinha seus filhos em posição relativa
- **TableLayout**: alinha seus filhos em linhas e colunas
- **FrameLayout**: é um placeholder que é usado para mostrar um única view ou stack de views
- **ConstraintLayout**: alinha as views com base em regras

<img src=".assets/39.jpg">

## Linearlayout

LinearLayout é um ViewGroup que alinha todos os filhos em um única direção vertical ou horizontal

<img src=".assets/40.jpg">

### Linearlayout Attributes

<img src=".assets/41.jpg">

<img src=".assets/42.jpg">

<img src=".assets/43.jpg">

<img src=".assets/44.jpg">

<img src=".assets/45.jpg">

<img src=".assets/46.jpg">

### Linearlayouts - Atividade

<img src=".assets/47.jpg">

```kotlin
<LinearLayout
xmlns:app="http://schemas.android.com/apk/res-auto"

xmlns:tools="http://schemas.android.com/tools"
    xmlns:android="http://schemas.android.com/apk/res/android"
    android:id="@+id/main"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    android:orientation="horizontal"
    tools:context=".MainActivity">


    <Button
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:layout_gravity="center"
        android:layout_weight="1"
        android:layout_marginLeft="10dp"
        android:text="Hello World!"/>

    <Button
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:layout_gravity="center"
        android:layout_weight="1"
        android:text="Hello World!"/>

    <Button
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:layout_gravity="center"
        android:layout_weight="1"
        android:layout_marginRight="10dp"
        android:text="Hello World!"/>
</LinearLayout>
```

## Relativelayout

RelativeLayout é um ViewGroup que exibe visualizações dos seus filhos em posições relativas a elementos irmãos (i.e, a esquerda ou abeixo de outra view) ou relativas a área RelativeLayout pai (por exemplo, alinhado à parte inferior, à esquerda ou no centro)

<img src=".assets/48.jpg">

<img src=".assets/49.jpg">

<img src=".assets/50.jpg">

<img src=".assets/51.jpg">

```kotlin
<?xml version="1.0" encoding="utf-8"?>
<RelativeLayout xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:app="http://schemas.android.com/apk/res-auto"
    xmlns:tools="http://schemas.android.com/tools"
    android:id="@+id/main"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    tools:context=".MainActivity">

    <Button
        android:id="@+id/btn1"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:text="Button1"
        android:layout_marginLeft="10dp"/>
        

    <Button
        android:id="@+id/btn2"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:text="Button2"
        android:layout_alignParentRight="true"
        android:layout_centerInParent="true"
        android:layout_marginRight="10dp"
        />

    <Button
        android:id="@+id/btn3"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:text="Button3"
        android:layout_alignParentLeft="true"
        android:layout_centerInParent="true"
        android:layout_marginLeft="10dp"
        />

    <Button
        android:id="@+id/btn4"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:text="Button4"
        android:layout_alignParentBottom="true"
        android:layout_marginHorizontal="10dp"
        />

    <Button
        android:id="@+id/btn5"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:text="Button5"
        android:layout_centerInParent="true"
        />

    <Button
        android:id="@+id/btn6"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:text="Button6"
        android:layout_above="@id/btn4"
        android:layout_centerInParent="true"
        />

    <Button
        android:id="@+id/btn7"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:text="Button7"
        android:layout_toEndOf="@id/btn1"
        android:layout_centerHorizontal="true"
        android:layout_marginRight="10dp"
        />
</RelativeLayout>
```

## Tablelayout

Tablelayout é um ViewGroup que exibe elementos filhos de View em linhas e colunas.

<img src=".assets/52.jpg">

<img src=".assets/53.jpg">

<img src=".assets/54.jpg">

## Framelayout

- Framelayout foi criado para bloquear uma parte da tela para mostrar múltiplas views como uma só. As views são desenhadas em forma de stack de forma que uma sobrepõe a outra

- Pode-se usar layout_gravity para posicionar as view

<img src=".assets/55.jpg">

<img src=".assets/56.jpg">

## Constraintlayout

- Constraint significa algo como "restrição" ou "limitação"

- O ConstraintLayout permite que você crie layouts grandes e complexos com uma hierarquia flat no seu XML (sem a necessidade de ficar alinhando um monte de layouts uns dentro dos outros).

- Ele é similar ao Reletivelayout, uma vez que todas suas views se relacionam entre si e com o parent

<img src=".assets/57.jpg">

<img src=".assets/58.jpg">

<img src=".assets/59.jpg">

<img src=".assets/60.jpg">

<img src=".assets/61.jpg">

```kotlin
<?xml version="1.0" encoding="utf-8"?>
<androidx.constraintlayout.widget.ConstraintLayout xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:app="http://schemas.android.com/apk/res-auto"
    xmlns:tools="http://schemas.android.com/tools"
    android:id="@+id/main"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    tools:context=".ConstraintLayout">

    <Button
        android:id="@+id/buttonA"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:text="ButtonA"
        tools:layout_marginLeft="45dp"
        tools:layout_marginTop="243dp"
        app:layout_constraintTop_toTopOf="parent"
        app:layout_constraintStart_toStartOf="parent"/>

    <Button
        android:id="@+id/buttonB"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:text="ButtonB"
        tools:layout_marginLeft="57dp"
        app:layout_constraintTop_toTopOf="@+id/buttonA"
        app:layout_constraintStart_toEndOf="@id/buttonA"
        app:layout_constraintEnd_toEndOf="parent"/>

    <Button
        android:id="@+id/buttonC"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:layout_marginStart="4dp"

        android:layout_marginTop="60dp"
        android:text="ButtonC"
        app:layout_constraintStart_toStartOf="@id/buttonA"
        app:layout_constraintTop_toBottomOf="@+id/buttonA"
        app:layout_constraintEnd_toEndOf="@+id/buttonA"/>


</androidx.constraintlayout.widget.ConstraintLayout>
```

### Referências

- https://developer.android.com
- livros:
  Pro Android UI wallace Jackson

  Android UI Fundamentals develop and design - jason Ostrander

  Android UI Design Plan, design, and build engaging user interfaces for your Android applications - Jassica Thornsby


```
OBS: Para organizar o código XML rapidamente você pode rodar o comando: (CTRL+ALT+L)

```

## Exercício

- Criar um novo projeto Empty Views Project

- Ir para res/layout


<img src=".assets/62.jpg">

<img src=".assets/63.jpg">

<img src=".assets/64.jpg">

<img src=".assets/65.jpg">

<img src=".assets/66.jpg">

<img src=".assets/67.jpg">

<img src=".assets/68.jpg">

<img src=".assets/69.jpg">

<img src=".assets/70.jpg">

obs: Correção é relativeLayout não linearLayout

<img src=".assets/71.jpg">

<img src=".assets/72.jpg">

<img src=".assets/73.jpg">

<img src=".assets/74.jpg">

```kotlin
<?xml version="1.0" encoding="utf-8"?>
<androidx.constraintlayout.widget.ConstraintLayout xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:app="http://schemas.android.com/apk/res-auto"
    xmlns:tools="http://schemas.android.com/tools"
    android:id="@+id/main"
    android:layout_width="match_parent"
    android:layout_height="match_parent"

    tools:context=".MainActivity">


    <TextView
        android:id="@+id/text1"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:text="Hello World!"
        app:layout_constraintBottom_toBottomOf="parent"
        app:layout_constraintEnd_toEndOf="parent"
        app:layout_constraintStart_toEndOf="@+id/text3"
        app:layout_constraintTop_toTopOf="parent" />

    <TextView
        android:id="@+id/text2"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:text="Hello World!"
        app:layout_constraintBottom_toTopOf="@id/text1"
        app:layout_constraintEnd_toStartOf="@id/text1"
        app:layout_constraintStart_toEndOf="@id/text3" />

    <TextView
        android:id="@+id/text3"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:text="Hello World!"
        app:layout_constraintBottom_toBottomOf="@id/text2"
        app:layout_constraintEnd_toStartOf="@+id/text1"
        app:layout_constraintStart_toStartOf="parent"
        app:layout_constraintTop_toTopOf="@id/text4" 
        app:layout_constraintHorizontal_chainStyle="packed"/>

    <TextView
        android:id="@+id/text4"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:text="Hello World!"
        app:layout_constraintEnd_toStartOf="@id/text1"
        app:layout_constraintStart_toEndOf="@id/text3"
        app:layout_constraintTop_toBottomOf="@+id/text3" />


</androidx.constraintlayout.widget.ConstraintLayout>
```
