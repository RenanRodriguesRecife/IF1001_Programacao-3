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

## Relativelayout

RelativeLayout é um ViewGroup que exibe visualizações dos seus filhos em posições relativas a elementos irmãos (i.e, a esquerda ou abeixo de outra view) ou relativas a área RelativeLayout pai (por exemplo, alinhado à parte inferior, à esquerda ou no centro)

<img src=".assets/48.jpg">

<img src=".assets/49.jpg">

<img src=".assets/50.jpg">

<img src=".assets/51.jpg">

## Tablelayout

Tablelayout é um ViewGroup que exibe elementos filhos de View em linhas e colunas.

<img src=".assets/52.jpg">

<img src=".assets/53.jpg">

<img src=".assets/54.jpg">
