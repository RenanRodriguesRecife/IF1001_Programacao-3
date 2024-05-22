# Aula01

## Motivação

- Motivação
- Formato das aulas
- Calendário
- Nivelamento Kotlin
  - Variáveis
  - Operadores
  - Hello world
- Bibliografia

<img src=".assets/01.JPG">

<img src=".assets/02.JPG">

<img src=".assets/03.JPG">

<img src=".assets/04.JPG">

<img src=".assets/05.JPG">

## Android

<img src=".assets/06.JPG">

<img src=".assets/07.JPG">

<img src=".assets/08.JPG">

<img src=".assets/09.JPG">

- Atividade: Falar um pocuo sobre você e uma ideia de aplicativo

- Atividade: Instalar o IntelliJ - (https://www.jetbrains.com/idea/)


## Kotlin

### Variáveis

- Nomes são **case-sensitive** (number não é o mesmo que Number, a mesma letras maiúscula e minúsculas são tratadas como letras diferentes)

- Cada nome pode incluir apenas **letras, dígitos, e underscores** (carácter de sublinhado _)

- Um nome **não pode começar com um dígito**

- Um nome **não pode ser uma palavra chave**(por exemplo, val, var, fun são ilegais)

- Variáveis
  - Char…….: caracter
  - String….: texto
  - Byte.……: -128 … 127
  - Short…..: -32768 … 32767
  - Int.………: -2_147_483_648 … 2_147_483_647
  - Long.……: -9_223_372_036_854_775_808 … 9_223_372_036_854_775_807
  - Float……: 7 casas decimais
  - Double..: 15 casa decimais
  - Boolean: true, false

- kotlin aceita undescore para compreenção.


### VAR x VAL 

ambas querem dizer variaveis

VAR - Mutável

VAL - Imutável 

```kotlin
fun main(){
  val a: Int = 1
  val b = 2
  val c: Int
  c = 3
  println("a = $a,b = $b, c = $c")
}
```

```kotlin
fun main(){
  var x = 5
  x += 1
  println("x = $x")
```

### CONST x VAL

Const - Tempo de compilação

VAL - Tempo de Execução





intends - são intensões que tem no android para requisitar certas funções: camera, calendário. você pode passar e receber informações de uma intend para outra.

data management - banco de dados, persitências

threads 

permisões

broadcast recivers - é quando ocorre algum evento no celular e o aplicativo tá abilitado em fazer alguma coisa quando recebe esse broadcast.
Ex: você está recebendo uma mensagem e seu aplicativo ver que recebeu e faz alguma coisa.

notificações

Service workmanager - serviços que ficam rodando por tráz. Serviços que ficam continuamente rodando.

Conecção com internet - uso de API


IDE - IntelliJ IDEA

--------------------

Nivelamento de Código - Kotlin



Você pode Ter uma const val: Isso é uma constante em tempo de compilação
(mais na frente isso vai fazer sentido)

Obs: as variáveis precisam ser inicializadas

Função main
(slide)

operadores
(slide)

comentários
(slide)

24 27
-----------------

7:33

------------------------



Operador Elvis

lista x spt

spt só aceita valores únicos
